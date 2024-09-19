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

![image](https://github.com/user-attachments/assets/ddbb4903-1124-4882-bf3c-ff3da220f66d)


<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Here is a file of what is needed to meet the Technical Requirements for osTicket. See the file  <a href="www.linkedin.com/in/annabel-salgado-69b67340">here</a>
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
We will start with enabling Internet Information Services (IIS)
Follow the steps shown above
Programs and Features -> update applications -> Internet Information Services -> World Wide Web Services -> Application Development Features -> Make sure "CGI" is checked

</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From the “osTicket-Installation-Files” folder install PHPManagerForIIS_V1.5.0.msi and rewrite_amd64_en-US.msi
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create C:\PHP
  which means you go file explorer -> this PC -> Windows C: -> create New Folder named PHP

Extract php-7.3.8-nts-Win32-VC15-x86.zip file into the PHP Folder 

</p>
<br />
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
From the “osTicket-Installation-Files” folder, install VC_redist.x86.exe and mysql-5.5.62-win32.msi
for mysql-5.5.62-win32.msi the steps are as follows: 
  Typical Setup at install -> Launch Configuration Wizard  -> Standard Configuration -> Set your Password

</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Open IIS, select your server on the left hand side, click on PHP Manager
-Register PHP and select php-cgi.exe from the C:\PHP folder created earlier.

Return to IIS Manager Home select your server, then on the right hand panel click stop and then start. This reloads IIS with the changes you made. 

</p>
<br />
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From the “osTicket-Installation-Files” folder, unzip “osTicket-v1.15.8.zip” and copy the “upload” folder into “c:\inetpub\wwwroot”

rename the "upload" folder to osTicket

Return to IIS Manager Home select your server, then on the right hand panel click stop and then start. This reloads IIS with the changes you made. 
 
</p>
<br />
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Open osTicket
  in the IIS click on your server -> sites ->default -> osTicket -> Browse *.80

  - You will see that some needed extensions are disabled.
  - Go back to IIS, sites -> Default -> osTicket
    Double-click PHP Manager
    Click “Enable or disable an extension”
    Enable: php_imap.dll
    Enable: php_intl.dll
    Enable: php_opcache.dll
    Refresh the osTicket site in your browser, and you will see the extensions needed are now enabled. Do not click continue yet. 

</p>
<br />
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

Assign Permissions: ost-config.php
Disable inheritance -> Remove All
New Permissions -> Everyone -> All


</p>
<br />
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Fill in the Highlighted fields 
Name of the Helpdesk
Email for the helpdesk
MySQL Database: osTicket
MySQL Username: root
MySQL Password: password you created
DON'T Click INSTALL NOW
  
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From the “osTicket-Installation-Files” folder, install HeidiSQL 
Open Heidi SQL
Create a new session, root/ password you created
Connect to the session
Create a database called “osTicket”

now on your osTicket Browser click Install Now! 

</p>
<br />


<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

if done correctly your help desk login is http://localhost/osTicket/scp/login.php

The end user login is http://localhost/osTicket/
</p>
<br />

