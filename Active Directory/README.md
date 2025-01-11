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
 ![image](https://github.com/user-attachments/assets/3dd76cde-f220-4ecb-a716-10b391cf6705)
![image](https://github.com/user-attachments/assets/c79853a3-edc4-4634-a317-4b19763bbc01)


 Within Windows Server 2019, I created a root domain using my last name.
![image](https://github.com/user-attachments/assets/e9d432f4-d663-469f-b62f-370ec9adf9f9)

I then created an organizational unit (OU) named CYB-515.
![image](https://github.com/user-attachments/assets/b76ab1f3-7449-4d05-9e24-4be228b245ae)

Within the Administrator Command Prompt, I created 10 user accounts to put into the OU that was just created by using the following commands:

**dsadd user "cn=John Doe4,OU=CYB-515,dc=farrell,dc=com" -samid Doe4J -upn Doe4J@farrell.com -fn John -ln "Doe 4" -display "John Doe4" -disabled no -pwd "Password1" -mustchpwd no**


![image](https://github.com/user-attachments/assets/f46579a7-62d5-4194-9c35-840f99ad7acb)

Within Administrator Windows PowerShell, I also created five groups that were placed into the OU.
![image](https://github.com/user-attachments/assets/31950335-ebca-45d1-a4c8-a7b60e0fb25e)

Password policies within Active Directory for each of the five groups were implemented. Along with a "gpupdate /force" to update Group Policy Settings immediately.
![image](https://github.com/user-attachments/assets/9e70e506-db82-4b93-9062-3969a2a8db0f)


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
- Join Windows 11 VM to the domain.
- Disable automatic administrative logon.

In windows 11, I navigated to the settings/system/about and selected Domain. I was then able to change the domain of the system by simply entering my domain name of "whatever.com". If I wanted to put this system into a work group, I would be able to do so from the same properties page.
![windows 11 VM domain join](https://github.com/user-attachments/assets/709508d2-c95c-4fbd-863e-b9d8701f92b4)

In Windows Server 2019, I navigated to Local Security Policy/Local Policies/Security Options and "Disabled" "Recovery console: Allow automatic adminsitrative logon". Once applied, I was prompted to enter the password of
the account that's to be configured.

I then restarted the Windows Server 2019 VM and was presented with a bitLocker drive encryption screen prompting me to enter the password to unlock the drive.
![image](https://github.com/user-attachments/assets/6d8675cd-28db-4188-8d67-a678c181e14b)
![image](https://github.com/user-attachments/assets/a8e85505-360d-44d7-aa15-9cd9c56e9679)

