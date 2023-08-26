<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Computer)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Set up couple of VM's in  Azure (DC-1 our Domain Controller & Client-1)
- Install Active Directory on DC-1 VM
- Promote DC-1 to Domain Controller
- Point Client-1 VM to DNS of Domain Controller DNS
- Join Client-1 VM to Domain Controller VM DC-1
  

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://i.imgur.com/nhSEiZk.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
To begin this Configuring Active Directory tutorial the above image shows we first have created our first VM from inside Microsoft Azure called DC-1 which will eventually will be promoted to a Domain  Controller.
</p>
<br />

<p>
<img src="https://i.imgur.com/uBYJjrz.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next, the above image shows the second created VM called Client-1 which will eventually be pointed to and then joined to DC-1 VM (our Domain Controller). 
</p>
<br />

<p>
<img src="https://i.imgur.com/PAqQXGO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next, the above image shows we are editing the IP Configuration of DC-1 from Dynamic to Static.
</p>
<br /># configure-ad

<p>
<img src="https://i.imgur.com/5Qm2FdU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next, we are going to test connectivity between Client-1 VM and DC-1 VM but first need to open up the Firewall in DC-1 to be able to receive ICMP traffic which is the protocol that the "ping" command uses. To do this as the above image shows we need to go to "Windows Defender Firewall with Advanced Security" which is found by just going to the computer's start menu search.
</p>
<br /># configure-ad

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br /># configure-ad

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br /># configure-ad

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br /># configure-ad

