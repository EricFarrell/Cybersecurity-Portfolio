## Nmap & Zenmap

### Objective
- Perform various Nmap scans in Kali Linux and Zenmap scans in Windows 10
- Analyze the information obtained from each scan, and explain the purpose and use of each scanning technique.



To start off, I will be confirming the IP addresses of all VM's that will be used. 

Windows 10 VM IP address is 192.168.56.101

![401784974-627bfb96-d948-4da8-b043-c65e8469b6a1](https://github.com/user-attachments/assets/0c5774d7-33f0-4b7b-9660-0e6c048c7223)


Kali Linux VM IP address is 192.168.102

![401785164-774a7274-d655-4c3b-8457-ae349ca22481](https://github.com/user-attachments/assets/b204fbf0-d21b-4f5e-9b58-8e3fcdb49f48)


I started off by running "netdiscover" command in in Root Terminal on Kali Linux. 
This command is used to identify live hosts on the network while mapping the IP address and MAC addresses of those hosts.

![401785743-ee43f6cb-7859-4fef-aadc-8f64f8b96fff](https://github.com/user-attachments/assets/e4215d19-ee1a-4461-943f-063165835154)


### Nmap Scans

"nmap -sn 192.168.56.0/24" was ran on Root Terminal in Kali Linux. This scan performs a ping scan, but this type of scan detects which hosts
are on the network without doing a port scan. It said four hosts are up and it shows 
both IP addresses for the Kali Linux VM and the Windows 10 VM.

![401788115-2d3c57e4-978c-49f0-a7cd-d3e1f726484e](https://github.com/user-attachments/assets/394e8da0-6ae0-4747-8285-ccb60a12809a)


"nmap -sV 192.168.56.101" was ran on Root Terminal in Kali Linux. This scan performs a service scan which detects the software that's running 
on open ports. This scan detected the Windows 10 VM was using "Oracle Virtualbox Virtual NIC".

![401790106-db274190-520b-4efe-b658-2d43ae406516](https://github.com/user-attachments/assets/07a849a8-7ee8-47ab-b3ef-302d56f22833)


"nmap -O 192.168.56.101" was ran on Root Terminal in Kali Linux. This scan performs a operating system detection scan. It figures out what operating system 
the target device is running by looking at it's response to network traffic.

![401794268-f0859f99-6a45-4064-aaa8-482c9fbec0c5](https://github.com/user-attachments/assets/b2de45c8-dc67-4b0d-a461-f4b57e9645a7)



### Zenmap Scans
"nmap -T4 -A -v 192.168.56.101" was ran on Zenmap GUI on Windows 10. The profile ran was an "Intense scan". 
-T4: This adjusts the timing to level 4. This speeds up the scan, but can be more noticable by an intrusion detection system or firewall.

-A: This enables several features including Operating System Detection (-O), Version Detection (-sV), Script Scanning (-sC),
and traceroute to see the route the packets take to reach its target.

-v: This enables verbrose output. It just gives more detailed information about the scan process, and results.

Profile: Intense scan is considered aggressive because of the high level of detail it tries to gather. This type of profile is thorough
and can be detected due to its speed.

![401795465-1e1d246f-4351-4a18-8a5a-f8420ef79c56](https://github.com/user-attachments/assets/95cb75f3-61ff-4107-9bcb-33a4f7e118e8)


This is the Network Topology for the previous Intense scan. It's designed to show how the devices in a network are arranged and connected 
to each other. It's helpful for planning better design, fix problems, security, and improve performance.

![401799573-447504db-103c-4bf5-b609-07898afa1a6d](https://github.com/user-attachments/assets/d1f51d5e-47c0-4cc7-8afb-769de1c50a1a)


"nmap 192.168.56.101" was ran on Zenmap GUI on Windows 10. The profile ran was a "Regular Scan". 
This scan just scans for open ports. It detected three open ports for the Windows 10 VM.

![401798967-945ce0e3-2e3b-4341-8150-ba8623fbdb89](https://github.com/user-attachments/assets/fddea1a4-59af-4189-a663-16745160e1c5)

