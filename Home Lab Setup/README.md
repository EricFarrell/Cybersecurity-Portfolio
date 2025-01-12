## Home Lab Setup
This section outlines the design and configuration of my home lab, which serves as a sandbox for experimenting with cybersecurity tools, testing attack scenarios, and developing mitigation strategies. The lab is designed to replicate real-world environments, enabling hands-on learning and skill development in a controlled setting.


### Virtualbox running with all of the Virtual Machines (VM's) listed.
![36165aff-91b6-4418-b1ca-3d6c9f24959b](https://github.com/user-attachments/assets/4c2c7124-3ed2-4f18-b38a-bc6c2f93e6a8)

![Screenshot 2025-01-09 175330](https://github.com/user-attachments/assets/43f47cce-9f70-41d2-9512-408b061d9227)


The setup process for Windows Server 2019, Windows 10, and Ubuntu were all exactly the same for the VM. Add a new VM, make sure it has enough storage. I went with a minimum of 15GB each and 2048MB of memory. These numbers I adjusted depending on which VM's I would be making downloads on in the future. Then I upload the dedicated ISO file for each VM in the virtual disk drive. Next make sure the network settings are set to Internal Network. For windows 10, this is set to Not Attached while downloading to avoid having to link an account with windows. Once the download process is completed on Windows 10, the network  settings can be reverted to Internal Network. For all VM’s once the download is completed, the system will restart. Before it restarts, I went to the VM settings and ejected the virtual disk ISO file that was used to setup the download. If it isn’t removed, it will act as if it wants to set up the system again off of that virtual disk drive. Removing it allows the system to run off of the software that it downloaded.

## Windows Server 2019

(All virtual machines were configured with static IP addresses within the network settings. This approach ensures better organization and simplifies tracking and management of each virtual machine within the environment.)
![a08760f2-55a7-463e-a19b-300727ce2a44](https://github.com/user-attachments/assets/7b851069-24fa-4ed0-ba01-3f0abf8087ec)

 
## Windows Server 2019 Ping to Windows 10 VM (192.168.1.11) and Ubuntu VM (192.168.1.12) to ensure connectivity
![0ff9a7b5-30a5-40ff-960a-fa59db2f83ed](https://github.com/user-attachments/assets/ac7d8e95-06c5-4637-9b26-166016a003d1)

## Ubuntu Pinging Windows Server 2019 (192.168.1.10) & Windows 10 (192.168.1.11) to ensure connectivity
![bf19c0f8-79c5-42f2-b711-6db1f7076a95](https://github.com/user-attachments/assets/5604044c-aea8-4f0c-a483-30e4fb29cf33)

## Window 10 Pinging Ubuntu (192.168.1.12) & Windows Server 2019 (192.168.1.10) to ensure connectivity
![74977834-ac38-441a-af3b-79255e4cca10](https://github.com/user-attachments/assets/cdb9a330-b5a9-4df7-8e2b-7a44b6ebe388)

### Kali Linux VM desktop
![32ce49f1-6a0a-40f5-a872-7bd10fb7fe0c](https://github.com/user-attachments/assets/ba5e754c-2105-4b5a-8613-74ab28e9d33a)

### ifconfig -a to see all network connections 
![c74bed70-33d6-4334-bdd7-a489ac14b352](https://github.com/user-attachments/assets/5a2e5d52-f210-4a0e-a384-1bb7c992fefb)

### Ping IP address of my PC to ensure connectivity
![3ef36d57-1112-4550-b17f-bbdcb4af7b8b](https://github.com/user-attachments/assets/e24e51b1-c0f2-4b64-921d-992558edae5d)

### Windows 10 VM desktop
![9dda6713-aa17-4735-bcac-f889d32732aa](https://github.com/user-attachments/assets/a3d704ad-48fc-4a7a-aebe-49b443d52a64)

### Ping IP address of Windows 10 VM from Kali Linux VM to ensure connectivity
![c34d21b1-4792-4aa4-9986-81305630b695](https://github.com/user-attachments/assets/017c6c4a-2dd5-4831-977a-216d41b1a7ae)

### Kioptrix 2 VM main menu(default settings)
![e2b859d1-1fd7-4b5a-9d56-9cf6b0826f01](https://github.com/user-attachments/assets/d144b153-cb5b-4367-819e-ec931b7836fa)

### Kioptrix 3 VM main menu (default settings)
![0e088f61-3ef3-4cce-ad87-b3c23f296c34](https://github.com/user-attachments/assets/d25460b1-4e3b-4b04-bb7b-f17a07fe0e7a)

### Wireshark (default settings)
<img width="1126" alt="674720c1-98dd-4def-8a6f-34d71da3c91c" src="https://github.com/user-attachments/assets/e6022d16-a4a9-4e77-b9d6-c0591d77c411" />

### OWASP ZAP main menu (default settings)
<img width="1116" alt="7a171a3b-b36e-40b9-b87e-fd1b231a05ba" src="https://github.com/user-attachments/assets/6e7820ab-8e65-4bd1-b02c-092c05aa559a" />


### pfSense Firewall VM running 

<img width="1075" alt="31c6ffaa-c180-4a26-8ca6-bcb80d1ea6d2" src="https://github.com/user-attachments/assets/5c5c62fd-fa2c-466f-aa5a-7d1724fb00fa" />

### pfSense Firewall GUI dashboard (default settings)
![bdc4ad69-3d34-4fae-97ba-2252710ff823](https://github.com/user-attachments/assets/fb4308fc-462e-427f-9b55-6eb751308564)

