<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>


- Enable extensions in IIS
- Add HeidiSQL 12.3.0
- Add MySQL 5.5.62
- Internet Information Services (IIS)
- Add all simple versions of x86 PHP up to v7.3.8
- Install osTicket v1.15.8
- Refresh the osTicket website in your browser and observe the changes made
- Clean up files for optimal use

<h2>Installation Steps</h2>

 (Create Virtual Machine in Azure)
Create a Resource Group
<p>
<img src="https://i.imgur.com/JwFKfgE.png"  height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create a Windows 10 Virtual Machine (VM) with 2-4 Virtual CPUs
When creating the VM, allow it to create a new Virtual Network (Vnet)
<p>
<img src="https://i.imgur.com/8yuDMDN.png"  height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

Install / Enable IIS in Windows WITH CGI
World Wide Web Services -> Application Development Features -> [X] CGI
<p>
<img src="https://i.imgur.com/Lj3ZyIE.png"  height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/lCG1ZVy.png"  height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From the Installation Files,
<img src="https://i.imgur.com/mctOLVm.png"  height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
<p> 
Download and install  the following
    PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)
    The Rewrite Module (rewrite_amd64_en-US.msi)

Create the directory C:\PHP


From the Installation Files,
 <img src="https://i.imgur.com/mctOLVm.png"  height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
<p> 
 download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP
<p>
   download and install VC_redist.x86.exe.
   download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
Typical Setup ->
Launch Configuration Wizard (after install) ->
Standard Configuration ->

Open IIS as an Admin

Register PHP from within IIS
<p>
<img src="https://i.imgur.com/mctOLVm.png"  height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

Reload IIS (Open IIS, Stop and Start the server)


Download and Install osTicket from the Installation Files Folder
<p>
<img src="https://i.imgur.com/J9u3k1F.png"  height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Extract and copy “upload” folder to c:\inetpub\wwwroot
Within c:\inetpub\wwwroot, Rename “upload” to “osTicket”

<p>
<img src="https://i.imgur.com/6qNZrbF.png"  height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Reload IIS (Open IIS, Stop and Start the server)

Go to sites -> Default -> osTicket
On the right, click “Browse *:80”

<p>
<img src="https://i.imgur.com/RzVjsMs.png"  height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

Go back to IIS, sites -> Default -> osTicket
Double-click PHP Manager
Click “Enable or disable an extension”
<p>
<img src="https://i.imgur.com/VTky94S.png"  height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Enable: php_imap.dll
Enable: php_intl.dll
Enable: php_opcache.dll
Refresh the osTicket site in your browse, observe the changes

Rename: ost-config.php
From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
To: C:\inetpub\wwwroot\osTicket\include\ost-config.php
<p>
<img src="https://i.imgur.com/s7XYptj.png"  height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Assign Permissions: ost-config.php
Disable inheritance -> Remove All
New Permissions -> Everyone -> All
<p>
<img src="https://i.imgur.com/CeRsXDh.png"  height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

Continue Setting up osTicket in the browser (click Continue)
Name Helpdesk
Default email (receives email from customers)


From the Installation Files, download and install HeidiSQL.
Open Heidi SQL
Create a new session, root/Password1
Connect to the session
Create a database called “osTicket”
<p>
<img src="https://i.imgur.com/J9u3k1F.png"  height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Continue Setting up osticket in the browser
MySQL Database: osTicket
MySQL Username: root
MySQL Password: Password1
Click “Install Now!”

<p>
<img src="https://i.imgur.com/rtIciQJ.png"  height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>


Congratulations, hopefully it is installed with no errors!
Browse to your help desk login page: http://localhost/osTicket/scp/login.php

<p>
<img src="https://i.imgur.com/NFBESuD.png"  height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
End Users osTicket URL:
http://localhost/osTicket/ 

Clean up
Delete: C:\inetpub\wwwroot\osTicket\setup
Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php

Notes:
Browse to your help desk login page: http://localhost/osTicket/scp/login.php  
End Users osTicket URL: http://localhost/osTicket/ 


</p>
<br />

