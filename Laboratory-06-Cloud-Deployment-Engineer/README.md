# Laboratory Activity 6: Cloud Deployment Engineer

## Mission Overview
In this laboratory activity, I deployed a two-tier private cloud storage system using Docker Compose. I documented the multi-tier architecture, wrote a `docker-compose.yml` file that defines a MariaDB database container and a Nextcloud web container, deployed both with a single command, accessed the Nextcloud setup page through the browser, and then shut the whole stack down cleanly.

## Objectives
- Explain the concept of a multi-tier application architecture.
- Understand the purpose and structure of a docker-compose.yml file.
- Use a Linux command-line text editor (nano) to create configuration files.
- Deploy a multi-container application (Nextcloud + Database) using Docker Compose.
- Document deployment procedures and Infrastructure as Code (IaC) principles using Markdown.
- Continue expanding my professional GitHub Cloud Computing Portfolio.

## Commands Executed
| Command | Purpose |
|---|---|
| `mkdir nextcloud-deployment` | Created a project directory for the deployment. |
| `cd nextcloud-deployment` | Moved into the project directory. |
| `nano docker-compose.yml` | Opened the nano editor to write the Compose file. |
| `docker-compose up -d` | Pulled the images and started both containers in the background. |
| `docker-compose ps` | Verified that both containers were running. |
| `docker-compose down` | Stopped and removed the containers and the network. |

## Skills Learned
- How a two-tier architecture separates the web tier from the database tier.
- How to read and write a `docker-compose.yml` file, including the `services:` block.
- How containers find each other by service name on a Compose network.
- How to deploy and tear down a multi-container application with one command each.
- How to write YAML carefully, since indentation matters.
- How Infrastructure as Code makes deployments repeatable.
