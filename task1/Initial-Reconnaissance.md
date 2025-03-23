# Identify Metasploitable's IP Address & Perform Initial Reconnaissance

## 1. Identify Metasploitable's IP Address
- Start Metasploitable and log in using the default credentials ( username and password : msfadmin)
- Open a terminal in Metasploitable and type:
              ifconfig
                or
                ip a
- Look for the `eth0` network interface and note down the IP address.

---

## 2. Perform Initial Reconnaissance
- Open a terminal in Kali Linux
- Use `nmap` to scan Metasploitable and identify open ports and services:
                    nmap -A  <Metasploitable-IP>

- Review the scan results to identify:
  - Open ports
  - Running services
  - Possible vulnerabilities

Example output:

21/tcp  open  ftp       vsftpd 2.3.4
22/tcp  open  ssh       OpenSSH 4.7p1
23/tcp  open  telnet    Linux telnetd
53/tcp  open  domain    ISC BIND 9.4.2
80/tcp  open  http      Apache 2.2.8
110/tcp open  pop3?
111/tcp open  rpcbind   2 (RPC #100000) 

like this all the open ports and services will be there 

This helps identify potential vulnerabilities.


