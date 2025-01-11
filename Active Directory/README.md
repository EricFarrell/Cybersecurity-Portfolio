 ## Active Directory
 ### Objectives
- Update the system.
- Create a root domain.
- Create an Organizational Unit (OU) and add 10 users to it.
- Create 5 groups within the OU.
- Assign users to appropriate groups.
- Implement password policies for each of the 5 groups.
- Restrict login hours for each department to 9 AM – 8 PM, Monday to Friday.
- Grant the Human Resources department read, write, and modify all properties of Active Directory user information.
- Allow the IT department to reset passwords and enforce password changes on the next login for all user accounts.

 
 Before making any changes, I went to the settings and ensured the system is up to date on the latest update. 
 ![image](https://github.com/user-attachments/assets/7a10b3ba-c9ad-4d7d-bd7b-1075db672c4f)

![image](https://github.com/user-attachments/assets/05daecfa-4835-4976-8c96-e4219f51656c)



 Within Windows Server 2019, I created a root domain using my last name.
![image](https://github.com/user-attachments/assets/e9d432f4-d663-469f-b62f-370ec9adf9f9)

I then created an organizational unit (OU) named CYB-515.
![image](https://github.com/user-attachments/assets/b76ab1f3-7449-4d05-9e24-4be228b245ae)

Within the Administrator Command Prompt, I created 10 user accounts to put into the OU that was just created by using the following commands:

**dsadd user "cn=John Doe4,OU=CYB-515,dc=farrell,dc=com" -samid Doe4J -upn Doe4J@farrell.com -fn John -ln "Doe 4" -display "John Doe4" -disabled no -pwd "Password1" -mustchpwd no**


![image](https://github.com/user-attachments/assets/f46579a7-62d5-4194-9c35-840f99ad7acb)

Within Administrator Windows PowerShell, I also created five groups that were placed into the OU.
![image](https://github.com/user-attachments/assets/31950335-ebca-45d1-a4c8-a7b60e0fb25e)

Password policies within Active Directory for each of the five groups were implemented. Along with The gpupdate /force command in Administrator Windows Powershell refreshes and reapplies all Group Policy settings immediately, ensuring both user and computer policies are updated regardless of changes.
![image](https://github.com/user-attachments/assets/9e70e506-db82-4b93-9062-3969a2a8db0f)


In the following three screenshots, I placed three users into the Human Resources Department group, three other users in the Research and Developement group, and four other users in the IT Department group.
![image](https://github.com/user-attachments/assets/0fb00a0d-ff13-4ce6-906f-8bc6c0ccddc4)
![image](https://github.com/user-attachments/assets/c9bb1337-2715-477f-a9f2-14b891421ac8)
![image](https://github.com/user-attachments/assets/1cd31579-669d-4226-af6c-cbf81c120177)



For the Research and Developement Department group, I limited this departments logon hours from 9AM to 8PM Monday through Friday.
In the following two screenshots, I enabled "Disconnect clients when logon hours expire". 
Along with The gpupdate /force command in Administrator Windows Powershell refreshes and reapplies all Group Policy settings immediately, ensuring both user and computer policies are updated regardless of changes.
![image](https://github.com/user-attachments/assets/c9e84a09-da17-4a5c-a663-45549da4ca4a)
![image](https://github.com/user-attachments/assets/0f51ae8c-c8a2-4985-807e-f1498aef1f1c)
![image](https://github.com/user-attachments/assets/f115310b-e7b4-4e55-a6bf-fe899f1dbce5)


I gave control to the Human Resources Department to Read, Write, and Write all Properties of all active directory user account information by using the Active Directory Control Wizard.
![image](https://github.com/user-attachments/assets/63e39bc3-a22c-4c73-9b96-10af28d796c6)


I gave access the IT Department group the ability to reset passwords and force a password change at the next log-on for all active directory user accounts.
![image](https://github.com/user-attachments/assets/4301c708-be0e-44b0-991d-6a9634e1d2ea)



For the following user "John Doe 4" since they are apart of the Human Resources Department, it shows that they are able to edit a user account in Active Directory. In the screenshot, The user of "John Doe 5" is being modified.
![image](https://github.com/user-attachments/assets/c2573c9e-eadf-43a6-a226-262e8ba2cd1a)


For the users apart of the IT department, they can not edit user accounts in Active Directory, but they are able to change passwords of all other users.
![image](https://github.com/user-attachments/assets/666577d5-712b-4ddd-a5c9-29fcd5f0c6e9)



### Next Objective
- Join Windows 11 VM to the domain.
- Disable automatic administrative logon.

In windows 11, I navigated to the settings/system/about and selected Domain. I was then able to change the domain of the system by simply entering my domain name of "whatever.com". If I wanted to put this system into a work group, I would be able to do so from the same properties page.
![windows 11 VM domain join](https://github.com/user-attachments/assets/709508d2-c95c-4fbd-863e-b9d8701f92b4)

In Windows Server 2019, I navigated to Local Security Policy/Local Policies/Security Options and "Disabled" "Recovery console: Allow automatic adminsitrative logon". Once applied, I was prompted to enter the password of
the account that's to be configured.

I then restarted the Windows Server 2019 VM and was presented with a bitLocker drive encryption screen prompting me to enter the password to unlock the drive.
![image](https://github.com/user-attachments/assets/6d8675cd-28db-4188-8d67-a678c181e14b)
![image](https://github.com/user-attachments/assets/a8e85505-360d-44d7-aa15-9cd9c56e9679)

