## ARP Poisoning
### Objective:


"Macchanger -r eth0" was used in Root Terminal on Kali Linux. This was used to randomly change the MAC address of the network interface.
It shows the current MAC address, the permanent MAC address, and the new MAC address. 

After doing an "ifconfig -a" it can be seen that the new MAC address was applied.
![image](https://github.com/user-attachments/assets/a466c9ff-c9bf-4b00-beee-5600c008fe1f)

"arpspoof -i eth0 -t 192.168.1.185 192.168.1.1"

- In this, the "eth0" is the network interface thats being used for the attack.

- 192.168.1.185 is the target IP address/the IP address I want to impersonate. 

- 192.168.1.1 is the gateway IP address. This can also be any other devices IP address whose traffic I'd want to intercept. 

** It's important to have permission before using tools like "arpspoof" in a network because unauthorized use is illegal. **
![image](https://github.com/user-attachments/assets/39a284bd-c02e-4a57-a69d-0907726f0893)
"arp -a" was used in Windows 10 Command Prompt. This is used to display ARP (Address Resolution Protocol) cache on the computer. 
ARP cache is a table that has mappings of IP addresses to MAC addresses on the local network.

In the first column under Internet Address, the gateway address has a Physical Address ending in "99-a4". 

I ran the same command after I changed the gateway address's Physical Address. It can now be seen that this address changed
and is now ending in "d0-5e".

![image](https://github.com/user-attachments/assets/17139fca-9370-486d-9dae-58e5428caaab)

-------------------------------------------------------------------------------------------
[Back to Home]([./README.md](https://github.com/EricFarrell/Cybersecurity-Portfolio?tab=readme-ov-file#cybersecurity-portfolio)) 

