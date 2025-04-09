# 6.  OS Fingerprinting
- To uncover the target machine’s OS type and version using Nmap’s built-in OS scanning.
- Command used: nmap -O target-ip
- -O --> enables OS detection
- Nmap figures out the OS by sending special network requests and watching how the system replies.then guesses the OS based on behavior it’s seen before in other systems.

![](https://github.com/deepthiii33/sapienceintern/blob/main/task3/screenshots/OS_scan.png)


#### Here the output is :
- **OS CPE: cpe:/o:linux:linux_kernel:2.6 |
OS details: Linux 2.6.9 - 2.6.33 |
Network Distance: 1 hop**

- It indicates that the target machine is running a Linux operating system with a kernel version between 2.6.9 and 2.6.33. The CPE (Common Platform Enumeration) provides a standardized identifier for the OS, and the system is just one network hop away, meaning it's directly accessible on the local network.










