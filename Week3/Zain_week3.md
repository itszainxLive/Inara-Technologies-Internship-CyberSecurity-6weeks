<img src="media/media/image1.png" style="width:5.76597in;height:1.75694in" />

1.  **<u>How containers differ from virtual machines; isolation and the shared kernel:-</u>**

    A virtual machine has its own full operating system inside it, so it is big and takes time to start. A container does not have its own operating system it uses the same one as the host computer, so it is small and starts fast. Containers stay separate from each other using special Linux features that keep their files, processes, and network apart.

    <img src="media/media/image2.png" style="width:4.69792in;height:1.34375in" />

- containers use the same kernel as the host, not their own.

2.  **<u>Docker engine and client; images, registries, and containers:-</u>**

    The Docker Engine is the background program that actually runs containers. The Docker Client is the tool we type commands into to talk to the Engine. An image is like a saved copy of everything needed to run an app. A registry is an online place, like Docker Hub, where images are stored and shared. A container is what you get when you actually run an image.

    <img src="media/media/image3.png" style="width:5.76042in;height:0.76597in" />

- It lists all the images you currently have downloaded.

  <img src="media/media/image4.png" style="width:5.7625in;height:3.38542in" />

- It shows details about the Docker Engine running on your computer.

  <img src="media/media/image5.png" style="width:5.76389in;height:0.52708in" />

- This downloads an image from a registry onto your computer.

  <img src="media/media/image6.png" style="width:5.76389in;height:0.54306in" />

- This lists all containers on your system both running and stopped.

  <img src="media/media/image7.png" style="width:5.76597in;height:1.97569in" />

- It shows whether the Docker Engine is active and running.

  <img src="media/media/image8.png" style="width:5.75972in;height:0.53472in" />

- A registry is an online storage location where images are kept and shared. This command downloads an image from that registry onto your computer.

3.  **<u>Container lifecycle — run, stop, inspect, logs, exec:-</u>**

    **Run:**

    <img src="media/media/image9.png" style="width:5.76319in;height:2.07778in" />

- It creates and starts a new container named test container from the nginx image.

  **Stop:**

  <img src="media/media/image10.png" style="width:5.76528in;height:0.96806in" />

- It stops the running container without deleting it.

  **Inspect:**

  <img src="media/media/image11.png" style="width:5.76458in;height:2.6125in" />

  <img src="media/media/image12.png" style="width:5.7625in;height:2.21389in" />

- It shows detailed information about the container in JSON format its network settings, mounted volumes, environment variables, and configuration.

  **Logs :**

  <img src="media/media/image13.png" style="width:5.76181in;height:3.21597in" />

- It shows the output messages that the application inside the container has printed.

  **Exec :**

  <img src="media/media/image14.png" style="width:3.65625in;height:0.92708in" />

- This opens an interactive terminal session inside the running container, letting you type commands directly as if you were inside that container's own system.

4.  **<u>Volumes and bind mounts; networking in Docker:-</u>**

    **Volume creation:-**

    <img src="media/media/image15.png" style="width:5.76597in;height:2.04375in" />

- This starts a new container and attaches the volume to its data folder.

  <img src="media/media/image16.png" style="width:5.7625in;height:3.00069in" />

- A bind mount directly links a folder from your host computer.

  <img src="media/media/image17.png" style="width:5.75903in;height:2.33472in" />

- This creates a custom network and runs a container on it — user-defined networks let containers talk to each other by name, which the default bridge network doesn't easily allow.

  **Practical Task: <u>Run a containerized service, inspect its network, exec into it, and mount a volume — then verify isolation:-</u>**

  <img src="media/media/image18.png" style="width:5.69792in;height:3.62083in" />

  <img src="media/media/image19.png" style="width:5.76806in;height:3.82292in" />

  <img src="media/media/image20.png" style="width:5.76458in;height:1.61111in" />

- First I started a small web service inside a container and gave it its own storage space. Then I checked that it was running and that the website inside it was replying. After that, I looked at the container's network and saw it had its own IP address, different from my computer. Next, I went inside the container and checked its name and network, which were separate from my real computer's name and network. I also checked where the container's saved data was actually being stored on my computer. Finally, I compared the container's name and network with my real computer's name and network outside the container, and they were different, which shows the container is kept isolated from the host.

  <img src="media/media/image21.png" style="width:5.76667in;height:1.88958in" />

1.  **<u>Docker Compose defining and running multi-container applications:-</u>**

- I wrote a docker-compose.yml file that starts two containers together an nginx web server and a redis database —with one single command. I ran into a port conflict from an old leftover container, fixed it by removing that container, and then successfully started both services. I confirmed it worked by visiting the web server and seeing the nginx welcome page.

  <img src="media/media/image22.png" style="width:5.76042in;height:3.31875in" />

  <img src="media/media/image23.png" style="width:5.76389in;height:3.34653in" />

  <img src="media/media/image24.png" style="width:5.76667in;height:2.42778in" />

2.  **<u>Building images with Dockerfiles — FROM, COPY, RUN, CMD; layering and caching:-</u>**

    <img src="media/media/image25.png" style="width:3.94653in;height:2.24861in" />

    <img src="media/media/image26.png" style="width:5.76458in;height:3.07639in" />

- I made a Dockerfile, which is like a recipe for building my own custom container image. It starts from the nginx image, then copies my own HTML file into it, and tells it to run nginx when it starts. I built the image using the Dockerfile, then ran a container from it on a different port (8081). When I checked the page, it showed my own custom message instead of the default nginx page, which proved that my custom image was working correctly.

3.  **<u>Container security basics — running as non-root, read-only file systems, capability dropping:-</u>**

    <img src="media/media/image27.png" style="width:5.76458in;height:3.13889in" />

- I tested three ways to make containers safer: running them as a regular user instead of root less power if hacked, making the filesystem read-only so nothing can be changed or written inside, and removing all extra Linux capabilities and only adding back the one that was actually needed. All three reduce the damage an attacker could do if they got inside a container.

4.  **<u>Image scanning and managing secrets in containers:-</u>**

    <img src="media/media/image28.png" style="width:5.76389in;height:1.93958in" />

- We put the password in a secret file, pass it to the container as a secret, and read it inside the container when needed. After that, we delete the original file.

**Practical Task:**

**<u>Write a docker-compose.yml with two services; build a custom image that runs as non-root with a read-only filesystem:-</u>**

<img src="media/media/image29.png" style="width:5.76111in;height:3.40208in" />

<img src="media/media/image30.png" style="width:5.76181in;height:3.66875in" />

- In this practical, we created a Docker Compose file with two services: an app service and a redis service. We built a custom Docker image for the app and configured it to run as a non-root user for better security. We also made its filesystem read-only, so the container cannot change or create files inside it. Finally, we built and ran the services using Docker Compose and verified that the app was running as a non-root user and had a read-only filesystem.

  <img src="media/media/image31.png" style="width:5.76319in;height:1.48403in" />

1.  **<u>Reducing the attack surface — removing unused packages and services:-</u>**

    <img src="media/media/image32.png" style="width:5.11181in;height:1.24861in" />

- It shows a full list of every piece of software currently installed on the computer.

  <img src="media/media/image33.png" style="width:5.34792in;height:2.80625in" />

- It shows every service that automatically starts when the computer turns on.

  <img src="media/media/image34.png" style="width:5.76111in;height:2.10833in" />

- It completely removes a package.stops a service.

2.  **<u>Auditing installed software; reviewing listening ports and open files:-</u>**

    <img src="media/media/image35.png" style="width:5.76736in;height:1.92014in" />

- It counts the total number of installed packages and which installed packages have newer versions available.

  <img src="media/media/image36.png" style="width:5.76667in;height:2.22986in" />

- It shows every port that is open and waiting for connection and all files and network connections currently being used by running programs.

  <img src="media/media/image37.png" style="width:5.76736in;height:1.03889in" />

- It shows exactly which program is using one specific port, here port 22 which is used for SSH.

3.  **<u>Access control lists (ACLs) with setfacl/getfacl:-</u>**

    <img src="media/media/image38.png" style="width:5.76181in;height:5.02986in" />

    First I installed the tools needed for ACLs, then made a test file to practice on. I gave a specific user extra read and write permission on the file, which is something normal permissions cannot do alone. Then I checked the file to see that permission was really added. After that, I removed that one specific permission, and also removed all extra ACL rules at once to bring the file back to normal. Finally, I checked the file again to confirm everything was clean and back to its simple, default permissions.

4.  **<u>CIS Benchmark awareness — what Level 1 controls look like in practice:-</u>**

    I installed a tool called Lynis, which checks a computer against common security best practices, similar to what CIS Benchmarks recommend. Then I ran a full system audit with it, which looks at things like passwords, file permissions, running services, and installed software, and gives a report showing what is already secure and what needs to be fixed. CIS Level 1 controls are the basic, safe security settings that should work on almost any system without breaking normal use, like requiring strong passwords, turning off unused services, and locking down file permissions — the Lynis report helps show which of these basic controls are already in place and which ones are missing.

    <img src="media/media/image39.png" style="width:5.76528in;height:3.60278in" />

    <img src="media/media/image40.png" style="width:5.7625in;height:3.17986in" />

    <img src="media/media/image41.png" style="width:5.76389in;height:1.80625in" />

    <img src="media/media/image42.png" style="width:5.76597in;height:2.57292in" />

**Practical Task:**

**<u>Audit a practice host against CIS Level 1 controls: identify and remediate at least 5 findings</u>**

<img src="media/media/image43.png" style="width:5.26806in;height:3.44306in" />

<img src="media/media/image44.png" style="width:5.7625in;height:4.14583in" />

<img src="media/media/image45.png" style="width:5.75903in;height:1.90764in" />

I ran a security scan using Lynis, which checks the computer against common CIS Level 1 security controls and gives a list of warnings. From that report, I picked five findings and fixed them one by one: I installed a tool to force stronger passwords, turned off an unused service (cups) that wasn't needed, stopped direct root login through SSH for better security, searched for files that anyone could edit which is a risk, and turned on automatic security updates so the system stays patched. Finally, I ran the scan again to confirm the fixes actually improved the system's security score.

<img src="media/media/image46.png" style="width:5.76389in;height:1.53194in" />

1.  **<u>Input validation, least privilege for service accounts, secrets handling in scripts and config:-</u>**

    <img src="media/media/image47.png" style="width:5.75694in;height:1.66875in" />

    I wrote a small script that checks user input and only allows letters, which is an example of input validation — it stops bad or unexpected data from causing problems. Then I checked which user account I'm running as, showing why apps should run with the least privilege possible (a normal limited account, not root/admin) so that if something goes wrong, the damage is limited. Finally, I searched a script for the word "password" to show why secrets like passwords should never be written directly in code or config files, since anyone reading the file could see them — they should be stored safely somewhere else, like environment variables or a secrets manager.

2.  **<u>Kubernetes RBAC, network policies, and pod security standards (concept level):-</u>**

    <img src="media/media/image48.png" style="width:4.51389in;height:3.06042in" />

    <img src="media/media/image49.png" style="width:4.49375in;height:3.70486in" />

    I checked if Kubernetes' command tool was available, then created three sample configuration files to show key security concepts. The first file was an RBAC role that only allows viewing pods, not changing them, showing how Kubernetes controls who can do what. The second file was a network policy that blocks all incoming traffic by default, showing how Kubernetes can control which pods are allowed to talk to each other. The third file was a pod configuration that forces the pod to run as a normal user instead of root and blocks it from gaining extra permissions, showing how pod security standards keep containers safe even if we don't have a live Kubernetes cluster to test on directly.

3.  **<u>Secrets handling in Kubernetes vs environment variables:</u>**

    <img src="media/media/image50.png" style="width:4.40278in;height:3.14167in" />

    <img src="media/media/image51.png" style="width:4.3125in;height:1.35417in" />

    I first set a password as an environment variable, which is a common but simple way to pass secrets into an app it works, but anyone who can see the process list or environment might read it. Then I created a Kubernetes Secret file, which stores the same kind of sensitive data but encodes it and keeps it as a separate, managed object instead of sitting in plain text in a script; Kubernetes Secrets can also be restricted using RBAC so only certain pods or users can access them. Finally, I showed how the encoding works using base64, which is not real encryption but just a way to hide the value from a normal glance proving that Kubernetes Secrets are a bit safer and more organized than plain environment variables, but still need extra protection like encryption at rest for real security.

    **Practical Task:**

    **<u>Review a sample application config and Kubernetes manifest for security misconfigurations and document fixes</u>**

    <img src="media/media/image52.png" style="width:5.45486in;height:4.86389in" />

    I created a sample application config and a Kubernetes pod file that both had common security mistakes on purpose, like storing a password in plain text, allowing debug mode, allowing any host to connect, running as a privileged container, and running as the root user. Then I reviewed both files and wrote down six findings along with their fixes — mainly moving passwords into proper secrets instead of plain text, turning off debug mode, restricting allowed hosts, and making the container run with normal, limited permissions instead of full root access. This matches how real security reviews work: find risky settings, then document exactly how to fix them.

    <img src="media/media/image53.png" style="width:5.7625in;height:3.35625in" />

    <img src="media/media/image54.png" style="width:5.76389in;height:1.10694in" />

    <img src="media/media/image55.png" style="width:5.76181in;height:1.58056in" />

<!-- -->

1.  **<u>Metrics collection with Prometheus; visualising data in Grafana (concept level):-</u>**

    **<u>Prometheus:-</u>**

    <img src="media/media/image56.png" style="width:5.76111in;height:3.65486in" />

    <img src="media/media/image57.png" style="width:5.76181in;height:2.07431in" />

    <img src="media/media/image58.png" style="width:5.20833in;height:0.85417in" />

    I downloaded the actual Prometheus program file from its official website. After that, I unpacked the downloaded file into a folder so I could get to the real program inside it, and moved into that folder. Finally, I listed the files inside to confirm the Prometheus program and its settings file were really there and ready to use.

    **<u>Grafana:-</u>**

    <img src="media/media/image59.png" style="width:5.76181in;height:2.77153in" />

    I started the Grafana service so it begins running, and also set it to start automatically every time the computer turns on. Then I checked that Grafana was really working by asking its web address for a reply, and getting a response back confirmed it was running successfully.

2.  **<u>Centralising logs — log aggregation concepts, searching, filtering, retention:-</u>**

    <img src="media/media/image60.png" style="width:5.76597in;height:2.89722in" />

    <img src="media/media/image61.png" style="width:5.76597in;height:3.31806in" />

    <img src="media/media/image62.png" style="width:5.76458in;height:2.50278in" />

    I checked which log files exist on the system, then used journalctl to see the last 20 log entries collected from all services in one place, which is what centralising logs means — everything in one tool instead of many separate files. I searched through those logs for the word "error" to show how filtering and searching works, then filtered logs down to just one specific service (Grafana) to find relevant messages without noise from everything else. Finally, I checked how much disk space the stored logs were using and then set a size limit, which shows how retention works — deciding how long logs are kept before old ones get automatically deleted to save space.

3.  **<u>Health checks, endpoint monitoring, and on-call basics:-</u>**

    <img src="media/media/image63.png" style="width:5.76667in;height:2.31042in" />

    <img src="media/media/image64.png" style="width:5.7625in;height:3.62708in" />

    I checked if a website and a service were alive by sending them a quick request and looking at their reply — this is a basic health check, where a good reply like "200 OK" or "healthy" means the service is working fine. Then I built a small script that automatically checks a website's address and prints whether it is up or down, which is the core idea behind endpoint monitoring, where a system keeps watching addresses automatically instead of a person checking by hand. Finally, the alert message the script prints when something is down represents on-call basics — in a real company, this kind of alert would actually notify whichever engineer is on duty that day, so problems get noticed and fixed quickly instead of staying broken unnoticed.

    **Capstone Practical Task:**

    **<u>Harden a containerized service end-to-end — iptables rules, SSH key auth, non-root container, log verification, and a cron-scheduled audit script:-</u>**

    **Part 1: Container ko non-root user ke sath run karna:**

    <img src="media/media/image65.png" style="width:5.76111in;height:2.69514in" />

    <img src="media/media/image66.png" style="width:5.76181in;height:0.66389in" />

    This confirms the container is running and shows it's using a normal (non-root) user ID.

    **Part 2: iptables rules — service ko harden karna:**

    <img src="media/media/image67.png" style="width:5.75972in;height:1.92639in" />

    <img src="media/media/image68.png" style="width:5.76458in;height:1.93611in" />

    This confirms the containerized service is still reachable after applying the firewall rules, since we specifically allowed its port.

    **Part 3: SSH key authentication setup karna:**

    <img src="media/media/image69.png" style="width:5.76736in;height:3.64653in" />

    <img src="media/media/image70.png" style="width:5.76667in;height:3.42222in" />

    I generated a new pair of keys — a private key that stays secret on my computer and a public key that gets shared with the server — used for logging in without a password. I added the public key to the list of allowed keys and set safe permissions on that file so only I could access it. Then I turned off password-based login in the SSH settings and restarted the SSH service, which forces everyone to use a key instead of a password, since keys are much harder to guess or attack than passwords. Finally, I tested logging in using the private key to confirm that key-based authentication was actually working.

    **Part 4: Log verification — containerized service ke logs check karna:**

    <img src="media/media/image71.png" style="width:5.75972in;height:3.47986in" />

    <img src="media/media/image72.png" style="width:5.75972in;height:3.20486in" />

    I checked the logs coming from inside the containerized service to see what it's been doing and whether there are any errors, then looked at just the most recent 20 lines to keep it focused. I also checked the Docker service's own system logs to see how the container has been managed at a higher level. Finally, I checked the SSH logs specifically for login attempts, filtering for "accepted" or "failed" to verify whether our new key-based login is working and being recorded properly — this kind of log verification is important because logs are the main way to confirm security changes are actually working and to notice if anyone tries to break in.

    **Part 5: Cron-scheduled audit script:**

    <img src="media/media/image73.png" style="width:5.76458in;height:3.45in" />

    <img src="media/media/image74.png" style="width:5.7625in;height:2.76042in" />

    <img src="media/media/image75.png" style="width:5.76042in;height:2.97569in" />

    I wrote a script that automatically checks all the security things we set up — whether the container is running, what user it's running as, the firewall rules, whether SSH password login is turned off, and any recent failed login attempts — and saves all of this into one report file with a timestamp. I ran the script once by hand to confirm it worked and showed the report it created. Then I scheduled this same script to run automatically every hour using cron, which is a built-in tool for running tasks on a timer without anyone needing to start them manually. Finally, I checked the list of scheduled cron jobs to confirm the audit script was properly set to keep running on its own every hour, just like real automated security audits work in companies.
