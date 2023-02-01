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

- Microsoft Azure Virtual Machine (VM) under tenant
- Install IIS (with CGI)
- Install PHP Manager and Rewrite Module
- Install and configure MySQL
- Install and configure HeidiSQL
- Install osTicket

<h2>Microsoft Azure Steps</h2>
<p>
Navigate to portal.azure.com and search for Virtual machines.
</p>
<p>
<img src="https://i.imgur.com/E6VDlGR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
Click the blue drop-down menu and click "Azure Virtual Machine".
</p>
<p>
<img src="https://i.imgur.com/H3eC2M2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
Name your virtual machine "vm-osTicket", select Windows 10 Pro for the image, select a size with 4 vCPUs, and create a username and password to use to connect to your VM.
</p>
<p>
<img src="https://i.imgur.com/ylZvWBy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/CQUicVo.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
Go back to your virtual machines and copy the IP address.
</p>
<p>
<img src="https://i.imgur.com/1a8VSCv.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
Search "remote desktop connection" in your search bar and open it. Select "Show options", paste the IP you copied from your virtual machine and type the username you set for it, click "Connect". A window will pop up asking for the password, hit enter and another window will pop up, just click "Yes."
</p>
<p>
<img src="https://i.imgur.com/VHeLTzI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<h2>Inside your Virtual Machine</h2>

<p>
Once inside your virtual machine, search for your control panel and open it. Click "Programs", then click "Turn Windows features on or off" with the shield in front of it. Navigate down to "Internet Information Services", click the box in front of it then expand it, expand "World Wide Web Services", expand "Application Development Features" and check the box beside CGI.
</p>
<p>
<img src="https://i.imgur.com/CdSXWYO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<h2>PHP Manager and URL Rewrite Module</h2>

<p>
Search Google for PHP Manager and URL Rewrite Module, download and install them.
<p>
<img src="https://i.imgur.com/B0YdFah.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/gtFFk0t.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
Create a folder in C: drive named "PHP", google and download PHP 8.2, open the zip file and extract everything into the folder you created.
</p>
<p>
<img src="https://i.imgur.com/XkmKYWl.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<h2>VC redist and MySQL</h2>

<p>
Google VC 2015-2022 redistributable (x86) and MySQL, download and install them. Navigate through the MySQL, and create a password for "root".
</p>
<p>
<img src="https://i.imgur.com/sNQINYw.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/o5hCsuz.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<h2>PHP 8.2</h2>

<p>
Open IIS as administrator, click "PHP Manager", click "Register new PHP version", click the 3 little dots and look for php-cgi.exe in the PHP folder you created.
</p>
<p>
<img src="https://i.imgur.com/RdXiHek.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
Click "Enable or disable an extension", look for these 3 extensions and enable them, they will be needed to recieve mail and improve performance for osTicket.
</p>
<p>
<img src="https://i.imgur.com/5xDwLvn.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<h2>Downloading and configuring osTicket</h2>

<p>
Search Google for osTicket, download and open the zip file. Extract the upload folder into c:/inetpub/wwwroot and rename it to osTicket.
</p>
<p>
<img src="https://i.imgur.com/kZz29fU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
Go back to IIS, expand "sites", expand "default web site", click "osTicket", then click "Browse *:80 (http)" to see if it opens.
</p>
<p>
<img src="https://i.imgur.com/PbfSpGB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
Go back to your osTicket folder, open "Include", scroll and find "ost-conig.php" and right click it, click "Properties", click "security", click "advanced", click "Disable Inheritance", then click "Remove all Inherited permission from this object."
</p>
<p>
<img src="https://i.imgur.com/PBgmwUy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
Create a new permission for "Everyone" with full control.
</p>
<p>
<img src="https://i.imgur.com/ssBElhS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<h2>HeidiSQL</h2>

<p>
Search Google for HeidiSQL, download, install, and launch it.
</p>
<p>
<img src="https://i.imgur.com/U338fq4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
Open HeidiSQL, enter the password under "root" you created when you installed MySQL, then click "Open".
</p>
<p>
<img src="https://i.imgur.com/8xy0nec.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
Right-click "Unnamed" or what you named it, go down to "Create new", and click "Database". Name it "osTicket" and click "OK".
</p>
<p>
<img src="https://i.imgur.com/PRyPn3i.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<h2>Finishing up osTicket</h2>

<p>
Go back to osTicket, fill out everything and once you get to the last 3, enter the database information you created in HeidiSQL, and click "Install Now".
</p>
<p>
<img src="https://i.imgur.com/a38UUKD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
If everything was followed correctly, osTicket will be successfully installed.
</p>
<p>
<img src="https://i.imgur.com/yExtBTN.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
