# Installing Kali Linux and Metasploitable  

Kali Linux is a powerful penetration testing operating system, while Metasploitable is a deliberately vulnerable virtual machine designed for security training. Below are the two methods for installing Kali Linux.  

---

## Method 1: Installing Kali Linux via ISO (Manual Installation)  

1. **Download Kali Linux ISO**  
   - Get the latest ISO file from [Kali Linux Official Site](https://www.kali.org/get-kali/#kali-platforms).  

2. **Create a New Virtual Machine**  
   - Open **VirtualBox** or **VMware Workstation**.  
   - Click **New** → Name it "Kali Linux" or any preferred name.  
   - Set **Type**: Linux, and **Version**: Debian (64-bit).  
   - Allocate RAM (**Recommended: 4GB or more**).  
   - Choose **Create a Virtual Hard Disk** and attach the Kali Linux ISO under the virtual CD/DVD drive (complete offline installation from the official site).  

3. **Load Kali ISO & Install**  
   - Start the VM and select the Kali ISO as the boot disk.  
   - Follow the installation wizard to set up username, password, and partitioning.  
   - Complete the installation, restart, and log in to Kali Linux.  

---

## Method 2: Using Kali Linux Prebuilt Virtual Machine (Easier & Faster)  

1. **Download the Prebuilt VM**  
   - Go to the [Kali Linux Virtual Machines page](https://www.kali.org/get-kali/#kali-virtual-machines).  
   - Download the **OVA file** (for VirtualBox or VMware).  

2. **Import the OVA File**  
   - Open **VirtualBox** or **VMware Workstation**.  
   - Click **File → Import Appliance** → Select the OVA file and Import.  

3. **Start Kali Linux**  
   - Launch the VM and log in using the default credentials:  
     - **Username**: kali  
     - **Password**: kali  

---

## Updating Kali Linux  

After installation, update and upgrade Kali Linux:  
           sudo apt update  
           sudo apt upgrade  


---

# Installing Metasploitable  

1. **Download Metasploitable 2**  
   - Get the VM file from [SourceForge](https://sourceforge.net/projects/metasploitable/files/Metasploitable2/).  

2. **Extract & Import**  
   - Extract the downloaded **ZIP file**.  
   - In **VirtualBox/VMware**, click **New** → Set **Type: Linux** and **Version: Linux**.  
   - Under **Hard Disk**, choose **"Use an existing disk file"** and select the extracted Metasploitable 2 file.  

3. **Start the VM**  
   - Once started, log in using:  
     - **Username**: msfadmin  
     - **Password**: msfadmin  

---

# Configuring Networking  

To allow communication between Kali Linux and Metasploitable:  

1. Open **VirtualBox/VMware settings** for both VMs.  
2. Under **Network**, select **Bridged Adapter**.  
3. Restart both VMs and find their IP addresses:  
   ```bash
   ifconfig  # On Metasploitable  
   ip a      # On Kali Linux  
   ```
4. Note the **IP addresses**.  

---

# Security Tools Installation  

Kali Linux comes with several preinstalled tools for penetration testing, network analysis, and security assessments.  

### Preinstalled Tools in Kali Linux  

- **Aircrack-ng** – Wireless network security auditing.  
- **Hydra** – Password cracking tool for various protocols.  
- **Sqlmap** – Automated SQL injection detection and exploitation.  
- **John the Ripper** – Fast password cracker.  
- **Nikto** – Web vulnerability scanner.  

### Additional Tools to Install  

Kali Linux comes with several preinstalled tools for penetration testing, network analysis, and security assessments. 
Below are some commonly used ones:  

# Preinstalled Tools in Kali Linux  
 * Aircrack-ng – Wireless network security auditing.  
 * Hydra – Password cracking tool for various protocols.  
 * Sqlmap – Automated SQL injection detection and exploitation.  
 * John the Ripper – Fast password cracker.  
 * Nikto      – Web vulnerability scanner.  

# Additional Tools to Install
You can install more tools based on your requirements:  

 * Nmap  – Network scanning and reconnaissance tool.  
             Command: sudo apt install nmap  
 * Netdiscover – Used for finding live hosts in a network.  
            Command: sudo apt install netdiscover  
 * Metasploit Framework – Exploitation and penetration testing tool.  
            Command: sudo apt install metasploit-framework  
 * Wireshark  – Captures and analyzes network traffic.  
            Command: sudo apt install wireshark  
 * Burp Suite  – Web security testing and vulnerability scanning tool.  
            Command: sudo apt install burpsuite  

Kali Linux provides a wide range of preinstalled tools, and you can install additional tools based on your penetration testing needs.
