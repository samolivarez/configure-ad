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
Next, we are going to test connectivity between Client-1 VM and DC-1 VM but first need to open up the Firewall in DC-1 to be able to receive ICMP traffic which is the protocol that the "ping" command uses. To do this as the above image shows we need to go to "Windows Defender Firewall with Advanced Security" which is found by just going to the computer's start menu search then once there click on "inbound rules.
</p>
<br /># configure-ad

<p>
<img src="https://i.imgur.com/8yIpA0F.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next, within the "inbound rules" page under the Protocol column find ICMPv4 then to the left side of the screen find "Core Networking Diagnostics-ICMP Echo Request" and enable both rules.
</p>
<br /># configure-ad

<p>
<img src="https://i.imgur.com/L0217OB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next, after having opened up a command line in Client-1 VM and typing the "ping -t" command followed by DC-1's private IP address next to the command which creates a perpetual ping we see that DC-1 IS replying to Client-1's ping command which confirms connectivity between DC-1 and Client-1 VM's.
</p>
<br /># configure-ad


<p>
<img src="https://i.imgur.com/I0jNT7R.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next, we begin the installation of Active Directory which starts off with going to: DC-1 VM>Windows Server Manager>Add roles & features>then on the "select a server" tab make sure the proper server is chosen as the above image shows we have our DC-1 server selected because that is where we are installing Active Direcory.
</p>
<br /># configure-ad

<p>
<img src="https://i.imgur.com/NAXLcdG.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next, in the "Add roles & features" wizard set-up screen that says "Add features that are required for Active Directory Domain Services?" make sure to click the "Add Features" tab and click the "include management tools" box as well.
</p>
<br /># configure-ad

<p>
<img src="https://i.imgur.com/Qm9oNI6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next, in the "Add roles & features" wizard set-up process in the screen that says "Select Server Roles" make sure the "Active Directory Domain Services" box is checked.
</p>
<br /># configure-ad

<p>
<img src="https://i.imgur.com/EQ2YPMB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next, back on the "Windows Server Manager" dashboard go to the yellow triangle alert on the upper right>click "Promote this server to a domain controller". This is how we finish installing Active Directory on this server and turn it into a Domain Controller.
</p>
<br /># configure-ad

<p>
<img src="https://i.imgur.com/EOfk3JJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next, in the "Active Directory Domain Services Configuration Wizard" select the "Add new forrest" tab>specify the root domain name for our selected server which in this case we will name "mydomain.com". 
</p>
<br /># configure-ad

<p>
<img src="https://i.imgur.com/JUPlgNZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next, in the "Active Directory Wizard" set-up process; if the previous steps were done correctly; in the "Prerequisites Check" screen that appears there should now be a "green arrow" followed by the message "All prerequisite checks passed. Click "install" to begin installation" as the above image shows. Press "install".
</p>
<br /># configure-ad

<p>
<img src="https://i.imgur.com/6oIEPc7.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once Active Directory is finished installing we can now go to our newly installed Active Directory Users & Computers>mydomain.com and create as needed "organizational units" inside Active Directory. "Organizational units" amount to basically "folders" we can create inside Active Directory. As the above image shows we have created 2 organizational Units called _EMPLOYEES AND _ADMINS which help us to group/separate employees and admins.
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
