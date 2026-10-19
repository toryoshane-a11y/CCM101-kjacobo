# Mission Reflection

**1. Why is automation critical when managing hundreds of cloud servers?**

Typing commands by hand on hundreds of servers would be slow, and every repeated step is a chance for a mistake. A script does the same task the same way every time, and a scheduler like cron runs it on time without anyone remembering. Automation lets a small team manage a large number of servers reliably.

**2. What are the potential dangers of automation? (What happens if there is a destructive typo inside a script that is scheduled to run on 1,000 servers?)**

Automation repeats mistakes as efficiently as it repeats correct work. A destructive typo, such as deleting the wrong folder, would run on all 1,000 servers at once and could cause a massive outage or data loss before anyone notices. This is why scripts should be tested on one machine first, and why backups and careful review matter.

**3. How did writing a Bash script differ from creating a Docker Compose YAML file (Mission 6)?**

A Bash script is a list of commands that run step by step, so I describe how to do the task. A Docker Compose file describes the end result I want, such as which containers should exist, and Docker works out the steps. Bash gave me more control and flexibility, while YAML was shorter but strict about indentation.

**4. Review your entire GitHub repository from Laboratory 1 to Laboratory 9. How has your understanding of Cloud Computing transformed over the course of this semester?**

At the start, I thought of the cloud mainly as someone else's computers. Across the labs I inspected servers, compared AWS, Azure and GCP, deployed containers and object storage, used Docker Compose, monitored systems, secured them with a firewall, and automated backups. Now I see the cloud as a set of services that can be built, secured and run with code.

**5. Which role did you enjoy the most (Infrastructure Engineer, Cloud-Native Engineer, Security Engineer, etc.) and why?**

I enjoyed the Cloud-Native Engineer role the most because seeing a working web server start in seconds with one command was satisfying. Solving problems along the way, like the MinIO image error, taught me how real troubleshooting works.
