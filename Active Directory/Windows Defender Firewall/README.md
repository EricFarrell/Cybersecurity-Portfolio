## Windows Defender Firewall with Advanced Security
### Objective
- Block Inbound Connections for all profiles.
- Enable Firewall for all profiles.
- Don't store LAN Manager hash values on password change.
- Allow NTLMv2 and Refuse LM & NTLM.
- Disable network sharing.
- Disable all services from the system.


On Windows Server 2019 I navigated to Windows Defender Firewall and changed the following options on the Domain Profile:

- Block Inbound Connections
- Enabled Firewall

  The same changes were made for the Private Profile, and Public Profile.

  (Domain Profile)
![image](https://github.com/user-attachments/assets/a9b3d61d-6830-40f0-a600-3a0d92ec9e9e)
  (Private Profile)
![image](https://github.com/user-attachments/assets/daeff71a-b6d6-4f9e-ada0-f144600f7788)
(Public Profile)
![image](https://github.com/user-attachments/assets/1623264e-ab90-43fa-835f-6ecc49116735)

I navigated to Inbound Rules and applied which ports I wanted to allow, while blocking all others.
![image](https://github.com/user-attachments/assets/cf65b68f-9205-4e5a-a1fd-a44131bcd5d5)

Some changes were made from Group Policy Management. I navigated to Manage Hash Values and Enaled a policy for "Network security: Do not store LAN Manager hash value on next password change."
![image](https://github.com/user-attachments/assets/83994400-bc92-4ead-bdc0-6cf24b412a61)


Within Local Security Policy, I went to security options and changed the LAn manager authentication level to allow only NTLMv2 and refuse LM and NTLM. 

This means that the system will only accept the most secure version of NTLM for logging in. It will block the use of the older and less secure ones.
This option improves security of the system by not allowing outdated protocols.
![image](https://github.com/user-attachments/assets/da83a25e-c675-4382-bf39-6c1cd5a800c4)



In advanced sharing settings, network discovery, along with file and printer sharing were disabled. 

Network discovery is when the current computer can see other network computers and devices and is visable to other network computers. 

file and printer sharing is when files and printers shared from that computer can be accessed by anyone on the same network.
![image](https://github.com/user-attachments/assets/272a690d-2747-4b2f-b1c6-1bc93aa86c65)


When navigating to the optional features, I was given this error stating I may not have 
the appropriate permissions to access that item. Which shows that my previous rule I disabled is effective.
![image](https://github.com/user-attachments/assets/ddf9ece1-3229-49d6-90f3-1708611d5d40)


Within Server Manager and its System Configurations, I diabled all services from the system. All services that are needed for Windows,
were unabled to be modified, which is why they are checked.
![image](https://github.com/user-attachments/assets/5f1999ee-cc14-489a-b902-03720d31c569)

