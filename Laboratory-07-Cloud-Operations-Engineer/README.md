# Laboratory Activity 7: Cloud Operations Engineer

## Mission Overview
In this laboratory activity, I took the role of a Cloud Operations Engineer (SRE) preparing a client's web server for a surge in traffic. I established a baseline of the host server's memory, disk and CPU load, deployed an Nginx container named `client-website`, generated normal and failing web requests, and then used application logs and real-time container metrics to confirm that the infrastructure was healthy.

## Objectives
- Utilize native Linux command-line tools to monitor host CPU, Memory, and Disk capacity.
- Deploy a web container and track its real-time performance using Docker metrics.
- Generate web traffic and extract application access logs for analysis.
- Translate raw performance data into a readable technical report using Markdown.
- Continue expanding a professional GitHub Cloud Computing Portfolio.

## Monitoring Commands Executed
| Command | Purpose |
|---|---|
| `free -h` | Checked the total and used memory (RAM) of the host server. |
| `df -h` | Checked the disk capacity and usage of the host file systems. |
| `top` | Viewed running processes and live CPU load on the host. |
| `docker run -d -p 8080:80 --name client-website nginx` | Deployed the Nginx web server in the background, mapped to port 8080. |
| `docker ps` | Confirmed that the container was running. |
| `curl http://localhost:8080` | Sent a successful HTTP request to the web server (run three times). |
| `curl http://localhost:8080/hidden-admin-page` | Requested a page that does not exist to trigger a 404 error. |
| `docker logs client-website` | Retrieved the application access logs, showing the 200 and 404 requests. |
| `docker logs client-website 2>&1 \| grep 404` | Isolated the single log line containing the 404 error. |
| `docker stats` | Viewed live CPU, memory and network usage of the container. |

## Skills Learned
- How to establish a host performance baseline using `free`, `df` and `top`.
- How to deploy a web server container and test it with `curl`.
- How to read an access log and tell successful requests (200) from errors (404).
- How to use `grep` to filter a log for a specific status code.
- How to read real-time container metrics (CPU, memory, network I/O) with `docker stats`.
- How logs and metrics work together to show whether an application is healthy.
- How to document system health clearly using Markdown.
