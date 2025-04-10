# 1.  Phishing using Zphisher

## Tools Used

- Zphisher (GitHub-based automated phishing tool)
- Kali Linux (Attacker machine)
- Tunneling Services: localhost.run, localexpose

## What is Zphisher?

Zphisher is an easy-to-use phishing tool written in bash that helps create fake login pages for popular websites like Facebook, Instagram, Gmail, etc. It’s mainly used for ethical hacking and security testing. It automates the process of setting up a phishing page and gives you a link to send to the target. When someone enters their username and password on the fake page, the tool captures and displays the credentials on your terminal.

## Steps

1. Clone the zphisher tool
- ``git clone https://github.com/htr-tech/zphisher.git``
-   ``cd zphisher``
-   `` chmod +x  zphisher.sh`` : Provides execute permission
-  ``./zphisher.sh``

2. Choose a phishing method 
