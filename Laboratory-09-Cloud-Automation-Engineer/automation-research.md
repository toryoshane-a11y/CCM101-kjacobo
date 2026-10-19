# Automation Research

## Bash Script
A Bash script is a text file containing a list of Linux commands that the Bash shell runs in order, so a task can be repeated without typing each command by hand. The first line, `#!/bin/bash`, is called the shebang, and it tells the system which program (here, Bash) should interpret the rest of the file. Without it, the system may not know how to run the script.

## Variables
A variable stores a value under a name, such as `BACKUP_DIR="backups"`, so the script can reuse it by writing `$BACKUP_DIR`. Programmers use variables because the value is typed only once, which reduces typing mistakes and makes the script easy to change later. If the backup folder changes, only one line needs editing instead of every place the path appears.

## Cron Job
A cron job is a task that the Linux cron scheduler runs automatically at a set time or interval, based on a schedule written in the crontab file. It is essential for cloud operations because routine work such as backups, log cleanup and health checks must happen on time without anyone remembering to do them. This removes human error and lets one engineer manage many servers.
