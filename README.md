<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10 (22H2)

<h2>List of Prerequisites</h2>

- osTicket Installation Files
- Item 2
- Item 3
- Item 4
- Item 5

![image](https://github.com/user-attachments/assets/b316e094-837e-41b4-a7f9-f1bf8e62acab)<br />

<h2>Installation Steps</h2>

<p>
<img src="https://github.com/user-attachments/assets/aa2083e6-4311-4994-82e8-21e6e2c50236" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>

Download the <a href="https://www.drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD">osTicket-Installation-Files</a> and unzip it onto your desktop.

<br />

<p>
<img src="https://github.com/user-attachments/assets/8ca00ad8-2185-4006-8140-cee0ba2f2df6" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<b>Install / Enable IIS (Internet Information Services) in Windows WITH CGI (Common Gateway Interface)</b><br />
Open a browser tab and type 127.0.0.1 in the address bar. You should get a message similar to "This site can't be reached."<br />Follow these steps: Go to Start Menu, Control Panel, Programs, Turn Windows features on or off, check the “Internet Information Services” box and expand, expand “Worldwide Web Services”, expand “Application Development Features”, check the "CGI" box, click OK.<br />Refresh the browser tab and it should open to a tab similar to the image above.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<b>Install PHP Manager for (IIS https://github.com/phpmanager/phpmanager/releases -> PHPManagerForIIS_x64.msi)</b><br />
<b>Install the Rewrite Module (https://www.iis.net/downloads/microsoft/url-rewrite -> English: x86 installer / x64 installer)</b><br />
<b>Create a folder on the C drive called “PHP”</b><br/>
<b>Double-click on the “php-8.4.5-nts-Win32-vs17-x86” folder, select all the files and copy, open the PHP folder on the C drive and paste the contents of the “php-8.4.5-nts-Win32-vs17-x86” folder</b></br>
<b>Install VC_redist.x86.exe</b></br>
<b>Install MySQL 9.2.0 (mysql-9.2.0-winx64.msi). Select “Typical” on the “Choose SetupType” section -> click on the “Launch MySQL Instance Configuration Wizard” box BEFORE clicking “Finish” -> Standard Configuration -> In the “Please set the security options" choose a username and password</b></br>
<b>Open IIS as an Admin (Type “iis” in the Start Menu and select “Run as administrator”)</b></br>
<b>Register PHP from within IIS (PHP Manager -> C:\PHP\php-cgi.exe) -> Double-click on the “PHP Manager” icon inside the “Internet Information Services (IIS) Manager” window -> Click on the “Register new PHP version” link -> A window will open. Click on the three dots (...) -> Navigate to the PHP folder (C drive, PHP) -> Double-click the “php-cgi” file and click OK</b></br>
pen a browser tab and type 127.0.0.1 in the address bar. You should get a message similar to "This site can't be reached."<br />Follow these steps: Go to Start Menu, Control Panel, Programs, Turn Windows features on or off, check the “Internet Information Services” box and expand, expand “Worldwide Web Services”, expand “Application Development Features”, check the "CGI" box, click OK.<br />Refresh the browser tab and it should open to a tab similar to the image above.
</p>
<br />
