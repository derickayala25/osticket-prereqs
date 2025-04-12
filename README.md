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

- <b>osTicket Core, v1.18.2</b>   osTicket v1.15.8
- <b>HeidiSQL 12.10.0.7000 64bit build</b>   HeidiSQL_12.10.0.7000_Setup   Heidi SQL build 12.3.0.6589
- <b>MySQL v9.2.0 (win64)</b>   mysql-9.2.0-winx64   (MySQL v5.5.62 (win32))
- <b>php-8.3.20-nts-Win32-vs16-x64</b>   php-7.3.8-nts-Win32-VC15-x86
- <b>PHP Manager for IIS v1.5.0</b>   PHPManagerForIIS_x64.msi   PHP Manager for IIS v1.5.0
- <b>IIS URL Rewrite Module 2.1</b>   rewrite_amd64_en-US   IIS URL Rewrite Module 2   
- <b>Microsoft Visual C++ Redistributable for Visual Studio 2015</b>   vc_redist.x64   Microsoft Visual C++ 2015-2022 Redistributable (x86) - 14.34.31931
- <b>Visual Studio 2022 v17.13 (Community)</b>   VisualStudioSetup (2022 Community)

![image](https://github.com/user-attachments/assets/b316e094-837e-41b4-a7f9-f1bf8e62acab)<br/>

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
<b>Enable IIS (Internet Information Services) in Windows WITH CGI (Common Gateway Interface)</b><br />
:white_check_mark: &#x2611; &#9745; :black_square_button: :white_square_button: &#x1F5F9; ☑ "\uD83D\uDDF9" &#128505; [x] U+2611</br>
Open a browser tab and type 127.0.0.1 in the address bar.  You should get a message similar to "This site can't be reached."<br/></b>

1. Type <b>Control Panel</b> in the search bar and open it. Select `Programs` > `Turn Windows features on or off`
2. Tick :white_square_button: the <b>Internet Information Services</b> box and expand
3. Expand <b>Worldwide Web Services</b> and then <b>Application Development Features</b>
4. Check &#x1F5F9; the `CGI` box and click `OK`. Once the operation is done, click `Close` and close the <b>Programs</b> window.<br/>
5. Refresh the browser tab and it should open to a tab similar to the image above.
</p>
### 🌐 Enable Internet Information Services (IIS)

1. Navigate to **Control Panel** > `Uninstall a program` > `Turn Windows features on or off`
2. Tick &#9989;`Internet Information Services`
3. Expand **Internet Information Services** > **World Wide Web Services** > **Application Development Features**
4. Tick &#9989;`CGI` > `OK` > After it finishes, click `Close`
<br/>


<p>
<img src="https://github.com/user-attachments/assets/f2d1695b-ef7b-426f-9957-16d5a7fa52fc" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<b>Install PHP Manager for IIS</b></br>
Navigate to https://github.com/phpmanager/phpmanager/releases on your browser. Click on the file named <b>PHPManagerForIIS_x64.msi</b>. The file will be downloaded automatically.
Double-click the file, click `Next` > accept the terms > `Next` > `Next` > `Install` > `Finish`.<br/><br/>

<p>
<img src="https://github.com/user-attachments/assets/56b5e9aa-532b-4f0e-92f5-a759bb9622ad" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<b>Install the IIS URL Rewrite Module</b></br>
Navigate to https://www.iis.net/downloads/microsoft/url-rewrite. Click on the <b>English: x64 installer</b> file. The file will be downloaded automatically. Double-click the file
and accept the terms. Click `Install` and then `Finish`.<br/><br/>

<p>
<img src="https://github.com/user-attachments/assets/7d5ace4d-bb33-4014-bc6f-7c5bb2687cf4" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<b>Create a folder on the `(C:)` drive called PHP</b></br>
Type <b>File Explorer</b> in the Search bar. Click on the `This PC` icon > Double-click the Windows `(C:)` drive icon > Right-click inside the window and select `New` > `Folder`. Name the folder <b>PHP</b> and leave the window open.<br/><br/>

<p>
<img src="https://github.com/user-attachments/assets/873bdcb8-9c1e-4321-b785-954b1741076e" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<b>Download the PHP files by going to https://windows.php.net/download#php-8.4 and selecting the VS16 x64 Non Thread Safe (2025-Apr-08 22:21:54) Zip [30.7MB] file.</b></br><br/>

<p>
<img src="https://github.com/user-attachments/assets/559b0df8-a4b6-460a-85a2-71a76e14beb1" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<b>Copy the files from the `php-8.3.20-nts-Win32-vs16-x64` zipped folder into the <b>PHP</b> folder.</b></br>
Once downloaded, double-click on the `php-8.3.20-nts-Win32-vs16-x64` zipped folder, select all the files and copy them (by right-clicking inside the window, clicking `OK` on the <b>Windows Security</b> window pop-up, and clicking on <b>Copy</b>). Open the <b>PHP</b> folder on the `(C:)` drive and paste the contents of the `php-8.3.20-nts-Win32-vs16-x64` folder inside it. You can close the `php-8.3.20-nts-Win32-vs16-x64` folder.</b></br><br/>

<p>
<img src="https://github.com/user-attachments/assets/7ceb23d1-ce5e-4927-bcba-0dc90c17c478" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<b>Install Visual C++ Redistributable</b></br>
Go to https://www.microsoft.com/en-us/download/details.aspx?id=48145, click on <b>Download</b>, select `vc_redist.x64.exe`, and click on <b>Download.</b> Double-click the file, accept the terms and click `Install`. Click `Close`.</br><br/>

<p>
<img src="https://github.com/user-attachments/assets/680b6d8d-ec61-4ab0-a07f-5f47ad453f80" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<b>Install Visual Studio</b></br>
Go to https://visualstudio.microsoft.com/ and click on <b>Download Visual Studio</b>. Once downloaded, double-click the `VisualStudioSetup` file and click `Continue`. In the `Workloads` section, under `Other toolsets`, select <b>Data storage and processing</b>. Click `Install`. Once it finishes installing, close the <b>Visual Studio 2022</b> windows.</b></br><br/>

<p>
<img src="https://github.com/user-attachments/assets/68064547-7419-4d8a-9f9b-f50702062368" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<b>Install MySQL 9.2.0</b></br>
Go to https://dev.mysql.com/downloads/mysql/. `Download` the <b>Windows (x86, 64-bit), MSI Installer</b> file. Click on <b>No thanks, just start my download.</b> Double-click the `mysql-9.2.0-winx64` file in your `Downloads` folder. Click `Next`, accept the terms and click `Next`. Select `Typical` on the <b>Choose Setup Type</b> section and click `Install`. Click `Finish`.</br>
In the <b>MySQL Configurator</b> window, click `Next` until you get to the <b>Accounts and Roles</b> section. Type the word <b>root</b> as your password. Click `Next` until you get to the <b>Apply Configuration</b> section. Once there, click `Execute`. Once that's done, click `Next` and then `Finish`.</br><br/>

<b>Open IIS as an Admin (Type “iis” in the Start Menu and select “Run as administrator”)</b></br><br/>

<b>Register PHP from within IIS (PHP Manager -> C:\PHP\php-cgi.exe) -> Double-click on the “PHP Manager” icon inside the “Internet Information Services (IIS) Manager” window -> Click on the “Register new PHP version” link -> A window will open. Click on the three dots (...) -> Double-click on the PHP folder (C drive, PHP) -> Double-click the “php-cgi” file and click OK</b></br><br/>

<b>Reload IIS (Open IIS, Stop and Start the server) -> In the “Internet Information Services (IIS) Manager” window, click on the 	“osTicket-vm...” name on the left side under “Connections” and you'll see a right side panel open that says “Manage Server” -> There you will have the option to “Restart”, “Start” or “Stop” the server -> You can also right-click on the “osTicket-vm...” name and start or stop there.</b>.</br><br/>

<b>Download osTicket by going to https://osticket.com/ -> Get Started -> Download the Open Source file -> select an osTicket Core version, click Next Step -> select your desired language, click Next Step -> you can skip the plug ins -> No Thanks. -> Unzip “osTicket-v1.18.2.zip” and copy the “upload” folder into “c:\inetpub\wwwroot” -> Within “c:\inetpub\wwwroot”, rename “upload” to “osTicket”</b></br><br/>

<b>Reload IIS (Open IIS, Stop and Start the server) -> Make sure you open IIS as Administrator</b></br><br/>

<b>In the “Internet Information Services (IIS) Manager” window, click on the drop-down arrow by the “osTicket-vm...” name. -> Expand the “Sites” folder -> Expand “Default Web Site” -> Click ONCE on “osTicket” -> On the right-side panel, click “Browse *:80 (http)”. It should open a new tab loading the osTicket site (http://localhost/osTicket/setup/)</b></br><br/>

<b>Note that some extensions are not enabled. Go back to IIS -> sites -> Default Web Site -> osTicket -> Double-click PHP Manager -> Click “Enable or disable an extension” -> Enable php_imap.dll -> Enable php_intl.dll -> Enable php_opcache.dll -> Refresh the osTicket site in your browser, observe the changes</b></br><br/>

<b>Using this path, C:\inetpub\wwwroot\osTicket\include, rename ost-sampleconfig.php to ost-config.php</b></br><br/>

<b>Assign Permissions to ost-config.php -> Right-click on “ost-config.php” -> Properties -> Security -> Advanced -> Disable inheritance -> Remove all inherited permissions from this object -> Click “Add” -> “Select a principal” -> type “Everyone” -> click “Check Names” -> click “OK” -> check the “Full control” box -> click “OK”. In the “Advanced Security Settings for ost-config.php” window, were it says “Name” it should say C:\inetpub\wwwroot\osTicket\include\ost-config.php. Click “Apply” and “OK”. On the “ost-config.php Properties” window, click “OK”</b></br><br/>

<b>Continue Setting up osTicket in the browser (click Continue) -> Name Helpdesk -> Default email (receives email from customers) -> In the Admin User section, put in your name -> The email address in this section has to be different from the “System 	Settings” section -> Choose a username and password. DO NOT CLICK ON “Install Now” YET.</b></br><br/>

<b>Install HeidiSQL by going to https://www.heidisql.com/ -> Downloads -> Installer, 64 bit. Go to the Downloads folder and double-click on HeidiSQL_12.10.0.7000_Setup. Select Install for all users (recommended) -> In the "HeidiSQL 12.10.0.7000 - Session manager" window, click New on the bottom left side -> use the word "root" as a password ->  click Open -> Right-click on “Unnamed”, “Create new”, “Database” -> Type “osTicket”, click “OK” -> You will see the new database (osTicket) under the “Unnamed” panel, but if you click it you won't see anything inside of it.</b></br><br/>

<b>Continue Setting up osTicket in the browser -> MySQL Database: osTicket -> MySQL Username: root -> MySQL Password: root -> Click “Install Now!”</b></br><br/>

<b>Once the Congratulations message appears on the osTicket tab on the browser, right-click on the osTicket folder in the HeidiSQL window, select “Refresh” and you should see all the osTicket files in there. -> You can close the HeidiSQL window now</b></br><br/>

<b>Clean up -> Go to C:\inetpub\wwwroot\osTicket\include. Right-click on ost-config.php and select Properties. In the General tab, go to the Attributes section and click on the "Read-Only" box. Click Apply and then OK. You can now close any open file windows.</b></br><br/>

<b>End users URL is http://localhost/osTicket/ while the Staff URL is http://localhost/osTicket/scp/login.php

</p>
<br />
