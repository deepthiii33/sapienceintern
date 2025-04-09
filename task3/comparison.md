# 9.  Comparison with Other Open Source Tools

To repeat the network scanning and enumeration tasks using other tools like **Masscan**, **Nikto**, and **Zenmap**, and compare their outputs with Nmap results.

## Masscan
Masscan is a fast tool used to scan open ports on devices. It works by sending special SYN packets (used to start a connection) and can scan many IP addresses and ports at once. While it gives results similar to Nmap, it's much faster because it sends and receives data asynchronously, meaning it doesn't wait for a response before moving to the next target. Tools like scanrand and ZMap work in a similar way.

Command used: **masscan -p ports  (target IP range) --rate=(packets per second)**

Example: ``masscan -p 1-65535 192.168.1.4 --rate=1000``

![](https://github.com/deepthiii33/sapienceintern/blob/main/task3/screenshots/masscan_diff.png)

- -p 1-65535 → Scans all 65,535 TCP ports (from port 1 to 65535).
- 192.168.1.4 → Targets   IP address we  want to scan.
- --rate=1000 → Sends 1000 packets per second, controlling the speed of the scan to avoid overwhelming the network or triggering defenses.

command checks which ports are open on the target IP (192.168.1.4) very efficiently and quickly.

#### Masscan vs Nmap: Output Comparison

1. Speed:
   - Masscan completed the scan very quickly due to its high rate (--rate=10000), scanning all 65,535 ports.
   - Nmap took longer but provided detailed service information.
2. Port Detection:
   - Both tools discovered many of the same open ports,but Masscan detected additional high-numbered ports (e.g., 33289, 38194) which may be missed or filtered in Nmap by default without specific flags.
3. Service Identification:
   - Nmap identified the services running on the ports (like:  http on port 80, ssh on port 22, etc.).
   - But Masscan does not show service names—only open ports.
4. usage:
   - Masscan is fast, large-scale scans, especially when time is a constraint.
   - nmap is for depth scanning, including version detection and vulnerability checks.

- Masscan listed ports like 33289, 38194, and 60202 as open.
- Nmap confirmed the same ports and even marked unknown ones as such (unknown service).

**Masscan is faster for finding open ports, while Nmap gives more detailed information about those ports and the services running on them.**

----

## Nikto

Nikto is a free software command-line vulnerability scanner that scans web servers for dangerous files or CGIs, outdated server software and other problems.

Command used : **nikto -h <http://target-ip>

Example : ``nikto -h http://192.168.1.4``

![](https://github.com/deepthiii33/sapienceintern/blob/main/task3/screenshots/nikto.png)

Some key points from my nikto scan output:

- Old Software: The website is using an old version of Apache and PHP, which can have security holes.
- Directory Browsing On: Some folders (like /doc/, /icons/, /phpMyAdmin/) can be opened and browsed by anyone — not safe!
- Sensitive File Found: A file called phpinfo.php was found — it shows detailed info about the server that hackers can use.
- Possible Password Leak: A file named wp-config.php was found — it may contain login info for the database.
- Server Allows TRACE Requests: This could let hackers trick the website into giving up private info (XST attack).
- Missing Security Settings: Some important web security settings (headers) are not turned on — like blocking clickjacking attacks.
- Leak of Version Info: The site shows what software it's using — good info for attackers.

The Nikto scan identified several potential web server vulnerabilities, including outdated Apache version, exposure of sensitive files (like phpinfo.php and wp-config.php), and misconfigurations such as missing security headers. These issues may allow attackers to gather sensitive information or exploit known vulnerabilities. It is recommended to update the server software, disable unnecessary files, and apply proper HTTP security headers to reduce risk.

---

## Zenmap

 Provides a graphical interface for creating, saving, and visualizing Nmap scans. Performed scans using Zenmap to visualize host topology, scan summaries, and port/service maps.elped better understand large scans with graphical representation of data. Useful for reporting and quick reviews.

**Usage:** Enter the target IP in Zenmap’s interface, select a scan type, and run the command automatically through the GUI.

![](https://github.com/deepthiii33/sapienceintern/blob/main/task3/screenshots/zenmap_os_scan.png)

This scan shows Zenmap identifying the target host's IP address, discovering open ports, and performing service detection as part of an intense scan profile.

![](https://github.com/deepthiii33/sapienceintern/blob/main/task3/screenshots/zenmap_hostdetails_services.png)

This  summarizes key host information such as status, uptime, MAC address, and the detected operating system version.

![](https://github.com/deepthiii33/sapienceintern/blob/main/task3/screenshots/zenmap_port_scan_details.png)

This view displays detailed information about each open port, including the protocol, state, service running, and version details discovered during the scan.





  - **In this task, we used Nmap and Zenmap to scan a target system and gather important information like open ports, running services, and the operating system. These details help understand the network better and check for any possible security issues.**
  - **Nmap works through the command line and is good for users who are comfortable with commands. Zenmap is the same tool but with a graphical interface, which makes it easier to use and better for beginners. Both tools gave similar results, but Zenmap was more visual and user-friendly, while Nmap gave more control and flexibility.**


---








