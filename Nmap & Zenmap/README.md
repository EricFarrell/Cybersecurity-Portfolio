## Nmap & Zenmap

### Objective
- Perform various Nmap scans in Kali Linux and Zenmap scans in Windows 10
- Analyze the information obtained from each scan, and explain the purpose and use of each scanning technique.



To start off, I will be confirming the IP addresses of all VM's that will be used. 

Windows 10 VM IP address is 192.168.56.101
![image](https://github.com/user-attachments/assets/627bfb96-d948-4da8-b043-c65e8469b6a1)

Kali Linux VM IP address is 192.168.102

![image](https://github.com/user-attachments/assets/774a7274-d655-4c3b-8457-ae349ca22481)

I started off by running "netdiscover" command in in Root Terminal on Kali Linux. 
This command is used to identify live hosts on the network while mapping the IP address and MAC addresses of those hosts.

![image](https://github.com/user-attachments/assets/ee43f6cb-7859-4fef-aadc-8f64f8b96fff)

### Nmap Scans

"nmap -sn 192.168.56.0/24" was ran on Root Terminal in Kali Linux. This scan performs a ping scan, but this type of scan detects which hosts
are on the network without doing a port scan. It said four hosts are up and it shows 
both IP addresses for the Kali Linux VM and the Windows 10 VM.

![image](https://github.com/user-attachments/assets/2d3c57e4-978c-49f0-a7cd-d3e1f726484e)

"nmap -sV 192.168.56.101" was ran on Root Terminal in Kali Linux. This scan performs a service scan which detects the software that's running 
on open ports. This scan detected the Windows 10 VM was using "Oracle Virtualbox Virtual NIC".
![image](https://github.com/user-attachments/assets/db274190-520b-4efe-b658-2d43ae406516)

"nmap -O 192.168.56.101" was ran on Root Terminal in Kali Linux. This scan performs a operating system detection scan. It figures out what operating system 
the target device is running by looking at it's response to network traffic.

![image](https://github.com/user-attachments/assets/f0859f99-6a45-4064-aaa8-482c9fbec0c5)


### Zenmap Scans
"nmap -T4 -A -v 192.168.56.101" was ran on Zenmap GUI on Windows 10. The profile ran was an "Intense scan". 
-T4: This adjusts the timing to level 4. This speeds up the scan, but can be more noticable by an intrusion detection system or firewall.

-A: This enables several features including Operating System Detection (-O), Version Detection (-sV), Script Scanning (-sC),
and traceroute to see the route the packets take to reach its target.

-v: This enables verbrose output. It just gives more detailed information about the scan process, and results.

Profile: Intense scan is considered aggressive because of the high level of detail it tries to gather. This type of profile is thorough
and can be detected due to its speed.

![image](https://github.com/user-attachments/assets/1e1d246f-4351-4a18-8a5a-f8420ef79c56)

This is the Network Topology for the previous Intense scan. It's designed to show how the devices in a network are arranged and connected 
to each other. It's helpful for planning better design, fix problems, security, and improve performance.

![image](https://github.com/user-attachments/assets/447504db-103c-4bf5-b609-07898afa1a6d)


"nmap 192.168.56.101" was ran on Zenmap GUI on Windows 10. The profile ran was a "Regular Scan". 
This scan just scans for open ports. It detected three open ports for the Windows 10 VM.
![image](https://github.com/user-attachments/assets/945ce0e3-2e3b-4341-8150-ba8623fbdb89)





