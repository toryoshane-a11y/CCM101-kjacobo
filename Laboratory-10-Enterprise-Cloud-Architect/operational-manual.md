# Operational Manual: CloudNova Enterprise Portal

Handover document for the client IT team. Stack: WordPress + MariaDB on Docker, Ubuntu Server, VirtualBox.

## 1. Overview

Two-tier application deployed as code:

- **Web tier:** `cloudnova-web` (WordPress), published on host port 8080 (container port 80). Networks: `frontend`, `backend`.
- **Database tier:** `cloudnova-db` (MariaDB 11), **no published ports**, reachable only on the `backend` network. Has a healthcheck; WordPress waits for it to be healthy.
- **Storage:** named volumes `db_data` (database) and `wp_data` (WordPress files) survive container recreation and VM reboots.
- **Automation:** `automation-script.sh` runs daily at 02:00 via cron (health check, then backup).

See `architecture-diagram.png` in this folder.

## 2. Prerequisites

- VirtualBox VM running Ubuntu Server, NAT adapter with port forwards:
  - `2222 → 22` (SSH)
  - `8080 → 8080` (web)
- Internet access for pulling images.
- Recommended VM size: 2 CPUs, 2 GB RAM or more. (A single CPU caused slow first starts and CPU stalls during testing.)

## 3. Deployment

```bash
# Install Docker and Compose
sudo apt update
sudo apt install -y docker.io docker-compose-v2
sudo systemctl enable --now docker
sudo usermod -aG docker $USER      # log out and back in

# Get the project
mkdir -p ~/cloudnova-stack/scripts && cd ~/cloudnova-stack
# copy docker-compose.yml and .env.example here,
# and automation-script.sh into the scripts/ folder, then:
cp .env.example .env && nano .env  # set strong passwords

docker compose config              # validate (should show no WARN lines)
docker compose up -d
docker compose ps                  # db should become "healthy"
```

Open `http://localhost:8080` and complete the WordPress installer.

> Always run `docker compose` from the project folder so it finds `.env` and uses the correct project name.

## 4. Security hardening

```bash
sudo ufw default deny incoming
sudo ufw default allow outgoing
sudo ufw limit 22/tcp comment 'SSH (rate limited)'
sudo ufw allow 8080/tcp comment 'WordPress HTTP'
sudo ufw logging on
sudo ufw enable
sudo ufw status verbose
```

| Control | Reason |
|---|---|
| Default deny incoming | Nothing is reachable unless explicitly allowed |
| `limit 22/tcp` | Rate-limits SSH to slow brute-force attempts |
| `allow 8080/tcp` | The only application port |
| DB has no `ports:` entry | MariaDB is reachable only inside the Docker `backend` network |
| Secrets in `.env` | Kept out of Git via `.gitignore` |

**Known caveat:** Docker publishes ports by writing its own iptables rules, which can bypass UFW. Never add `ports: "3306:3306"` to the database service.

## 5. Automation

`automation-script.sh` has four modes:

```bash
./automation-script.sh backup     # database dump + WordPress files archive
./automation-script.sh health     # check services and self-heal
./automation-script.sh restore <file.sql.gz>   # restore the database
./automation-script.sh all        # health check, then backup (used by cron)
```

**Backup**
1. Dumps all databases from `cloudnova-db` (`mariadb-dump`) to `~/cloudnova-backups/db_<timestamp>.sql.gz`. The password is read from inside the container, never typed on the command line.
2. Archives the `wp_data` volume to `~/cloudnova-backups/wp_<timestamp>.tar.gz`.
3. Deletes backups older than 7 days.
4. Logs to `~/cloudnova-backups/automation.log`.

**Health check (self-healing)**
- Restarts the stack if either container is not running.
- Restarts the database if its healthcheck is not `healthy`.
- Restarts the web container if `http://localhost:8080` does not return HTTP 200, 301 or 302.

**Restore** asks you to type `YES` before it overwrites the database.

The script works from the project folder, which defaults to `~/cloudnova-stack` and can be changed with `PROJECT_DIR`. The backup folder defaults to `~/cloudnova-backups` and can be changed with `BACKUP_DIR`.

```bash
chmod +x scripts/automation-script.sh
./scripts/automation-script.sh all        # manual test
crontab -e                                # add the line from crontab.txt
crontab -l                                # verify
journalctl -u cron | grep automation-script   # confirm cron executed it
tail -n 20 ~/cloudnova-backups/automation.log # read the script's own log
```

Schedule: `0 2 * * *` (daily at 02:00).

## 6. Maintenance

```bash
cd ~/cloudnova-stack
docker compose ps                         # status
docker compose logs --tail 50 wordpress   # app logs
docker compose logs --tail 50 db          # database logs
docker compose pull && docker compose up -d   # update images
docker compose restart wordpress          # reconnect app to DB
sudo ufw status verbose                   # firewall check
ls -lh ~/cloudnova-backups                # backup check
```

**Never run `docker compose down -v` on a live site.** The `-v` flag deletes the data volumes.

## 7. Disaster recovery

**Restore the database** (use the full path to the backup file, because the script changes into the project folder first):
```bash
~/cloudnova-stack/scripts/automation-script.sh restore ~/cloudnova-backups/db_<timestamp>.sql.gz
```

**Restore WordPress files:**
```bash
cd ~/cloudnova-stack
docker compose stop wordpress
docker run --rm -v cloudnova-stack_wp_data:/data -v ~/cloudnova-backups:/backup alpine \
  sh -c "cd /data && tar xzf /backup/wp_<timestamp>.tar.gz"
docker compose start wordpress
```

## 8. Troubleshooting (issues met during the build)

| Symptom | Cause | Fix |
|---|---|---|
| Browser shows "Welcome to nginx!" instead of WordPress | Test nginx still holding port 80 | `sudo systemctl disable --now nginx`, then `docker compose up -d` |
| Host browser cannot reach the VM | NAT mode with no port forward, or wrong guest port | Add `8080 → 8080` rule; make the compose `ports:` match |
| Duplicate rule error in VirtualBox | Two forwards used host port 8080 | Delete the duplicate rule |
| `docker compose up` stuck on "Pulling fs layer" | Large image, slow or stalled connection | Ctrl+C, run `docker pull <image>` to see progress, retry |
| `additional properties '/services' not allowed` | Malformed `docker-compose.yml` | Rewrite the file cleanly; validate with `docker compose config` |
| `variable is not set` warnings, project named after the home folder | Compose run from the wrong directory | `cd ~/cloudnova-stack` first |
| "Error establishing a database connection" after reboot | DB not running or not ready when WordPress started | `docker compose up -d`, wait for `healthy`, `docker compose restart wordpress` |
| CPU soft lockup messages, slow start/SSH login | VM under-provisioned | Give the VM 2 CPUs and 2 GB+ RAM |
| `cat > scripts/...: No such file or directory` | `scripts/` folder not created | `mkdir -p scripts` |

## 9. Known limitations and improvements

- Backups are stored on the same VM. Copy them off-host (rsync/scp or cloud storage) for real disaster recovery.
- HTTP only. Add HTTPS (reverse proxy + certificate) for production.
- SSH uses password login. Use key-based authentication and disable passwords.
- No monitoring or alerting yet (e.g., Prometheus/Grafana or health-check emails).
