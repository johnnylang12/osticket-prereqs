<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />

<p>
<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Microsoft Azure (Virtual Machine)
- Heidi SQL
- osTicket Installation Files (Link Provided Below)

<h2>Step-by-Step Instructions</h2>

<h3>Step 1: Create Virtual Machine</h3>
Go to https://portal.azure.com/ to setup your Virtual Machine. Setup your virtual machine with Windows 10 Pro, version 22H2. Note, you will want to create a virtual machine with atleast 2 vcpus and 16 gbs of memory.
</p>
<br/>
<img src="https://i.ibb.co/pnzKYc0/VM.jpg" height="80%" width="60%" alt="VM"/>
<br/>
We will then connect to it with remote desktop app using the public ip address the vm is setup with. 
<br/>
</br>
<img src="https://i.ibb.co/vjJDcBv/VM-2.jpg" height="80%" width="60%" alt="VM"/>
<img src="https://i.ibb.co/yXX41Tx/Remote-Desktop.jpg" height="60%" width="40%" alt="remote desktop"/>
<br/>
Once you have connected to your virtual machine, let's move onto the next step.


<h3>Step 2: Install/Enable IIS in Windows</h3>
Access the "Control Panel" from start menu. Go to "Programs", then "Programs and Features". Then select "Turn Windows features on or off". On the pop up window, select the box for "Internet Information Services." Select appropriate boxes (See below).
</p>
<br/>
<img src="https://i.imgur.com/xsbKF1d.png" height="80%" width="60%" alt="Enable IIS"/>
<img src="https://i.ibb.co/Tt3vHjM/IIS-2.jpg" height="80%" width="60%" alt="Enable IIS"/>
<img src="https://i.ibb.co/xjL3fCZ/IIS-3.png" height="80%" width="60%" alt="Enable IIS"/>
<br/>
To make sure the IIS is working properly, go to a browser and search 127.0.0.1 It should look something like this.
<br/>
<br />
<img src="https://i.ibb.co/y4PxFt5/IIS-3.jpg" height="80%" width="60%" alt="IIS"/>


</p>
<h3> Step 3: Download & Install  </h3> Click the following link for the required downloads https://bit.ly/3WFRPdg. 
From the link provided, download and install PHPManagerForIIS_V1.5.0.msi and rewrite_amd64_en-US.msi and run through installation wizard.
Once installed, create a folder called PHP in C:\ drive then proceed to download file php-7.3.88-nts-Win32-VC15-x866.zip and extract it to C:\PHP.
<br/>
<br/>
<img src="https://i.ibb.co/RHNVfmf/PHP-2.jpg" height="50%" width="30%" alt="PHP"/>
<img src="https://i.ibb.co/dcLw7vh/PHP-3.jpg" height="50%" width="30%" alt="PHP"/>
<img src="https://i.ibb.co/7CF4Wvr/PHP.jpg" height="60%" width="40%" alt="PHP"/>


</p>
<h3> Step 3: Install MySQL  </h3> Click the following link for the required downloads https://bit.ly/3WFRPdg. 
From the link provided, download and install VC_redist.x86.exe and mysql-5.5.62-win32.msi and run through installation wizard.
For MySQL we will run it by Typical Setup -> select the checkbox "Launch MySQL Instance Configuration Wizard" -> Standard Configuration -> Install As Windows Service
<br/>
<br/>
We will set New root password with: Password1
<br />
<img src="https://i.ibb.co/9YkHcry/MySQL.jpg" height="60%" width="40%" alt="MySQL"/>

then Execute process
<img src="https://i.ibb.co/12xR2wk/MySQL-2.jpg" height="60%" width="40%" alt="MySQL"/>


<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
