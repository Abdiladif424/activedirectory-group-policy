<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1> Group Policy and Managing Accounts  </h1>
This tutorial outlines how to configure the account lockout policy in Active Directory and manage accounts within Azure Virtual Machines.

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Group Policy Management Console
- Active Directory Domain Services
  

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2> Configuration Steps</h2>

1. Open the Group Policy Management Console (GPMC)
- Log in to the virtual machine with the Group Policy Management Console installed (typically, a Domain Controller).
- Click Start, and type gpmc.msc in the search box, then press Enter. This opens the Group Policy Management Console.

<img width="2559" height="1439" alt="Screenshot 2025-07-21 111848" src="https://github.com/user-attachments/assets/1ff758a2-c652-48c5-92e3-affada44611b" />

2.  Create or Edit a Group Policy Object (GPO)
- In the GPMC, navigate to the Group Policy Objects section.
- Right-click Group Policy Objects and select New to create a new GPO, or right-click an existing GPO and select Edit to modify it.
- Give the new GPO a descriptive name if you're creating a new one

<img width="2559" height="1439" alt="Screenshot 2025-07-21 112440" src="https://github.com/user-attachments/assets/2f0b72f6-0dcf-4c5e-93d5-5d29dc0b19d1" />

3. Navigate to the Account Lockout Policy Settings
- In the Group Policy Management Editor, expand the following:
  Computer Configuration > Policies > Windows Settings > Security Settings > Account Policies > Account Lockout Policy.

<img width="2559" height="1439" alt="Screenshot 2025-07-21 120835" src="https://github.com/user-attachments/assets/82902107-4999-4208-b5ca-772dfc8e5440" />

4.  Configure Account Lockout Policy Settings
You will see three primary settings that you need to configure:

-Account Lockout Duration:
- Definition: The time in minutes that an account remains locked before it is automatically unlocked.
- Configuration: Double-click on this setting, select Define this policy setting, and then set the duration (e.g., 30 minutes).
  
-Account Lockout Threshold:
- Definition: The number of failed logon attempts that will trigger an account lockout.
- Configuration: Double-click on this setting, select Define this policy setting, and then set the threshold (e.g., 3 invalid attempts).
  
-Reset Account Lockout Counter After:
- Definition: The time in minutes after which the failed logon attempts counter is reset to 0, assuming there are no additional failed logon attempts.
- Configuration: Double-click on this setting, select Define this policy setting, and then set the time (e.g., 15 minutes).

<img width="2559" height="1439" alt="Screenshot 2025-07-21 121211" src="https://github.com/user-attachments/assets/a31d1363-cddb-45dd-8042-fd381e87ff2c" />

5. Update Group Policy
- You can wait for the Group Policy to propagate automatically, or you can force an update immediately.
- On a client machine or server, open Command Prompt and type gpupdate /force, then press Enter.

  <img width="2559" height="1438" alt="Screenshot 2025-07-21 122114" src="https://github.com/user-attachments/assets/a7a60dd1-8be8-4621-b178-b825e1d188f0" />

6. By following these steps, you can successfully configure an account lockout policy in Active Directory using Group Policy.
- We can now attempt to log in with it 6 times with a bad password
- We will then get a user account lockout message

<img width="2559" height="1439" alt="Screenshot 2025-07-21 122748" src="https://github.com/user-attachments/assets/5af5ed24-0756-455b-b6c8-13512e3773d2" />

7. Observe that the account has been locked out within Active Directory
- Go to Active Directory Users and Computers
- then right click on mydomain.com and click on find
- you will then see the user account you want to unlock 

<img width="2559" height="1439" alt="Screenshot 2025-07-21 123225" src="https://github.com/user-attachments/assets/e1cbfcf3-ead4-4c80-bcae-7291427eeffe" />

8. 




