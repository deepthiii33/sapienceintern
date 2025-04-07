# 1. Identify Target IP Range


- Determine the IP range for scanning to locate the Metasploit target machine.
- Commands used : ifconfig
- on metasploit machine use **ifconfig**
  ![](https://github.com/deepthiii33/sapienceintern/blob/main/task3/screenshots/target_ip.png)
- this gave my target ip address : 192.168.1.4

# 2. Perform Ping Scan

- To identify active hosts within the target IP range 192.168.1.4
- commands used : nmap -sn <target-ip>
- -sn  -->  Nmap to perform a "ping scan" — it checks which hosts are up without scanning ports.
![](https://github.com/deepthiii33/sapienceintern/blob/main/task3/screenshots/ping_scan.png)
- This confirmed that the Metasploit machine is reachable and ready for further enumeration.

  
# Task 3 – Port Scanning
- To identify open ports on the Metasploit target machine (`192.168.1.4`) using a  Nmap scan.
- command used : nmap -p- <target_ip>
- -p-  -->  Nmap to scan all 65535 ports
![](https://github.com/deepthiii33/sapienceintern/blob/main/task3/screenshots/port_scan.png)
-  useful for detecting services running on uncommon ports.
-  Open ports indicate potential entry points.
-  These results will be used in the next steps for service enumeration and vulnerability scanning.
-  Here open ports are : ftp,ssh,telnet,smtp,postgresql,.....and all



  
