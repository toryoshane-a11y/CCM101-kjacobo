# CloudNova Enterprise Portal: CCM101 Final Mission

**Author:** Xerzes Kurt G. Jacobo  |  **Course:** CCM101 Cloud Computing  |  **Role:** Enterprise Cloud Architect

A secure, automated, multi-tier private cloud environment: **WordPress + MariaDB** in Docker containers on **Ubuntu Server** inside **VirtualBox**, hardened with **UFW** and managed by a **Bash script on a cron schedule**.

![Architecture](architecture.png)

## Stack

| Layer | Technology |
|---|---|
| Host / Hypervisor | Windows laptop, VirtualBox (NAT: 8080→8080, 2222→22) |
| OS | Ubuntu Server (`cloudnova-server`) |
| Firewall | UFW: default deny incoming; 22/tcp (rate limited) and 8080/tcp allowed |
| Orchestration | Docker + Docker Compose |
| Web tier | `cloudnova-web` (`wordpress:latest`), host port 8080 → container port 80 |
| Database tier | `cloudnova-db` (`mariadb:11`), not published to the host |
| Persistent storage | Named volumes `db_data`, `wp_data` |
| Automation | `automation-script.sh` (health check, backup, restore) run by cron daily at 2:00 AM |

## Repository contents

| File | Purpose |
|---|---|
| `docker-compose.yml` | Infrastructure as Code for the full stack |
| `.env.example` | Template for secrets (the real `.env` is git-ignored) |
| `.gitignore` | Keeps the real `.env` out of Git |
| `automation-script.sh` | Health check with self-healing, database and file backup with 7-day retention, and restore |
| `crontab.txt` | The scheduled job |
| `operational-manual.md` | Handover manual for the client IT team |
| `final-reflection.md` | Journey from Mission 1 to Mission 10 |
| `architecture-diagram.png` | Network topology and architecture diagram |
| `screenshots/` | Evidence for each requirement |

## Quick start

```bash
git clone https://github.com/toryoshane-a11y/CCM101-kjacobo.git
cd CCM101-kjacobo/Laboratory-10-Enterprise-Cloud-Architect
cp .env.example .env      # then edit with strong passwords
docker compose up -d
docker compose ps
```
Browse to `http://localhost:8080` (via the VirtualBox port forward). Full steps are in [operational-manual.md](operational-manual.md).

## Requirements evidence

| Requirement | Evidence |
|---|---|
| 1. Base infrastructure and design | `architecture-diagram.png`, `screenshots/wordpress-browser.png`, `screenshots/port-forwarding.png` |
| 2. Deployment (IaC, persistence) | `docker-compose.yml`, `screenshots/docker-compose-ps.png`, `screenshots/site-after-reboot.png` |
| 3. Security | `screenshots/ufw-status-verbose.png` |
| 4. Automation | `automation-script.sh`, `crontab.txt`, `screenshots/backup-script-and-files.png`, `screenshots/crontab-and-journalctl.png` |
| 5. Documentation | `operational-manual.md`, `final-reflection.md`, this README |
