<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Configuring Active Directory within Azure VMs</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>Deployment and Configuration Steps</h2>

In Microsoft Azure, setup a Domain Controller<br />
Create a Resource Group - "Active-Directory-Lab"
<img width="788" height="452" alt="image" src="https://github.com/user-attachments/assets/a7da11c0-b442-472b-bf0c-de963c90e06b" />

Create a Virtual Network and Subnet
<img width="772" height="726" alt="image" src="https://github.com/user-attachments/assets/94aea8b5-fc70-4634-8816-ad503a62a557" />

Create the Domain Controller VM (Windows Server 2022) named “DC-1”<br />
After VM is created, set Domain Controller’s NIC Private IP address to be static<br />
<img width="754" height="826" alt="image" src="https://github.com/user-attachments/assets/aba121a7-c116-4e6b-a219-7e1afe31ddac" />

Set DC-1's NIC Private IP address to STATIC<br />
<img width="570" height="735" alt="image" src="https://github.com/user-attachments/assets/9b23623a-f4e4-42a0-a243-1fdbe1e3a0d4" />

Setup Client-1 in Azure
Create the Client VM (Windows 10) named “Client-1”
<img width="634" height="771" alt="image" src="https://github.com/user-attachments/assets/e103237c-9e4d-4bea-bcad-05b6b2eb2b05" />


Attach it to the same region and Virtual Network as DC-1
After VM is created, set Client-1’s DNS settings to DC-1’s Private IP address
<img width="544" height="703" alt="image" src="https://github.com/user-attachments/assets/4e9a77e0-aa69-444f-9433-703f481e7f5f" />


Restart Client-1 from the Azure Portal, login and attempt to DC-1's private IP Address<br/>
If the ping succeeded, you have successfully configured Client-1 VM to use the DC as its DNS server.
