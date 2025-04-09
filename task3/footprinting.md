# 7. Footprinting
To gather  information about the target IP and domain using basic footprinting tools like `whois`, `dig`, and `nslookup`.

## Whois command
**Used to retrieve registration details of a domain name or an IP address. It provides information about the owner, registrar, creation and expiration dates, and contact information.**

1. Command : whois domain  --->  ``whois vulnweb.com``
   
![](https://github.com/deepthiii33/sapienceintern/blob/main/task3/screenshots/whois_sample.png)

The whois information for vulinweb.com reveals that EuroDNS S.A. is the registrar responsible for this domain. The domain was initially registered on June 14, 2010, and its current registration is valid until June 14, 2025. If you need to report any abuse related to this domain, you can find the contact email and phone number provided by the registrar. The website's location on the internet is currently managed by name servers associated with EuroDNS.

2. OR : whois target-ip  ---> ``whois 192.168.1.4``
   
![](https://github.com/deepthiii33/sapienceintern/blob/main/task3/screenshots/whois_ip.png)

From this output we get,
- IP Address Checked: 192.168.1.4
- Type of IP: It's a private IP, used in home or office networks.
- IP Range It Belongs To: 192.168.0.0 – 192.168.255.255
- Owner of This IP Range: IANA (Internet Assigned Numbers Authority)
- Purpose: Meant for internal/local use only , Not used on the public internet
- Why No Owner Info Found: Private IPs are not tracked online , They're shared and reused in many networks
- Standard Followed: RFC 1918 (rules for private IPs)

---
## dig command
**It is a tool used to look up information from DNS (Domain Name System) servers. It helps you find details about a domain name, like its IP address or mail server. It's more advanced than basic tools and gives detailed responses, which makes it useful for checking and troubleshooting how domain names are being resolved.**

Command used : dig domain or dig target-ip
- ``dig -x 192.168.1.4``
  
![](https://github.com/deepthiii33/sapienceintern/blob/main/task3/screenshots/dig_scan.png)

From this output we get,
- Performs a reverse DNS lookup to check if the IP resolves to any domain name.
- This command performs a reverse DNS lookup to find the domain name linked to the IP address 192.168.1.4.
- The result shows that no domain name is associated with this IP,  because it's a private IP address used in local networks.
- The status NXDOMAIN means "Non-Existent Domain", confirming there's no reverse DNS record for this address.
- The DNS server used for the query is 103.153.93.230, and it responded in about 12 milliseconds.

---

## NSlookup command
**NSLookup is a command-line tool used to get information from DNS servers, like finding the IP address of a website; it's easy to use and works in both interactive and one-time query modes, though it shows less detail than dig.**

Command used: nslookup domain
- ``nslookup vulnweb.com``

![](https://github.com/deepthiii33/sapienceintern/blob/main/task3/screenshots/nslookup_sample.png)

From this nslookup vulnweb.com output we get,
- DNS Server Used for the Query: 103.153.93.230
- Domain Name Queried: vulnweb.com
- IP Address of the Domain: 44.228.249.3 (This is the IP address where vulnweb.com is hosted)
- Non-authoritative Answer: The response came from a DNS server that got the info from another source, not directly from the domain’s main 
  DNS server.

 - **nslookup can be used with an IP address to perform a reverse DNS lookup. This means it tries to find the domain name linked to that IP. It works well with public IP addresses, like Google’s 8.8.8.8, which resolves to dns.google. However, if you use it with a private IP (like 192.168.1.1), it usually won’t return a result unless your local network has reverse DNS set up.**


---
**Footprinting helped in extracting publicly available information related to the domain and IP addresses. While private IPs offer limited info, domain-based queries provided insights useful for mapping the network structure and identifying potential targets.**


