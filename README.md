<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.By the end of this tutorial, you will be able to launch the osTicket help desk login page and End user osTicket Submission page. <br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

![image](https://github.com/user-attachments/assets/ddbb4903-1124-4882-bf3c-ff3da220f66d)

The osTicket site shows the required prerequisites (shown above).After creating the Virtual Machine in Microsoft Azure, we will download a and install these. 

<h2>Installation Steps</h2>

<p>
  
![image](https://github.com/user-attachments/assets/e398a658-d888-4b36-92bc-aff7744895f8)

</p>

<p>
Here is a file of what is needed to meet the Technical Requirements for osTicket. See the file  <a href="www.linkedin.com/in/annabel-salgado-69b67340">here</a>. We will go through installing each of these independently in the steps that follow. 
</p>
<br />

<p>
  
![image](https://github.com/user-attachments/assets/c3ee499a-489b-4df2-844a-364de6a45d24)

</p>
<p>
We will start with enabling Internet Information Services (IIS)
Follow the steps in the order numbered above. 

Click Programs and Features -> update applications -> Internet Information Services -> World Wide Web Services -> Application Development Features -> Make sure "CGI" is checked

</p>
<br />

<p>
  
![image](https://github.com/user-attachments/assets/f7d0a7bc-9f67-4b41-a79f-f1f9c9ef8be0)

</p>
<p>
From the “osTicket-Installation-Files” folder install PHPManagerForIIS_V1.5.0.msi and rewrite_amd64_en-US.msi
</p>
<br />

<p>
  
![image](https://github.com/user-attachments/assets/33281e2a-b32d-499f-bc16-44421e4bfa02)


</p>
<p>
Create C:\PHP
  which means you go file explorer -> this PC -> Windows C: -> create New Folder named PHP

Extract php-7.3.8-nts-Win32-VC15-x86.zip from the “osTicket-Installation-Files” folder into the PHP Folder 

</p>
<br />
<p>
  
![image](https://github.com/user-attachments/assets/c0f6d102-2b8d-44ac-bbe2-ccc3e00c4302)

</p>

<p>
From the “osTicket-Installation-Files” folder, install VC_redist.x86.exe and mysql-5.5.62-win32.msi
for mysql-5.5.62-win32.msi the steps are as follows: 
  Typical Setup at install -> Launch Configuration Wizard  -> Standard Configuration -> Set your Password

</p>
<br />

<p>
![image](https://github.com/user-attachments/assets/e12a4c06-ee20-4043-969d-73d642220f16)

![image](https://github.com/user-attachments/assets/8378396e-c0be-4c18-9938-96a51d38ef63)

</p>
<p>
Open IIS, select your server on the left hand side, click on PHP Manager
-Register PHP and select php-cgi.exe from the C:\PHP folder created earlier.
  
![image](https://github.com/user-attachments/assets/ff8c5997-4d6f-4ed0-8741-a2d06c3acb3e)

Return to IIS Manager Home select your server, then on the right hand panel click stop and then start. This reloads IIS with the changes you made. 

</p>
<br />
<p
  
![image](https://github.com/user-attachments/assets/c5ac2ea8-d4dd-4bfc-b83c-fed17ac355fa)

</p>
<p>
From the “osTicket-Installation-Files” folder, unzip “osTicket-v1.15.8.zip” and copy the “upload” folder into “c:\inetpub\wwwroot”

rename the "upload" folder to osTicket

Return to IIS Manager Home select your server, then on the right hand panel click stop and then start. This reloads IIS with the changes you made. 
 
</p>
<br />
<p>

![image](https://github.com/user-attachments/assets/e1110245-0043-489b-aff0-33e6e07a889e)

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
    Refresh the osTicket site in your browser, and you will see the extensions needed are now enabled (see below) . Do not click continue yet.

    ![image](https://github.com/user-attachments/assets/ce64cb6a-5df9-4255-9276-d84052292ede)


</p>
<br />
<p>
![image](https://github.com/user-attachments/assets/35ed50b9-54af-4b6f-a6e0-ba326972f0c4)

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
  
![image](https://github.com/user-attachments/assets/afd8bb17-f23e-4c39-a800-e4767635d22a)

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
![image](https://github.com/user-attachments/assets/b9293572-1c97-4fc9-b843-d9926bf35cde)

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

