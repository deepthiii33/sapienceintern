#  5. Banner Grabbing
 - To collect banners from open ports to identify services and possible vulnerabilities.
 - Command used : nmap --script=banner <target-ip>
 - --script=banner --> used in nmap to run a script that attempts to grab banners from services running on open ports.
 - identifying the  versions of services and  misconfigurations or outdated software.

![](https://github.com/deepthiii33/sapienceintern/blob/main/task3/screenshots/banner%20grabbing.png)

Banner grabbing is a technique used to gain information about a service running on an open port.It  includes details like the software name, version, operating system—all of which can help in vulnerability assessment.

#### From my output we can get information like :

- **FTP (port 21)** --> Banner: 220 (vsFTPd 2.3.4)
- Vulnerability: Known for a backdoor vulnerability in certain versions.
---
- **SSH (port 22)** --> Banner: SSH-2.0-OpenSSH_4.7p1 Debian-8ubuntu1
- Vulnerability: Outdated version, may be vulnerable to several known exploits.

- **SMTP (port 25)** --> Banner: 220 metasploitable.localdomain ESMTP Postfix (Ubuntu)
- Information leakage like Revealing mail server and hostname.

---

- **Shell (port 1524)** --> Banner: root@metasploitable:/#
- Indicates unauthenticated root shell is exposed—critical vulnerability!

---

- **FTP (port 2121)** --> Banner: 220 ProFTPD 1.3.1 Server (Debian)
- Vulnerability: Older versions of ProFTPD have known remote exploit vulnerabilities.

---

- **MySQL (port 3306)** --> Banner contains MySQL version: 5.0.51a-3ubuntu5

--- 
- **RC (port 6667)** --> Banner: irc.Metasploitable.LAN NOTICE AUTH :** Looking up your hostname


 

