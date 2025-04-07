# Task 4 – Service Enumeration
- To identify services and their versions running on the open ports of the Metasploit target (`192.168.1.4`).
- command used : nmap -sV 192.168.1.4
- -sV -->  enables version detection.

![](https://github.com/deepthiii33/sapienceintern/blob/main/task3/screenshots/service_enum_scan.png)
###  **Detailed Service Analysis**

#### **1. vsftpd 2.3.4 (Port 21 - FTP)**
- Very Secure FTP Daemon (vsftpd) is a common FTP server.
- **Risk**: This version has a well-known **backdoor vulnerability** that allows unauthenticated remote access.

---

#### **2. OpenSSH 4.7p1 (Port 22 - SSH)**
- Used for secure remote login.
- **Risk**: Older versions can be vulnerable to **user enumeration**, weak encryption configs, or **privilege escalation exploits**.

---

#### **3. Apache httpd 2.2.8 (Port 80 - HTTP)**
-  A popular open-source web server.
- **Risk**: This outdated version may be affected by **remote code execution**, **buffer overflows**, and **info disclosure vulnerabilities**.

---

#### **4. MySQL 5.0.51a (Port 3306 - Database)**
- An open-source relational database used for backend storage.
- **Risk**: Vulnerable to **SQL injection**, **auth bypass**, and **weak default settings**.

---

#### **5. PostgreSQL 8.3.x (Port 5432 - Database)**
- Open-source object-relational database system.
- **Risk**: May be affected by **DoS**, **privilege escalation**, or **unauthorized access issues**.

---

#### **6. ProFTPD 1.3.1 (Port 2121 - FTP)**
- An alternative FTP service.
- **Risk**: Known vulnerabilities in this version include **remote command injection** and **unauthenticated access**.

---

#### **7. Apache Tomcat (8180 - HTTP/AJP13)**
- Java-based web app server.
- **Risk**: Outdated versions may expose **admin interfaces**, **RCE vulnerabilities**, or **file upload flaws**.

---

#### **8. Metasploit Bindshell (Port 1524)**
- A backdoor shell listener included in Metasploitable intentionally.
- **Risk**: Grants direct remote shell access without authentication. High severity.

---

#### **9. Samba (Ports 139 & 445 - SMB)**
- Provides file/printer sharing between Unix and Windows.
- **Risk**: May allow **unauthenticated file access**, and is susceptible to exploits like **EternalBlue**.

---
- these are some services which include in the screenshot
