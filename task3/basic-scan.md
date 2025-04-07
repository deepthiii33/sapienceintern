# 1. Identify Target IP Range


- Determine the IP range for scanning to locate the Metasploit target machine.
- Commands used : ifconfig
- on metasploit machine use **ifconfig**
  ![](https://github.com/deepthiii33/sapienceintern/blob/main/task3/screenshots/target_ip.png)
- this gave my target ip address : 192.168.1.4

# 2. Perform Ping Scan

- To identify active hosts within the target IP range 192.168.1.4
- commands used : nmap -sn 192.168.1.4
![](https://github.com/deepthiii33/sapienceintern/blob/main/task3/screenshots/ping_scan.png)
- -sn  -->  Nmap to perform a "ping scan" — it checks which hosts are up without scanning ports.
- This confirmed that the Metasploit machine is reachable and ready for further enumeration.

  




  
