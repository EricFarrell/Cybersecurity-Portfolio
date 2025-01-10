## Wireshark

### Objective
- Capture network traffic using packet analysis.
- Ping virtual machines (VMs) and monitor network activity.
- Identify any insecure network traffic or vulnerabilities.
- Perform a service scan to assess available services.

### Identifying Kali Linux & Windows 10

For this lab, I will first be identifying Kali Linux and Windows IP addresses. 

Kali Linux has an IP address of 192.168.1.245


![image](https://github.com/user-attachments/assets/90ecde5b-0045-44f5-9e71-5c2d42b0986a)
Windows has an IP address of 192.168.1.150
![image](https://github.com/user-attachments/assets/0e059bf0-cff3-43f1-8518-c94c0b858a19)

In Wireshark on Kali Linux, I will begin a Packet Capture on my current network. All network traffic is shown here.
![image](https://github.com/user-attachments/assets/444310d0-2451-4f9f-8b22-e037beeb8d0b)
I opened the Terminal Emulator, and pinged the Windows 10 VM. While it's pinging, I added a filter of "ICMP". In Wireshark, you can see the IP addresses of both Kali Linux and Windows 10 communicating with each other. 

*ICMP (Internet Control Message Protocol)* is used for error reporting and network diagnostics. It helps devices communicate issues such as unreachable destinations or expired packets. Also known as a ping scan.

![image](https://github.com/user-attachments/assets/a5c914e4-5b61-43c6-85aa-b969be612877)

In Wireshark on Kali Linux, I filtered the Windows 10 IP address and ran some nmap commands in Terminal. I started off a service scan of "nmap -sV <Windows 10 IP Address>" and there was no movement in Wireshark. 

Next in Terminal, I ran "nmap -Pn <Windows 10 IP Address>" and Wireshark tracked all of the movement that was occuring.
![image](https://github.com/user-attachments/assets/72a6ad92-05cf-4f23-9740-c7b7bc7180bf)

I tried to run an "HTTP" filter to see if there is any unsecured traffic on the network. There were no results for HTTP traffic.

![image](https://github.com/user-attachments/assets/6f6138d9-0696-4107-a009-f3e639bc8876)

I tried the same for a "TCP" filter to see if there is any traffic. This time, there was an abundence of traffic. 

![image](https://github.com/user-attachments/assets/9125ddcf-b6d2-4a22-8fa0-44103b591d65)



[Back to Home](https://github.com/EricFarrell/Cybersecurity-Portfolio/blob/6a83e9281d036567be6e5ed086086a2c0a63f5f6/README.md)

[Previous Project - Nmap & Zenmap](https://github.com/EricFarrell/Cybersecurity-Portfolio/tree/6a83e9281d036567be6e5ed086086a2c0a63f5f6/Nmap%20%26%20Zenmap)

[Next Project - pfSense](https://github.com/EricFarrell/Cybersecurity-Portfolio/tree/6a83e9281d036567be6e5ed086086a2c0a63f5f6/pfSense)

