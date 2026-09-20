# Laboratory Activity 4: Cloud-Native Engineer

## Mission Overview
In this laboratory activity, I explored the shift from traditional virtualization to 
containerization. I researched the key differences between Virtual Machines and 
Containers, then used Docker inside a KillerCoda Playground to pull, run, and manage a 
live Nginx web server container, simulating the role of a Cloud-Native Engineer.

## Objectives
- Differentiate between traditional Virtual Machines (VMs) and Containers.
- Access a Docker-enabled cloud environment using KillerCoda.
- Execute fundamental Docker CLI commands.
- Pull, run, manage, and terminate a containerized application (Nginx).
- Create professional technical documentation of container operations using Markdown.
- Continue developing a well-organized GitHub Cloud Computing Portfolio.

## Docker Commands Executed
| Command | Purpose |
|---|---|
| `docker --version` | Verified Docker was installed. |
| `docker info` | Checked the current status of the Docker environment. |
| `docker pull nginx` | Downloaded the official Nginx image from Docker Hub. |
| `docker run -d -p 8080:80 --name my-nginx nginx` | Ran the Nginx container in detached mode, mapping port 8080 to container port 80. |
| `curl http://localhost:8080` | Verified the Nginx web server was running and accessible. |
| `docker ps` | Listed currently running containers. |
| `docker stop my-nginx` | Stopped the running container. |
| `docker ps -a` | Verified the container had stopped. |
| `docker rm my-nginx` | Removed the stopped container completely. |

## Skills Learned
- How to verify Docker installation and check its running status.
- How to pull container images from Docker Hub.
- How to run a container in detached mode and map host ports to container ports.
- How to verify a running service using `curl`.
- How to manage the full lifecycle of a container: listing, stopping, and removing it.
- How containerization differs architecturally from traditional virtual machines.

## Challenges Encountered
- Had to get familiar with Docker's command syntax, especially port mapping (`-p`) and 
  detached mode (`-d`), since these were new commands compared to previous labs.
- Needed to understand the difference between `docker ps` (running containers only) and 
  `docker ps -a` (all containers, including stopped ones) to properly verify each step 
  of the container lifecycle.
