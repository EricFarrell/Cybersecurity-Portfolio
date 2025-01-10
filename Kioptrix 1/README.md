### Objective:
To perform reconnaissance and enumeration on the Kioptrix Level 1 virtual machine using Nmap to identify open ports, running services, and potential vulnerabilities, highlighting the role of scanning in penetration testing.

### Tools and Techniques Used:
Tool: Nmap (Network Mapper) & Kali Linux

Techniques: Network scanning, port enumeration, service version detection, vulnerability scanning
Concepts: Reconnaissance, OS detection, banner grabbing, and vulnerability identification

## Nmap 192.168.56.0/24 
This command performs a basic ping sweep, scanning all IP addresses in the 192.168.56.0/24 subnet range (from 192.168.56.0 to 192.168.56.255) to identify active hosts. This command found the IP address of 192.168.56.102 with open ports. This is the Kioptrix 1 VM. 

The following ports were found to be open during the Nmap scan:

**Port 22 (SSH):** OpenSSH service running for remote login.

**Port 80 (HTTP):** Apache web server hosting a website.

**Port 111 (RPCbind):** A service used for Remote Procedure Calls (RPC), often associated with NFS.

**Port 139 (NetBIOS-SSN):** Samba service for file sharing and network communication.

**Port 443 (HTTPS):** Secure web server (SSL/TLS).

**Port 32768 (RPC High Port):** A high port typically associated with RPC or other dynamically assigned services.


![image](https://github.com/user-attachments/assets/7bd5c30a-3878-46f6-a7e0-47fe87bfe3d2)

## 192.168.56.102
I typed the IP address into a web browser and it resulted in a test page.
![image](https://github.com/user-attachments/assets/7210013f-3566-476b-8b62-ce3a57938871)

## NMAP -O 192.168.56.102
This command performs an operating system detection of the target host. It detected it was running Linux 2.4.X
![image](https://github.com/user-attachments/assets/8b1cea0a-04f5-43a3-8792-856d179415ed)

## NMAP -sV 192.168.56.102
This command runs a service version detection. This option probes open ports to determine the exact software and version running on those ports. It helps you identify not just that a port is open, but also what application or service is running on it and its version.
![image](https://github.com/user-attachments/assets/92a396aa-ec18-4a7a-9864-1d4b07ed5818)
## Nmap –p- -A 192.168.56.102
This command is a comprehensive Nmap scan that combines several options to gather extensive information about the target system.
### -p-
Tells Nmap to scan all 65,535 TCP ports.
### -A
OS Detection: Attempts to identify the operating system.

Service Version Detection: Determines the software and version running on each open port.

Script Scanning: Runs Nmap's default NSE (Nmap Scripting Engine) scripts to detect vulnerabilities or gather additional information.

Traceroute: Maps the route packets take to the target host.
![image](https://github.com/user-attachments/assets/602336f8-9dda-4e08-b094-89009417e098)

## NMAP -SX 192.168.56.102
This command performs an Xmas Scan, which is a type of stealthy TCP port scan. This method can bypass simple firewalls or intrusion detection systems because it doesn’t use full connection attempts like SYN scans.
![image](https://github.com/user-attachments/assets/c6aa34e6-9402-4105-a165-26c87555e290)

## NMAP -PN -SCRIPT VULN 192.168.56.102
This command is a vulnerability scan on the specified target.
### -Pn
This disables host discovery, treats the target as "online" regardless if it responds to the ping requests.
### -- script vuln 
Runs Nmap's vulnerability scanning scripts, which are part of the NSE (Nmap Scripting Engine) and focuses on identifying known vulnerabilities in services running on the target.

### Vulnerabilities found:
SSL POODLE, CCS Injection
![image](https://github.com/user-attachments/assets/3e79a37f-3b41-47c6-8e7d-54db4e49e340)




[Back to Home](https://github.com/EricFarrell/Cybersecurity-Portfolio/blob/6a83e9281d036567be6e5ed086086a2c0a63f5f6/README.md)


[Previous Project - Infrastructure Diagram](https://github.com/EricFarrell/Cybersecurity-Portfolio/tree/6a83e9281d036567be6e5ed086086a2c0a63f5f6/Infrastructure%20Diagram)


[Next Project - Maltego](https://github.com/EricFarrell/Cybersecurity-Portfolio/tree/6a83e9281d036567be6e5ed086086a2c0a63f5f6/Maltego)
