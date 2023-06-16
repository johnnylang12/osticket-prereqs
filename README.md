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
<br/>
<img src="https://i.ibb.co/12xR2wk/MySQL-2.jpg" height="60%" width="40%" alt="MySQL"/>
<br/>
<br/>
Now that we have everything installed we will then open the program as administrator (this is important!)
<br/>
<br/>
<img src="https://i.ibb.co/kQDq7nt/IIS-4.jpg" height="60%" width="40%" alt="IIS"/>
<br/>
<br/>
Next let's register PHP from IIS. Select the php path C:\PHP and select the file php-cgi.exe then restart the server.
<br/>
<br/>
<img src="https://i.ibb.co/yqGyh75/IIS-5.jpg" height="80%" width="60%" alt="IIS"/>
<br/>
<img src="https://i.ibb.co/Lzm6v0y/IIS-6.jpg" height="80%" width="60%" alt="IIS"/>
<br/>
<img src="https://i.ibb.co/tMpZLGz/IIS-7.jpg" height="80%" width="60%" alt="IIS"/>
<br/>
<img src="https://i.ibb.co/6tmz5TZ/IIS-8.jpg" height="80%" width="60%" alt="IIS"/>
<br/>
<p>

<h3> Step 4: Install osTicket  </h3> Click the following link for the required downloads https://bit.ly/3WFRPdg. 
From the link provided, download and install osTicket v1.15.8. <br/>
Inside installation folder, copy "upload" folder to path c:\inetpub\wwwroot and rename the folder to "osTicket"
<br/>
<br/>
<img src="https://i.ibb.co/v3fF92C/IIS-9.jpg" height="80%" width="60%" alt="IIS"/>
Restart IIS again and on the left hand side, go to Sites -> Default -> osTicket and on the right, click “Browse *:80”
<br/>
<img src="https://i.ibb.co/NKrX48X/IIS-10.jpg" height="80%" width="60%" alt="IIS"/>
We can see some extensions are not enabled on osTicket
<img src="https://i.ibb.co/GJ06L84/osTicket.jpg" height="80%" width="60%" alt="osTicket"/>
Let's enable some of the extensions. Go back to PHP manager, on the bottom click "Enable or disable an extension" <br/>
We want to enable php_imap.dll, php_intl.dll, and php_opcache.dll
<br/>
<br/>
<img src="https://i.ibb.co/yqGyh75/IIS-5.jpg" height="80%" width="60%" alt="IIS"/>
<img src="https://i.ibb.co/5134Rxv/IIS-11.jpg" height="80%" width="60%" alt="IIS"/>
<img src="https://i.ibb.co/qM3dYRP/IIS-12.jpg" height="80%" width="60%" alt="IIS"/>
Now we need to rename file "ost-sampleconfig.php" to "ost-config.php" in path c:\inetpub\wwwroot\osTicket\include <br/>
We will need to add permissions to the file. <br/>
Right click "ost-config.php" file -> properties -> Security -> Advanced -> Disable inheritance -> Remove all inherited permissions from this object. <br/>
Now we will add new permissions
<br/>
<br/>
Click Add -> Select a principal. Then type "everyone" in the box and click ok. 
<img src="https://i.ibb.co/CVr0r80/IIS-13.jpg" height="80%" width="60%" alt="IIS"/>
<img src="https://i.ibb.co/n1JvLTQ/IIS-14.jpg" height="80%" width="60%" alt="IIS"/>
Make sure "Full control" is checked then press ok -> apply -> ok
<img src="https://i.ibb.co/9HVBB1R/IIS-15.jpg" height="80%" width="60%" alt="IIS"/>
<img src="https://i.ibb.co/pJKtvDR/IIS-16.jpg" height="80%" width="60%" alt="IIS"/>
<p>

<h3> Step 5: Install HeidiSQL </h3> Click the following link for the required downloads https://bit.ly/3WFRPdg. 
From the link provided, download and install HeidiSQL_12.3.0.6589_Setup.exe and run through installation wizard.<br/>
Program will start once installation is finished. <br/><br/>

Click new, we want to make sure username is root and password is Password1. Click open.
<img src="https://i.ibb.co/9HkGpDb/Heidi.jpg" height="80%" width="60%" alt="IIS"/>
<img src="https://i.ibb.co/Qk2Wmb0/Heidi2.jpg" height="80%" width="60%" alt="IIS"/>
<br/>
Now we will create a database within HeidiSQL. <br/>
Right click on the left side -> Create new -> Database. We will name this "osTicket"
<img src="https://i.ibb.co/fpqqz21/Heidi3.jpg" height="80%" width="60%" alt="IIS"/>
<img src="https://i.ibb.co/k5mrhxk/Heidi4.jpg" height="80%" width="60%" alt="IIS"/>
<br/>
<br/>
Now back on osTicket we can fill out and complete the setup.
<img src="https://i.ibb.co/HGKrHmK/os-Ticket2.jpg" height="60%" width="60%" alt="IIS"/>

We just need to clean up now. We want to delete the "setup" folder in path c:\inetpub\wwwroot\osTicket. <br/>
We also want to set the permissions back to read only. in the ost-config.php file. 
<img src="https://i.ibb.co/Lz6690f/IIS-17.jpg" height="80%" width="60%" alt="IIS"/>
<img src="https://i.ibb.co/sbnT8Dg/IIS-18.jpg" height="80%" width="60%" alt="IIS"/>
<br/>
<br/>
Last step is to just log in! Go to localhost/osTicket/scp/login.php and login!
<img src="https://i.ibb.co/NNvSFRD/os-Ticket3.jpg" height="80%" width="60%" alt="osTicket"/>

Congrats! You have now successfully installed and setup osTicket!


</p>

