## pfSense 
### Objective
- Configure the TCP port to 8443.
- Block access to World of Warcraft.
- Restrict access to the websites Hulu.com and Tiktok.com.
 


First, I made sure my pfSense VM is running and operating properly. from Kali Linux VM, I accessed the pfSense web interface by entering it's IP address into the web browser.

I navigated to the system settings/Advanced/Admin Access and change the TCP port to 8443.
![image](https://github.com/user-attachments/assets/a019ff09-087d-46f3-a5de-0392fbec9d53)
Setting the TCP port to 8443 typically changes the port used for secure web administration through HTTPS. By default, pfSense’s web interface listens on port 443 for HTTPS, but changing it to 8443 can improve security by reducing exposure to common ports targeted by attackers. I would then need to access the web interface using  https://192.168.1.1:8443 . This change can also help prevent conflicts with other services using port 443. Now, it can be seen that the address changed to what was configured.
![image](https://github.com/user-attachments/assets/df2885f9-05f7-4221-a776-f01b805d79c3)

My next task was to disable the World of Warcraft game ports. I did this by going to Firewall/Rules/LAN and creating rules. I created three rules, One to block the port of 3724, and another for 6112. Along with blocking ports 6881-6999. These all are World of Warcraft ports. Disabling these will not allow players to log in, download updates, or interact with the game's servers. 

![image](https://github.com/user-attachments/assets/98e1aa86-e521-4001-b390-f479a6e6c4c6)

Since I am in the firewall settings, I decided to also disable a feature. I nagivated to the WAN tab, and created a new rule to disable inbound ICMP protocol. This rule prevents devices outside of my network from sending ICMP packets to my network (ping requests). This blocks external hosts from verifiying if my network is reachable which will reduce the risk of network reconnaissance by potential attackers. 
![image](https://github.com/user-attachments/assets/3d289b7c-75dc-47a1-beaa-7e6583489f88)


Next, I wanted to disable video streaming websites from being accessed on my network. I navigated to Services/DNS Resolver/General Settings/Edit Domain Override. I typed in Hulu.com & Tiktok.com. I then added a loopback address where it will redirect to the provided IP address. 

![image](https://github.com/user-attachments/assets/e3756b3c-462c-4646-99a2-a9b2f47d6512)

Once saved and applied, I tested the websites to ensure the firewall will deny access. 
![image](https://github.com/user-attachments/assets/6faf7ccb-8447-466b-99f3-8d1d99c498aa)
![image](https://github.com/user-attachments/assets/95303874-d0c0-41b5-9796-ef9ce113d2cd)

## Next Objectives

-Configure WAN & LAN 

-Update rules

-Run Snort port scan



### WAN & LAN
WAN and LAN interfaces were created in Snort to monitor and analyze network traffic in different contexts for external and internal threats.
![image](https://github.com/user-attachments/assets/8715bb3b-5976-4cda-9b3f-eb115ad544e9)

### Snort
Once I downloaded snort, I enabled it by going to its settings and checking the box "Enable Snort VRT". I then went to snort.org and created an account to obtain a Oinkmaster code. This is needed to use analyze network traffic effectively and detect threats.
![enabling snort ](https://github.com/user-attachments/assets/4f461bdf-c0ec-4ed3-bc1d-f9136c7fff53)

Snort was then updated and the latest community rules were downloaded.
![image](https://github.com/user-attachments/assets/fe6e38c2-2e43-4464-9d44-d536ad39ca41)


Once configured, I ran a Snort port scan. The log it outputs includes the detecting of unauthorized scanning, potential attackers, it can be used in internal and external reconnaissance, and improving incident reponse.
![snort port scan log](https://github.com/user-attachments/assets/ccf02c81-07f3-49e8-b8b3-751431cd471e)


[Back to Home](https://github.com/EricFarrell/Cybersecurity-Portfolio/blob/6a83e9281d036567be6e5ed086086a2c0a63f5f6/README.md)

[Previous Project - Wireshark](https://github.com/EricFarrell/Cybersecurity-Portfolio/tree/6a83e9281d036567be6e5ed086086a2c0a63f5f6/Wireshark)

