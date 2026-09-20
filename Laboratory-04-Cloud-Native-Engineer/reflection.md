# Mission Reflection

**1. How does the boot time and setup process of a Docker container compare to installing an operating system on a Virtual Machine?**

Setting up a Docker container is dramatically faster than installing an operating 
system on a Virtual Machine. A VM requires installing a full guest operating system, 
which can take several minutes and requires manual configuration. A Docker container, 
on the other hand, starts in seconds because it shares the host machine's kernel and 
only needs to load the application and its dependencies rather than an entire OS.

**2. Why is port mapping (-p 8080:80) necessary when running a web server inside a container?**

Port mapping is necessary because the container runs in its own isolated network space, 
separate from the host machine. Without mapping port 8080 on the host to port 80 inside 
the container, external requests would never reach the Nginx server running inside the 
container. The `-p 8080:80` command creates a bridge so that traffic sent to the host's 
port 8080 is forwarded to port 80 inside the container.

**3. What happens to the data inside a container when you use the docker rm command?**

When the `docker rm` command is used, the container and any data stored inside it that 
was not saved to a persistent volume is permanently deleted. Containers are designed to 
be temporary and disposable, so any changes made inside the container's own filesystem 
are lost once it is removed, unless the data was explicitly stored in an external volume 
or bind mount.

**4. How do you think containerization changes the way software developers and IT operations teams work together (DevOps)?**

Containerization makes it easier for developers and IT operations teams to collaborate 
because it standardizes how applications are packaged and deployed. Since a container 
includes everything the application needs to run, developers can be confident that the 
software will behave the same way in production as it did in development. This reduces 
the "it works on my machine" problem and allows operations teams to deploy, scale, and 
manage applications more consistently and efficiently.

**5. How is your GitHub portfolio evolving?**

My GitHub portfolio continues to grow with each laboratory activity, now including 
documentation on Linux infrastructure, multi-cloud comparisons, and containerization 
using Docker. This mission added practical, hands-on evidence that I can deploy and 
manage containerized applications, which is a core skill for modern cloud-native 
engineering roles.
