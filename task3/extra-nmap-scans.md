# 10.  Additional Nmap Scans and Analysis

To perform five more advanced and diverse Nmap scans to gather deeper insights into the target system, and understand how each scan works and what it reveals.

## 1. UDP SCAN
A UDP scan is used to find open UDP ports on a target system. Unlike TCP scans, UDP doesn’t use handshakes, so it’s slower and harder to detect responses. But it’s important because many services like DNS, SNMP, and DHCP use UDP, and attackers might exploit open ones.

**Command used : nmap -sU target-ip**

Example : ``nmap -sU -T4 192.168.1.4``

![](https://github.com/deepthiii33/sapienceintern/blob/main/task3/screenshots/UDP_scan.png)

- The scan took a long time (~1138 seconds) because UDP scanning is slower than TCP.
- Nmap found 4 open UDP ports on the target:
- 53/udp – DNS (Domain Name System)
- 111/udp – RPCbind (used for remote procedure calls)
- 137/udp – NetBIOS Name Service (Windows networking)
- 2049/udp – NFS (Network File System, used for file sharing)
- 934 ports were marked closed (no service there).
- 62 ports were marked as open|filtered, meaning Nmap couldn’t tell if they're open or blocked.

There was a warning about hitting the retransmission limit on one port, which is common in UDP scans due to no acknowledgments.

--- 
# 2. FIN Scan (Stealth Scan)
A FIN Scan sends a TCP packet with only the FIN (Finish) flag set — like saying “I'm done,” without ever starting a connection. It is called a stealth scan because it doesn’t complete a full TCP handshake, making it harder to detect by firewalls or intrusion detection systems. It helps find open ports quietly.

**Command used: nmap -sF target-ip**

Example : ``nmaap -sF 192.168.1.4``

![](https://github.com/deepthiii33/sapienceintern/blob/main/task3/screenshots/FIN_scan.png)

- The scan shows many ports as "open|filtered", which means:
- Nmap couldn’t determine whether the port is open or just filtered by a firewall.
- This result is common in stealth scans, as they’re designed to be less detectable.
- 977 ports were confirmed as closed (responded with a reset packet).
- Detected services on various ports include: FTP (21), SSH (22), HTTP (80), MySQL (3306), PostgreSQL (5432), and many others

---

# 3. TCP SYN Scan 
A SYN scan sends a SYN (synchronize) packet to the target port (like starting a handshake).If the port replies with a SYN-ACK, it's open. If it replies with RST, it's closed.It doesn’t complete the handshake, which makes it stealthier than a full TCP connect scan.

**Command used: nmap -sS target-ip**

Example : ``nmap -sS 192.168.1.4``

![](https://github.com/deepthiii33/sapienceintern/blob/main/task3/screenshots/tcp_syn_scan.png)

- FIN scan sends TCP packets with the FIN flag to probe ports without starting a full connection.
- Ports responded as "open|filtered", meaning Nmap can't confirm if they are open or filtered by a firewall.
- Useful for bypassing some firewalls and IDS that don't log FIN packets.
- Host is up, and many common service ports responded (like FTP, SSH, HTTP, MySQL, VNC, etc.).

---
# 4. Aggressive Scan
An aggressive scan in nmap (using -A) is a scan that performs multiple checks at once to gather as much information as possible about a target. It’s faster but more likely to be detected because it’s quite thorough.Detects open ports.Identifies services running on those ports.
Performs OS detection to figure out what operating system the target is running.Performs version detection to determine the version of services.Runs a script scan to look for vulnerabilities.

**Command used : nmap -A target-ip**

Example : ``nmap -A 192.168.1.4``

![](https://github.com/deepthiii33/sapienceintern/blob/main/task3/screenshots/aggresive_scan.png)

It gives you a lot of detailed information about the target, all in one go. But it’s louder and easier to detect by security systems because it’s so aggressive.

---

# 5. IP Protocol Scan
It is used to determine which IP protocols (like TCP, UDP, ICMP, etc.) are supported by the target host.Scans for supported IP protocols: Rather than checking for open ports, it checks which protocols are open and allowed to communicate with the target. Doesn't check ports: It focuses on finding which higher-level protocols (like TCP, UDP, ICMP, IGMP, etc.) the target system is configured to support.

**Command used : nmap -sO target-ip**

Example : ``nmap -sO 192.168.1.4``

![](https://github.com/deepthiii33/sapienceintern/blob/main/task3/screenshots/IP_protocol_scan.png)

- Host is Online: The device at this address is reachable.
- Responds to Ping: It answers basic network "hello" messages.
- Accepts TCP: It can start regular internet connections.
- Accepts UDP: It can use faster, less reliable internet connections.
- Many Ports Unresponsive: Most network communication methods didn't get a reply.
- Looks Like Virtual Machine: The network card's information suggests it might be running inside a virtual environment (like VirtualBox).

---

**"Like this, we can explore additional commands and options by referencing the ``nmap --help`` documentation. This can help uncover more advanced features and functionalities that may be useful for future network scanning tasks. Understanding and utilizing these commands will enhance the efficiency and depth of our network assessments."**
