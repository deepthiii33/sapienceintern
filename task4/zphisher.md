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
- selected Facebook -->  Facebook Messenger login Page

#### Method 1: Localhost with Custom Port
![](https://github.com/deepthiii33/sapienceintern/blob/main/task4/screenshots/Zphisher_Setup.jpg)

- Configured Zphisher to run on localhost using a custom port(3333)


- Zphisher will start a local web server hosting the phishing page
  
![](https://github.com/deepthiii33/sapienceintern/blob/main/task4/screenshots/localhost.png)

If you're only using localhost, the link will only work on your own machine or LAN — not over the internet.
So after  opening the link and enters their credentials on the fake page , Zphisher captures and logs the username and password in real-time.

Here fake page is messanger login page , We can see the output in Zphisher terminal after victim enter the credentails , ex:

![](https://github.com/deepthiii33/sapienceintern/blob/main/task4/screenshots/output.png)

#### Method 2: LocalXpose for Internet Access

- Configured Zphisher to run on localxpose and choose a custom port(3333).Then paste the localxpose token after creating a account in localxpose.io

![](https://github.com/deepthiii33/sapienceintern/blob/main/task4/screenshots/localxpose.png)

Token can get from  ``https://localxpose.io/dasboard/access`` page

- Then we can enter custom url(Changing the Mask URL)
- After it will automatically generate 3URL's include our custom URL

 ![](https://github.com/deepthiii33/sapienceintern/blob/main/task4/screenshots/fake_url's.png)

Here, 3rd URL is my Custom URL.After generating the phishing URL using **Zphisher**, I tested it by opening it in a browser. Depending on the tunneling method, different warning confirmation messages appeared before reaching the fake login page.

![](https://github.com/deepthiii33/sapienceintern/blob/main/task4/screenshots/localxpose_confirm_page.png)

Once the user clicks Yes or Visit, the browser redirects to the fake login page, hosted via Zphisher. If the victim enters their credentials, Zphisher instantly captures them and displays them in the terminal(here fake page is messenger login page)

![](https://github.com/deepthiii33/sapienceintern/blob/main/task4/screenshots/localxpose_output.png)

here , When the victim opened the link and entered their login details, Zphisher captured the IP address and the credentials. The victim’s IP was 103.155.223.80, and the login details were saved in the auth folder. This confirms that the phishing page was working correctly.


After the phishing attempt, the captured data was saved automatically by Zphisher inside the auth folder. This included the victim's IP address in ip.txt and the login credentials in usernames.dat. The screenshot below shows the contents of the auth folder after a successful attack.

![](https://github.com/deepthiii33/sapienceintern/blob/main/task4/screenshots/zphisher_auth_folder.png)

----
## Conlusion

In this report, phishing was performed using Zphisher to demonstrate how easily phishing attacks can be carried out. This highlights the importance of being aware of such threats and taking steps like using strong passwords, multi-factor authentication, and educating users to avoid falling victim to phishing attacks.



