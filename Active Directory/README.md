 ## Active Directory
 Description: 

 
 Before making any changes, I went to the settings and ensured the system is up to date on the latest update. 
 ![image](https://github.com/user-attachments/assets/3dd76cde-f220-4ecb-a716-10b391cf6705)
![image](https://github.com/user-attachments/assets/c79853a3-edc4-4634-a317-4b19763bbc01)


 Within Windows Server 2019, I created a root domain using my last name.
![image](https://github.com/user-attachments/assets/77223026-b46d-4011-b51d-45b5133bc67d)
I then created an organizational unit (OU) named CYB-515.
![image](https://github.com/user-attachments/assets/36a0b062-4501-4b0b-95af-13f87da0f4d7)
Within the Administrator Command Prompt, I created 10 user accounts to put into the OU that was just created.
![image](https://github.com/user-attachments/assets/c0c66c75-9a68-4525-8ee6-b5b8e3be4e81)
Within Administrator Windows PowerShell, I also created five groups that were placed into the OU.
![image](https://github.com/user-attachments/assets/3cb50857-cef4-4212-a5d3-8e75281107c2)
Password policies within Active Directory for each of the five groups were implemented.
![image](https://github.com/user-attachments/assets/636c66b4-e326-4c27-a0f7-0e1a4ca9817a)

In the following three screenshots, I placed three users into the Human Resources Department group, three other users in the Research and Developement group, and four other users in the IT Department group.
![image](https://github.com/user-attachments/assets/60ac6c7d-58fe-4e8b-8e1f-4c716e134202)
![image](https://github.com/user-attachments/assets/345ab818-aee1-4dea-8362-d9ca2f82e453)
![image](https://github.com/user-attachments/assets/64ec632a-e9c1-46c3-ae4a-bb65b50cf846)

For the Research and Developement Department group, I limited this departments logon hours from 9AM to 8PM Monday through Friday.
In the following two screenshots, I enabled to "disconnect clients when logon hours expire". 
Along with The gpupdate /force command in Windows Server 2019 refreshes and reapplies all Group Policy settings immediately, ensuring both user and computer policies are updated regardless of changes.
![image](https://github.com/user-attachments/assets/0d22d6df-a09b-44a3-890c-3aef4056abe8)
![image](https://github.com/user-attachments/assets/5d7d965d-15aa-4361-8f35-b127f31edd03)

I gave control to the Human Resources Department to Read, Write, and Write all Properties of all active directory user account information.
![image](https://github.com/user-attachments/assets/23751392-f401-4ca6-8af6-52e9c253b354)

I gave access the IT Department group the ability to reset passwords and force a password change at the next log-on for all active directory user accounts.
![image](https://github.com/user-attachments/assets/444377c4-4ccc-4c07-943f-398d23d4e411)


For the following user "John Doe 4" since they are apart of the Human Resources Department, it shows that they are able to edit a user account in Active Directory.
![image](https://github.com/user-attachments/assets/1e023cf9-52dc-4db9-9f0c-1994f08ed71f)

For the users apart of the IT department, they can not edit user accounts in Active Directory, but they are able to change passwords of all other users.
![image](https://github.com/user-attachments/assets/2cfc9ee7-19c7-4761-a62f-8db2a707de8b)


### Next Objective
Join Windows 11 VM to the domain.

In windows 11, I navigated to the settings/system/about and selected Domain. I was then able to change the domain of the system by simply entering my domain name of "whatever.com". If I wanted to put this system into a work group, I would be able to do so from the same properties page.
![windows 11 VM domain join](https://github.com/user-attachments/assets/709508d2-c95c-4fbd-863e-b9d8701f92b4)

In Windows Server 2019, I navigated to Local Security Policy/Local Policies/Security Options and "Disabled" "Recovery console: Allow automatic adminsitrative logon". Once applied, I was prompted to enter the password of
the account that's to be configured.

I then restarted the Windows Server 2019 VM and was presented with a bitLocker drive encryption screen prompting me to enter the password to unlock the drive.
![image](https://github.com/user-attachments/assets/6d8675cd-28db-4188-8d67-a678c181e14b)
![image](https://github.com/user-attachments/assets/a8e85505-360d-44d7-aa15-9cd9c56e9679)

[Back to Home](https://github.com/EricFarrell/Cybersecurity-Portfolio/blob/6a83e9281d036567be6e5ed086086a2c0a63f5f6/README.md)

[Previous Project - ARP Poisoning](https://github.com/EricFarrell/Cybersecurity-Portfolio/tree/c824fca66a0acaaff5faa3e1339938c3491e7a95/ARP%20Poisoning)

[Next Project - Windows Defender Firewall](https://github.com/EricFarrell/Cybersecurity-Portfolio/tree/6a83e9281d036567be6e5ed086086a2c0a63f5f6/Active%20Directory/Windows%20Defender%20Firewall)
