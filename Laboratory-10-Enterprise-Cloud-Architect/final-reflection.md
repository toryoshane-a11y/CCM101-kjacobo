# Final Reflection: From Mission 1 to Mission 10

## The Journey

When I started this course, I could barely tell what was happening inside a terminal. In Mission 1, I was running basic commands to look at a Linux system for the first time. By Mission 10, I was designing, deploying, securing, automating and documenting a complete multi-tier system on my own, with no step-by-step guide. The biggest change was moving from typing commands one at a time to describing a whole system in code and trusting that code to rebuild it.

Each mission added a layer that I used in the final project:

- **Linux and the command line (Missions 1-2):** I learned to inspect a server's OS, CPU, memory, disk and network, and to manage files, permissions and services. In the final project I used this daily, including `chmod +x` for my script and `systemctl` to manage services.
- **Cloud concepts (Missions 2-3):** Comparing AWS, Azure and GCP showed me that the same building blocks (compute, storage, networking, identity) appear under different names, so skills transfer between providers.
- **Containers (Missions 4-6):** Docker taught me how images and containers work. Docker Compose then let me describe a multi-tier application in one file, with a database tier and a web tier, and with named volumes so data survives a restart.
- **Observability (Mission 7):** Reading logs and container metrics taught me to prove a system is healthy instead of assuming it is.
- **Security (Mission 8):** Using UFW with a default deny policy taught me to open only the ports I truly need, and to keep the database port unpublished so it is reachable only from the web container.
- **Automation (Mission 9):** Bash and cron removed the human from the backup process, which is what my final project's backup script does.
- **Documentation (every mission):** Writing the operational manual made me explain my own decisions clearly enough for someone else to repeat them.

## The Hardest Problems and How I Solved Them

1. **Reaching the VM from my browser.** With NAT networking, my host could not reach the VM until I set up port forwarding, and I had to make the port in my compose file match the forwarded port.
2. **A stalled image pull.** Compose showed no progress, so I pulled the image directly to see what was really happening.
3. **YAML and folder mistakes.** An invalid compose file and commands run from the wrong folder taught me to validate with `docker compose config` and to always check my working directory.
4. **Database connection errors after a restart.** I learned that startup order matters, that a slow VM makes it worse, and that my named volumes kept the data safe the whole time.
5. **Proving cron really ran.** Backup files appearing was not enough evidence, so I used `journalctl -u cron` to show that cron itself executed the script.

Earlier missions had their own surprises, such as image registries that stopped allowing downloads and Git pushes that were rejected. Each one taught me the same habit: read the exact error message, form a theory, and test one fix at a time.

## What I Would Improve

Given more time, I would add off-site backups so a lost VM cannot also mean lost backups, HTTPS for the web tier, SSH keys instead of passwords, and monitoring with alerts.

## What "An Architect Writes the Manual" Means to Me

An architect's job is not finished when the server works, because a system that only its builder understands is a risk to the client. Writing the operational manual meant recording how to deploy, secure, back up and restore the stack, along with the problems I hit during the build, so the client's IT team can keep it running when I am not there. To me, the manual is the part of the project that lets someone else trust and maintain what I built.
	
