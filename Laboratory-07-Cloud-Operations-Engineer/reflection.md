# Mission Reflection

**1. Why is it important to check the host server's resources even if your containers are running perfectly?**

Containers share the host's CPU, memory and disk. A container can look perfectly healthy while the host underneath is running out of RAM or storage, and when that happens every container on it can slow down or crash. Checking the host shows problems before they reach the application.

**2. If a user complains that they cannot log into a web application, how would the docker logs command help you solve the problem?**

The logs show which requests reached the application and what status codes it returned. I could find the user's request and see whether it failed with an error such as 401, 403 or 500, and read any error messages the application printed. That points me to the real cause, such as a failed database connection or a blocked request, instead of guessing.

**3. What is the difference between monitoring logs (Checkpoint 4) and monitoring metrics (Checkpoint 5)?**

Logs record individual events, such as who requested which page and whether it succeeded, so they explain what happened and why. Metrics are numbers measured over time, such as CPU percentage and memory usage, so they show how the system is performing. Metrics tell me that something is wrong, and logs help me find the reason.

**4. How do you think large enterprise companies monitor thousands of containers at the same time?**

Nobody can watch thousands of containers by hand, so companies use automated tools. Prometheus collects metrics from every container and stores them, and Grafana turns that data into dashboards and alerts. Log collection tools gather all the logs in one searchable place, and alerts notify the team when a value crosses a limit.

**5. How has your ability to troubleshoot Linux environments improved?**

I am more comfortable now. I can check host resources, read logs, filter output with grep, and understand live metrics instead of guessing. In earlier labs I struggled with permission errors and git push problems, and working through them taught me to read error messages carefully and test one fix at a time.
