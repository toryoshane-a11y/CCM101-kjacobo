# Mission Reflection

**1. How does writing a docker-compose.yml file make a cloud engineer's job easier compared to manually typing commands?**

Writing a Compose file puts the whole deployment into one saved file instead of several long commands that must be typed correctly each time. The file can be reused, shared with teammates, and stored in version control, so the same environment can be rebuilt exactly. One command starts every container, which saves time and reduces typing mistakes.

**2. What happens if you make an indentation error (like using a Tab instead of Spaces) in a YAML file?**

YAML uses indentation to show which settings belong to which service, and it does not accept Tabs for this. If a Tab or uneven spacing is used, Docker Compose reports a parsing error and refuses to start anything, because it cannot tell how the file is structured. This showed me that configuration files must be written carefully.

**3. Why did we use environment variables (like MYSQL_PASSWORD) in the Compose file?**

Environment variables pass settings such as the database name, user, and password into a container when it starts, without building them into the image. This keeps the same image reusable in different environments, and it lets the Nextcloud container and the MariaDB container use matching credentials. It is also a first step toward handling secrets properly in real deployments.

**4. How did it feel to deploy a fully functional enterprise cloud storage system (Nextcloud) in just a few minutes?**

It felt impressive. Installing and configuring a web server, PHP, and a database by hand would normally take hours, but here one file and one command brought up both tiers. Seeing the Nextcloud setup page appear in the browser made the idea of Infrastructure as Code feel real.

**5. How has your understanding of Cloud Computing evolved since Mission 1?**

In Mission 1, I thought of cloud computing mostly as renting servers online. Since then, I have investigated infrastructure, compared AWS, Azure, and GCP, worked with containers, deployed object storage, and now orchestrated a multi-tier application. I now see the cloud as automated, repeatable infrastructure that is defined in code and built from separate, cooperating services.
