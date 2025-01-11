## Kioptrix 1
### Objective
- Perform reconnaissance and enumeration on the Kioptrix Level 1 virtual machine using Nmap to identify open ports running services, and potential vulnerabilities.
-  Highlighting the role of scanning in penetration testing.

## Nmap 192.168.56.0/24 
This command performs a basic ping sweep, scanning all IP addresses in the 192.168.56.0/24 subnet range (from 192.168.56.0 to 192.168.56.255) to identify active hosts. This command found the IP address of 192.168.56.102 with open ports. This is the Kioptrix 1 VM. 

The following ports were found to be open during the Nmap scan:

**Port 22 (SSH):** OpenSSH service running for remote login.

**Port 80 (HTTP):** Apache web server hosting a website.

**Port 111 (RPCbind):** A service used for Remote Procedure Calls (RPC), often associated with NFS.

**Port 139 (NetBIOS-SSN):** Samba service for file sharing and network communication.

**Port 443 (HTTPS):** Secure web server (SSL/TLS).

**Port 32768 (RPC High Port):** A high port typically associated with RPC or other dynamically assigned services.


![7bd5c30a-3878-46f6-a7e0-47fe87bfe3d2](https://github.com/user-attachments/assets/2f472994-169e-4429-bf20-c22504c1ff69)


## 192.168.56.102
I typed the IP address into a web browser and it resulted in a test page.

![7210013f-3566-476b-8b62-ce3a57938871](https://github.com/user-attachments/assets/3dbc033d-9f0d-466f-9015-f9ba5e1f046d)


## NMAP -O 192.168.56.102
This command performs an operating system detection of the target host. It detected it was running Linux 2.4.X

![8b1cea0a-04f5-43a3-8792-856d179415ed](https://github.com/user-attachments/assets/13835eea-e1fe-4757-bfcb-19bc9a4ed6de)


## NMAP -sV 192.168.56.102
This command runs a service version detection. This option probes open ports to determine the exact software and version running on those ports. It helps you identify not just that a port is open, but also what application or service is running on it and its version.

![92a396aa-ec18-4a7a-9864-1d4b07ed5818](https://github.com/user-attachments/assets/b53533dc-7aa3-46fb-bbc3-e0164dd3719b)


## Nmap –p- -A 192.168.56.102
This command is a comprehensive Nmap scan that combines several options to gather extensive information about the target system.
### -p-
Tells Nmap to scan all 65,535 TCP ports.
### -A
OS Detection: Attempts to identify the operating system.

Service Version Detection: Determines the software and version running on each open port.

Script Scanning: Runs Nmap's default NSE (Nmap Scripting Engine) scripts to detect vulnerabilities or gather additional information.

Traceroute: Maps the route packets take to the target host.
![602336f8-9dda-4e08-b094-89009417e098](https://github.com/user-attachments/assets/e0d4649e-cce4-4232-8825-b62c0a18811d)


## NMAP -SX 192.168.56.102
This command performs an Xmas Scan, which is a type of stealthy TCP port scan. This method can bypass simple firewalls or intrusion detection systems because it doesn’t use full connection attempts like SYN scans.

![c6aa34e6-9402-4105-a165-26c87555e290](https://github.com/user-attachments/assets/0876d153-13d2-425a-bcef-67f2a47c8f1b)

## NMAP -PN -SCRIPT VULN 192.168.56.102
This command is a vulnerability scan on the specified target.
### -Pn
This disables host discovery, treats the target as "online" regardless if it responds to the ping requests.
### -- script vuln 
Runs Nmap's vulnerability scanning scripts, which are part of the NSE (Nmap Scripting Engine) and focuses on identifying known vulnerabilities in services running on the target.

### Vulnerabilities found:
SSL POODLE, CCS Injection

![3e79a37f-3b41-47c6-8e7d-54db4e49e340](https://github.com/user-attachments/assets/154806ef-c3c8-4f02-99f2-b48a73c730c9)

