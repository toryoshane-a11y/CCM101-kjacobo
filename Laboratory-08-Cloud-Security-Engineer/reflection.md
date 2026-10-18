# Mission Reflection

**1. How does a host-based firewall protect a server even if the physical network perimeter is breached?**

A host-based firewall runs on the server itself, so it keeps filtering traffic even if an attacker gets past the network's outer defenses. Every connection still has to match a rule on the machine before it reaches an application. This is the idea behind defense in depth, where one failed layer does not expose everything.

**2. Why is managing open network ports critical to reducing a server's attack surface?**

Each open port is a doorway to a running service, and every service may contain a weakness. Closing the ports that are not needed leaves attackers fewer places to probe. In this lab, only SSH and port 8080 were opened, so everything else stayed blocked.

**3. In a real enterprise environment, why is it dangerous to leave a database port (like 3306 for MySQL) open to the public internet?**

Anyone on the internet could then try to guess passwords or exploit known flaws in the database, which holds the most valuable data. Automated scanners find open database ports within minutes. A database should only be reachable from the application server that needs it.

**4. How did completing this mission change your perspective on how easily a server can be compromised?**

I realized that a server with no firewall is exposed by default, and that it takes only a few commands to change that. I also learned that order matters, because enabling the firewall before allowing SSH could lock an administrator out. Security takes careful, deliberate steps.

**5. How does your GitHub portfolio currently look with eight completed missions?**

My portfolio now has eight organized laboratory folders, each with documentation, screenshots and a reflection. It shows a clear progression from basic Linux commands to infrastructure, containers, monitoring and security. The commit history also shows my work over time.
