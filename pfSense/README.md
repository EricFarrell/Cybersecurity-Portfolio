## pfSense 
### Objective
- Configure the TCP port to 8443.
- Block access to World of Warcraft.
- Restrict access to the websites Hulu.com and Tiktok.com.
 


First, I made sure my pfSense VM is running and operating properly. from Kali Linux VM, I accessed the pfSense web interface by entering it's IP address into the web browser.

I navigated to the system settings/Advanced/Admin Access and change the TCP port to 8443.

![a019ff09-087d-46f3-a5de-0392fbec9d53](https://github.com/user-attachments/assets/f7db0af5-f0d8-470d-afc2-d90c435a1b28)

Setting the TCP port to 8443 typically changes the port used for secure web administration through HTTPS. By default, pfSense’s web interface listens on port 443 for HTTPS, but changing it to 8443 can improve security by reducing exposure to common ports targeted by attackers. I would then need to access the web interface using  https://192.168.1.1:8443 . This change can also help prevent conflicts with other services using port 443. Now, it can be seen that the address changed to what was configured.

![df2885f9-05f7-4221-a776-f01b805d79c3](https://github.com/user-attachments/assets/091ab834-3593-4673-a991-7dd511061e0e)

My next task was to disable the World of Warcraft game ports. I did this by going to Firewall/Rules/LAN and creating rules. I created three rules, One to block the port of 3724, and another for 6112. Along with blocking ports 6881-6999. These all are World of Warcraft ports. Disabling these will not allow players to log in, download updates, or interact with the game's servers. 

![98e1aa86-e521-4001-b390-f479a6e6c4c6](https://github.com/user-attachments/assets/4789cbff-0e8b-46db-9a17-7d507d68d145)

Since I am in the firewall settings, I decided to also disable a feature. I nagivated to the WAN tab, and created a new rule to disable inbound ICMP protocol. This rule prevents devices outside of my network from sending ICMP packets to my network (ping requests). This blocks external hosts from verifiying if my network is reachable which will reduce the risk of network reconnaissance by potential attackers. 

![3d289b7c-75dc-47a1-beaa-7e6583489f88](https://github.com/user-attachments/assets/24be7bcf-896b-4d64-8670-b1f749b34c92)

Next, I wanted to disable video streaming websites from being accessed on my network. I navigated to Services/DNS Resolver/General Settings/Edit Domain Override. I typed in Hulu.com & Tiktok.com. I then added a loopback address where it will redirect to the provided IP address. 

![e3756b3c-462c-4646-99a2-a9b2f47d6512](https://github.com/user-attachments/assets/139ff6ff-0adf-41b6-bb6a-0e61c9f493e5)

Once saved and applied, I tested the websites to ensure the firewall will deny access. 
![6faf7ccb-8447-466b-99f3-8d1d99c498aa](https://github.com/user-attachments/assets/b9c7a4fa-2194-46e3-ae5c-8050d12425cf)

![95303874-d0c0-41b5-9796-ef9ce113d2cd](https://github.com/user-attachments/assets/3d12bd48-f6a7-4590-849e-eb13f11354d2)

## Next Objectives

-Configure WAN & LAN 

-Update rules

-Run Snort port scan



### WAN & LAN
WAN and LAN interfaces were created in Snort to monitor and analyze network traffic in different contexts for external and internal threats.

![8715bb3b-5976-4cda-9b3f-eb115ad544e9](https://github.com/user-attachments/assets/16c88cce-4d56-4c8a-af3a-c559bf1e908a)

### Snort
Once I downloaded snort, I enabled it by going to its settings and checking the box "Enable Snort VRT". I then went to snort.org and created an account to obtain a Oinkmaster code. This is needed to use analyze network traffic effectively and detect threats.

![4f461bdf-c0ec-4ed3-bc1d-f9136c7fff53](https://github.com/user-attachments/assets/e2f7c84d-60ec-48c6-b35b-375712c25863)

Snort was then updated and the latest community rules were downloaded.

![fe6e38c2-2e43-4464-9d44-d536ad39ca41](https://github.com/user-attachments/assets/25248054-28d1-40e5-bda4-a893905e9bfb)

Once configured, I ran a Snort port scan. The log it outputs includes the detecting of unauthorized scanning, potential attackers, it can be used in internal and external reconnaissance, and improving incident reponse.

![ccf02c81-07f3-49e8-b8b3-751431cd471e](https://github.com/user-attachments/assets/047bec2b-9448-481a-9580-d4cb46e05d2a)

