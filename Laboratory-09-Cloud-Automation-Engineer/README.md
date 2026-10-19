# Laboratory Activity 9: Cloud Automation Engineer

## Mission Overview
In this laboratory activity, I took the role of a Cloud Automation Engineer and removed the human element from a backup process. I defined key automation concepts, created a dummy application folder, wrote a Bash script that compresses it into a timestamped backup, made the script executable with chmod, tested it, and scheduled it with a cron job to run every night at 2:00 AM.

## Objectives
- Understand the fundamental syntax of a Bash shell script, including variables and basic commands.
- Use a command-line text editor (nano) to write and save executable scripts.
- Modify Linux file permissions using the chmod command.
- Understand task scheduling and the syntax of a Linux crontab.
- Document automation code and Cron job configurations using Markdown.
- Complete the final chapter of my GitHub Cloud Computing Portfolio.

## Commands Executed
| Command | Purpose |
|---|---|
| `mkdir app-data` | Created a dummy folder to represent the client's data. |
| `echo "This is critical client data." > app-data/data.txt` | Created a test file inside the folder. |
| `nano backup.sh` | Opened the nano editor to write the backup script. |
| `./backup.sh` | Ran the script (first it failed with Permission denied, then it succeeded). |
| `chmod +x backup.sh` | Made the script executable. |
| `ls -l backups/` | Verified that the compressed `.tar.gz` backup was created. |
| `crontab -l` | Listed the current cron jobs. |
| `env EDITOR=nano crontab -e` | Opened the cron table in nano to add a schedule. |

## Skills Learned
- How to write a Bash script that uses variables, command substitution and comments.
- How the shebang line tells the system which interpreter runs a script.
- How to read and change file permissions with chmod.
- How to create a compressed, timestamped backup with tar.
- How to read a crontab expression and schedule a job with cron.
- How automation reduces human error in routine operations.
