<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Deploy VMs and ensure connectivity
- Install Active Directory and Create Administrators
- Connect Client-1 to New Domain
- Create Users to Access Client-1

<h2>Deployment and Configuration Steps</h2>

<h3>Virtual Machine Setup</h4>

<h4> Virtual Machine Details</h4>

1.) To configure and setup an Active Directory within Azure, you will first need to setup two VMs with the following details in each.
  * For VM1 (DC-1 for the Domain Controller), create a VM running Windows Server 2022
  * For VM2 (Client-1 for the client connecting to the AD), create a VM Rrunning Windows 10 Pro
  *Use the same resource group for both VMs.

2.) Next, you will need to set the IP adress for DC-1 to "Static", to do this, acess the networking screen for VM1 on Azure, from there navigate towards "IP Configurations". Now, click the "ipconfig1" section, from there, navigate to the assigment section, click "Static" and save. All screens pictured below.

![image](https://github.com/user-attachments/assets/e1ce0c4c-a801-47c5-acba-36a5514dc345)

![image](https://github.com/user-attachments/assets/53fc7887-574c-45a9-9ac5-072898bdc1a3)

![image](https://github.com/user-attachments/assets/9cdf6c6d-2b10-4162-b7bc-a34aaa789ae6)

<h3>Client to Domain Connection</h3>

<h4>Ping to DC-1</h4>
3.) Once you are done configuring the IP of DC-1, log into the Client-1 VM through Remote Desktop Connection, open the command prompt. From here, attempt to ping to the private IP address of DC-1. You will notice that this will not work and your screen should be similar to the one pictured below. To fix this, log back into DC-1 vIA RDC. 

![image](https://github.com/user-attachments/assets/236b2604-552f-47b9-9173-b99bbf1eac8f)

4.) Once logged onto DC-1, the Server Manager will immediately open and look similar to what is pictured below.

![image](https://github.com/user-attachments/assets/1efca298-b0be-4ae3-96cb-e2de6a6f9107)

5.) From here, click the start tab, and go to Windows Firewall, disable all options to ensure connection is possible. Log back into Client-1 and attempt to ping againt, this time successfully, seeing your command prompt look like this as shown below.

![image](https://github.com/user-attachments/assets/2a9b0edf-e91a-4ab2-92c2-ea312c1345e6)

<h3>Active Directory Setup and Installation</h3>
