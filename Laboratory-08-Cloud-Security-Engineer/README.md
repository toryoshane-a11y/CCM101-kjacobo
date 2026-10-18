# Laboratory Activity 8: Cloud Security Engineer

## Mission Overview
In this laboratory activity, I took the role of a Cloud Security Engineer securing a newly deployed server. I defined key security concepts, deployed an Nginx container named `secure-web-app` on port 8080, enabled the Uncomplicated Firewall (UFW) with a Default Deny policy, allowed SSH, and then opened only port 8080 for the web application.

## Objectives
- Understand the concept of the Attack Surface and the Principle of Least Privilege (PoLP).
- Perform a basic security audit of active network ports on a Linux server.
- Configure the Uncomplicated Firewall (UFW) with a Default Deny policy.
- Implement granular port management to selectively allow SSH and HTTP traffic.
- Document firewall rules and security best practices using Markdown.
- Continue expanding my professional GitHub Cloud Computing Portfolio.

## Commands Executed
| Command | Purpose |
|---|---|
| `docker run -d -p 8080:80 --name secure-web-app nginx` | Deployed the Nginx web server on port 8080. |
| `curl http://localhost:8080` | Verified that the web application responds. |
| `ufw allow ssh` | Allowed SSH (port 22) so remote administration continues to work. |
| `ufw default deny incoming` | Blocked all incoming traffic by default. |
| `ufw default allow outgoing` | Allowed all outgoing traffic. |
| `ufw enable` | Activated the firewall. |
| `ufw status verbose` | Checked that the firewall is active and showed the default policies. |
| `ufw allow 8080/tcp` | Allowed TCP traffic to the web application on port 8080. |
| `ufw status numbered` | Listed the firewall rules with numbers to confirm the new rule. |

## Skills Learned
- How the Principle of Least Privilege and a small attack surface reduce risk.
- How to configure UFW with a Default Deny policy.
- Why SSH must be allowed before the firewall is enabled.
- How to open a single port for a specific application.
- How to verify firewall rules with `ufw status`.
- How Docker's own network rules can affect how UFW behaves on a container host.
