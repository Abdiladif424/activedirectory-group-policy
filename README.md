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
