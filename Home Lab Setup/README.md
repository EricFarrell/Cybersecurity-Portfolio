# Home Lab Setup
This section outlines the design and configuration of my home lab, which serves as a sandbox for experimenting with cybersecurity tools, testing attack scenarios, and developing mitigation strategies. The lab is designed to replicate real-world environments, enabling hands-on learning and skill development in a controlled setting.
- **Description**: A detailed walkthrough of my home lab environment, including the tools, technologies, and configurations I use for cybersecurity testing and practice.
- **Tools**: VirtualBox, pfSense, Kali Linux, Windows, pfSense, etc.


### Virtualbox running with all of the Virtual Machines (VM's) listed.
![image](https://github.com/user-attachments/assets/36165aff-91b6-4418-b1ca-3d6c9f24959b)
![Screenshot 2025-01-09 175330](https://github.com/user-attachments/assets/43f47cce-9f70-41d2-9512-408b061d9227)


#### The setup process for Windows Server 2019, Windows 10, and Ubuntu were all exactly the same for the VM. Add a new VM, make sure it has enough storage. I went with 20GB each, 2048MB of memory, and then upload the dedicated ISO file for each VM in the virtual disk drive. Next make sure the network settings are set to Internal Network. For windows 10, this is set to Not Attached while downloading to avoid having to link an account with windows. Once the download process is completed on Windows 10, the network  settings can be reverted to Internal Network. For all VM’s once the download is completed, the system will restart. Before it restarts, go to the VM settings and eject the virtual disk ISO file that was used to setup the download. If it isn’t removed, it will act as if it wants to set up the system again off of that virtual disk drive. Removing it allows the system to run off of the software that it downloaded.

## Windows Server 2019
![image](https://github.com/user-attachments/assets/a08760f2-55a7-463e-a19b-300727ce2a44)
## Windows Server 2019 Ping to Windows 10 VM (192.168.1.11) and Ubuntu VM (192.168.1.12)

 (All VM's IP addresses were changed to static within the network settings. This allowed me to keep better track of all machines)
![image](https://github.com/user-attachments/assets/0ff9a7b5-30a5-40ff-960a-fa59db2f83ed)
## Ubuntu Pinging Windows Server 2019 (192.168.1.10) & Windows 10 (192.168.1.11)
![image](https://github.com/user-attachments/assets/bf19c0f8-79c5-42f2-b711-6db1f7076a95)

## Window 10 Pinging Ubuntu (192.168.1.12) & Windows Server 2019 (192.168.1.10) Successfully
![image](https://github.com/user-attachments/assets/74977834-ac38-441a-af3b-79255e4cca10)



### Kali Linux VM desktop
![image](https://github.com/user-attachments/assets/32ce49f1-6a0a-40f5-a872-7bd10fb7fe0c)
### ifconfig -a to see all network connections 
![image](https://github.com/user-attachments/assets/c74bed70-33d6-4334-bdd7-a489ac14b352)
### Ping IP address of my PC to ensure connectivity
![image](https://github.com/user-attachments/assets/3ef36d57-1112-4550-b17f-bbdcb4af7b8b)
### Windows 10 VM desktop
![image](https://github.com/user-attachments/assets/9dda6713-aa17-4735-bcac-f889d32732aa)
### Ping IP address of Windows 10 VM from Kali Linux VM to ensure connectivity between VM's
![image](https://github.com/user-attachments/assets/c34d21b1-4792-4aa4-9986-81305630b695)
### Kioptrix 2 VM main menu(default settings)
![image](https://github.com/user-attachments/assets/e2b859d1-1fd7-4b5a-9d56-9cf6b0826f01)
### Kioptrix 3 VM main menu (default settings)
![image](https://github.com/user-attachments/assets/0e088f61-3ef3-4cce-ad87-b3c23f296c34)
### Wireshark (default settings)
<img width="1126" alt="image" src="https://github.com/user-attachments/assets/674720c1-98dd-4def-8a6f-34d71da3c91c" />

### OWASP ZAP main menu (default settings)
<img width="1116" alt="image" src="https://github.com/user-attachments/assets/7a171a3b-b36e-40b9-b87e-fd1b231a05ba" />

### pfSense Firewall running 
<img width="1075" alt="Pfsense" src="https://github.com/user-attachments/assets/31c6ffaa-c180-4a26-8ca6-bcb80d1ea6d2" />

### pfSense Firewall GUI dashboard (default settings)
![image](https://github.com/user-attachments/assets/bdc4ad69-3d34-4fae-97ba-2252710ff823)

