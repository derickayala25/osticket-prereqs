<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

### 📍 Part 1: Prerequisites & osTicket Installation
### 👉 [Part 2: Post-Installation Configuration](https://github.com/derickayala25/post-install-config)
### 👉 [Part 3: Ticket Lifecycle Demo](https://github.com/derickayala25/ticket-lifecycle)

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com/watch?v=o-YBDTqX_ZU)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10 (22H2)

<h2>List of Prerequisites</h2>

- osTicket Core, v1.18.2
- HeidiSQL 12.10.0.7000 64bit build
- MySQL v9.2.0 (win64)
- php-8.3.20-nts-Win32-vs16-x64
- PHP Manager for IIS v1.5.0
- IIS URL Rewrite Module 2.1 
- Microsoft Visual C++ Redistributable for Visual Studio 2015
- Visual Studio 2022 v17.13 (Community)

<h2>Installation Steps</h2>

<br/>
How They Work Together (Simple Example):</br>
A user opens a ticket online.</br></br>

IIS sees the request and hands it to PHP.

PHP says, “Let’s write this ticket down,” and asks MySQL to save it.

MySQL saves the info.

PHP builds a "thank you" message.

IIS sends it back to the user to see in their browser.



<b>Enable IIS (Internet Information Services) in Windows WITH CGI (Common Gateway Interface)</b><br/>
IIS is Microsoft’s web server software. Enabling it basically turns your Windows machine into a web server. When you also enable CGI, this allows IIS to run external scripts or programs, usually for generating dynamic content.

1. Open a browser tab and type <b>127.0.0.1</b> in the address bar. You should get a message similar to <b>This site can't be reached.</b>
2. Type <b>Control Panel</b> in the Windows search box and open it. Select `Programs` > `Turn Windows features on or off`
3. Tick :white_square_button: the <b>Internet Information Services</b> box and then click on the plus sign <b>+</b> ![plus](https://github.com/user-attachments/assets/ac6453e2-b164-4ae3-ae33-a6059922e112)	&#8862; next to it to expand
4. Expand <b>World Wide Web Services</b> and then <b>Application Development Features</b>
5. Check &#x1F5F9; the <b>CGI</b> box and click `OK`. Once the operation is done, click `Close` and close the <b>Programs</b> window.
6. Refresh the browser tab and it should open to a tab similar to the image below.

:plus-square: :squar![laptop](https://github.com/user-attachments/assets/c0fa64e4-e262-4925-a2a9-62d3e414b317)
<i class="fa-solid fa-bars"></i>
&#8862;
&#x229E; U+F075  &#xF075; ![plus](https://github.com/user-attachments/assets/ac6453e2-b164-4ae3-ae33-a6059922e112)

<section class="default-example" id="default-example">
  <p>
    Align the star:
    <img id="example-element" src="https://github.com/user-attachments/assets/ac6453e2-b164-4ae3-ae33-a6059922e112" />
  </p>
</section>

<p>
<img src="https://github.com/user-attachments/assets/8ca00ad8-2185-4006-8140-cee0ba2f2df6" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p><br/>


<b>Install PHP Manager for IIS</b></br>
PHP used to stand for Personal Home Page. However, now it means PHP: Hypertext Processor. It's a server-side scripting language used mainly for web development. PHP Manager for IIS is a tool/plugin that helps you manage PHP installations on your IIS web server, making working with PHP easier and less manual.
1. Navigate to https://github.com/phpmanager/phpmanager/releases on your browser.
2. Click on the file named <b>PHPManagerForIIS_x64.msi</b>. The file will be downloaded automatically.
3. Type <b>File Explorer</b> in the search box and open it.
4. Open the <b>Downloads</b> folder.
5. Double-click the file `PHPManagerForIIS_x64` > click `Next` > accept the terms > `Next` > `Next` > `Install` > `Finish`.

<p>
<img src="https://github.com/user-attachments/assets/f2d1695b-ef7b-426f-9957-16d5a7fa52fc" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p><br/>


<b>Install the IIS URL Rewrite Module</b></br>
This is a feature for the IIS web server that lets you modify request URLs using rules. It acts like a URL filter/transformer, helping you manage how incoming URLs are handled.
1. Navigate to https://www.iis.net/downloads/microsoft/url-rewrite.
2. Click on the <b>English: x64 installer</b> file. The file will be downloaded automatically.
3. Double-click the file `rewrite_amd64_en-US` and accept the terms. Click `Install` and then `Finish`.

<p>
<img src="https://github.com/user-attachments/assets/56b5e9aa-532b-4f0e-92f5-a759bb9622ad" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p><br/>

<b>Create a folder on the (C:) drive called PHP</b></br>
1. Type <b>File Explorer</b> in the Search box and open it.
2. Click on the ![laptop](https://github.com/user-attachments/assets/c5c0284b-de55-4fa3-8068-503056ac8200) icon > Double-click the <b>Windows (C:)</b> drive icon
3. Right-click inside the window and select <b>New</b> > <b>Folder</b>. Name the folder <b>PHP</b>, press <b>Enter</b> and leave the window open.

<p>
<img src="https://github.com/user-attachments/assets/7d5ace4d-bb33-4014-bc6f-7c5bb2687cf4" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p><br/>

<b>Download the PHP files</b></br>
1. Go to https://windows.php.net/download#php-8.4.
2. Select the <b>VS16 x64 Non Thread Safe (2025-Apr-08 22:21:54) Zip [30.7MB]</b> file. The file will be downloaded automatically.

<p>
<img src="https://github.com/user-attachments/assets/873bdcb8-9c1e-4321-b785-954b1741076e" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p><br/>

<b>Copy the files from the `php-8.3.20-nts-Win32-vs16-x64` zipped folder into the PHP folder.</b></br>
1. Once downloaded, navigate to the <b>Downloads</b> folder and double-click on the `php-8.3.20-nts-Win32-vs16-x64` zipped folder.
2. Select all the files and copy them (by right-clicking inside the window, clicking `OK` on the <b>Windows Security</b> window pop-up, and clicking on <b>Copy</b>).
3. Open the <b>PHP</b> folder on the <b>(C:)</b> drive and paste the contents of the `php-8.3.20-nts-Win32-vs16-x64` folder inside it.
4. You can close the `php-8.3.20-nts-Win32-vs16-x64` folder.

<p>
<img src="https://github.com/user-attachments/assets/559b0df8-a4b6-460a-85a2-71a76e14beb1" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p><br/>

<b>Install Visual C++ Redistributable</b></br>
This installs runtime libraries (collections of code that programs use while they’re running) needed to run applications built with Visual C++ . In this case, MySQL (which we'll install shortly), is primarily built with C and C++.
1. Go to https://www.microsoft.com/en-us/download/details.aspx?id=48145.
2. Click on <b>Download</b>, select <b>vc_redist.x64.exe</b>, and click on <b>Download</b>.
3. Open the <b>Downloads</b> folder, double-click on the `vc_redist.x64` file, agree to the terms and click `Install`. Click `Close`.

<p>
<img src="https://github.com/user-attachments/assets/7ceb23d1-ce5e-4927-bcba-0dc90c17c478" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p><br/>

<b>Install Visual Studio</b></br>
Visual Studio is an Integrated Development Environment (IDE) from Microsoft used for writing, testing, and debugging software. Amongst many things, it's used for building applications.
1. Go to https://visualstudio.microsoft.com/ and click on <b>Download Visual Studio</b>.
2. Once downloaded, go back to the <b>Downloads</b> folder, double-click the `VisualStudioSetup` file and click `Continue`.
3. In the <b>Workloads</b> tab, scroll down to <b>Other toolsets</b>, select <b>Data storage and processing</b>.
4. Click `Install`. This might take a few minutes.
5. Once it finishes installing, close the <b>Visual Studio 2022</b> windows.

<p>
<img src="https://github.com/user-attachments/assets/680b6d8d-ec61-4ab0-a07f-5f47ad453f80" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p><br/>

<b>Install MySQL 9.3.0</b></br>
MySQL is  software that helps you store, organize, and retrieve data efficiently using SQL (Structured Query Language). It's like a digital notebook that helps apps remember and organize lots of information so they can find it later.
1. Go to https://dev.mysql.com/downloads/mysql/.
2. Download the <b>Windows (x86, 64-bit), MSI Installer</b> file. Click on <b>No thanks, just start my download.</b>
3. Go back to the <b>Downloads</b> folder and double-click the `mysql-9.3.0-winx64` file. <b>Please note that it might be a newer version</b>. Click `Next`, accept the terms and click `Next`.
4. Select `Typical` on the <b>Choose Setup Type</b> section and click `Install`. Click `Finish`.

<p>
<img src="https://github.com/user-attachments/assets/5a656e7b-5da4-45bf-984f-82d64e8b07ff" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p><br/>

5. In the <b>MySQL Configurator</b> window, click `Next` until you get to the <b>Accounts and Roles</b> section.
6. For <b>Username</b> type <em>Adminuser</em>, for <b>Host</b> make sure <em><All Hosts (%)></em> is selected. For <b>Role</b> select <em>DBAdmin</em>. Type your password and click `OK`.

<p>
<img src="https://github.com/user-attachments/assets/31b44a78-0f62-46b5-a041-24240992c022" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p><br/>

7. In the <b>Server File Permissions</b> section make sure to select the first option.

<p>
<img src="https://github.com/user-attachments/assets/d3c99319-4019-4720-adad-15a0aff676c5" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p><br/>

8. Click `Next` until you get to the <b>Apply Configuration</b> section.
9. Once there, click `Execute`. Once that's done, click `Next` and then `Finish`.</br></br>

<b>Open IIS as an Administrator</b></br>
1. Type <b>IIS</b> in the search box and select <b>Run as administrator</b>.

<p>
<img src="https://github.com/user-attachments/assets/15dba9f4-8bce-4001-ab48-4b8668dbe845" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p><br/>

<b>Register PHP from within IIS</b></br>
You have to register PHP within IIS so that IIS knows how to handle `.php files` when someone requests them through the web browser.
1. Double-click the <b>PHP Manager</b> icon inside the <b>Internet Information Services (IIS) Manager</b> window.
2. Click on the <b>Register new PHP version</b> link. A window will open.
3. Click on the ellipsis `...`. Double-click on the <b>PHP</b> folder.
4. Double-click the `php-cgi` file and click `OK`.

<p>
<img src="https://github.com/user-attachments/assets/018b3d25-1a4c-4628-87d4-6d139a44f321" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p><br/>

<b>Reload IIS</b></br>
1. In the <b>Internet Information Services (IIS) Manager</b> window, click once on the <b>osTicket-vm...</b> name on the left side under <b>Connections</b>.
2. You'll see a right side-panel open that says <b>Manage Server</b>. There you will have the option to `Restart`, `Start` or `Stop` the server.
3. You can also right-click on the <b>osTicket-vm...</b> name and start or stop there. Stop and start the server once.

<p>
<img src="https://github.com/user-attachments/assets/caef7993-ddda-4773-98d2-d4675b16dd76" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p><br/>

<b>Download osTicket</b></br>
1. Go to https://osticket.com/.
2. Click on <b>Get Started</b>. Navigate to the <b>Open Source</b> column and click on <b>Download</b>.
3. Select the latest osTicket Core version and click on <b>Next Step</b>. Select your desired language, click on the `>` arrow and click on <b>Next Step</b>.
4. Do not select any plugins and click on <b>Next Step</b>. Click on <b>No Thanks</b>.
5. Go back to the <b>Downloads</b> folder, double click the `osTicket-v1.18.2.zip` file (or whichever file is the latest) and copy the <b>upload</b> folder.
6. Go to the <b>Windows (C:)</b> drive folder, double-click the <b>inetpub</b> folder and then double-click the <b>wwwroot</b> folder.
7. Once inside the <b>wwwroot</b> folder, paste the <b>upload</b> folder.
8. Rename the <b>upload</b> folder to <b>osTicket</b>.

<p>
<img src="https://github.com/user-attachments/assets/63333852-7346-4007-9594-62522515e9b2" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p><br/>

<b>Reload IIS</b></br>
1. Open <b>IIS</b> as an Administrator (if the window isn't open already). Stop and Start the server once.

<p>
<img src="https://github.com/user-attachments/assets/79a4cd47-aca3-4d81-be75-a986aa529c40" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p><br/>

<b>Open the osTicket local site</b></br>
1. In the <b>Internet Information Services (IIS) Manager</b> window, click on the drop-down arrow on the left side of the <b>osTicket-vm...</b> name in order to expand.
2. Expand the <b>Sites</b> folder. Expand <b>Default Web Site</b>. Click ONCE on <b>osTicket</b>.
3. On the right side-panel, click on `Browse *:80 (http)`. It should open a new browser tab loading the osTicket local site (http://localhost/osTicket/setup/).

<p>
<img src="https://github.com/user-attachments/assets/ef617686-9734-4ec5-8c51-7ce4cc098ead" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p><br/>

<b>Enable extensions</b></br>
1. Note that some extensions are not enabled.
2. Go back to <b>IIS</b> > <b>Sites</b> > <b>Default Web Site</b> > <b>osTicket</b>. Double-click <b>PHP Manager</b>.
3. Click `Enable or disable an extension`. Right-click on the greyed out `php_imap.dll` and select `Enable`. Enable `php_intl.dll`. Enable `php_opcache.dll`.
4. Refresh the http://localhost/osTicket/setup/ site in your browser and observe the changes. You should have only one extension disabled.

<p>
<img src="https://github.com/user-attachments/assets/3f7d5414-ded2-4eb5-a384-a3a09219ee9c" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p><br/>

<b>Rename ost-sampleconfig.php</b></br>
1. Go to the <b>Windows search box</b> and paste this path <b>C:\inetpub\wwwroot\osTicket\include</b>.
2. Rename `ost-sampleconfig.php` to `ost-config.php`.

<p>
<img src="https://github.com/user-attachments/assets/e1ecb51f-b505-4ea1-82b6-224b1cd93aa4" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p><br/>

<b>Assign Permissions to `ost-config.php`</b></br>
1. Right-click on `ost-config.php` and select <b>Properties</b>.
2. Click on the <b>Security</b> tab. Click on `Advanced` > `Disable inheritance`. Click on `Remove all inherited permissions from this object`.
3. Click `Add` > `Select a principal`. Type <b>Everyone</b> in the <b>Enter the object names to select (examples):</b> box.
4. Click `Check Names` > `OK`. Check the <b>Full control</b> box and click `OK`.
5. In the <b>Advanced Security Settings for ost-config.php</b> window, were it says <b>Name:</b> it should say <b>C:\inetpub\wwwroot\osTicket\include\ost-config.php</b>.
6. Click `Apply` and `OK`. On the <b>ost-config.php Properties</b> window, click `OK`.

<p>
<img src="https://github.com/user-attachments/assets/a04ebf05-e382-446c-8cbc-9127cbdec2cd" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p><br/>

<b>Continue Setting up osTicket in the browser</b></br>
1. Back in the osTicket Installer browser tab, Click `Continue`.
2. In the <b>System Settings</b> section, in the <b>Helpdesk Name</b> box, type in whatever name you want to give your Helpdesk.
3. In the <b>Default email</b> (receives email from customers) box, type in a made-up email (for this example).
4. In the <b>Admin User</b> section, put in your made-up name, email address (it has to be different from the one in the <b>System Settings</b> section).
5. Choose a username and password. <b>DO NOT</b> click on `Install Now` yet.

<p>
<img src="https://github.com/user-attachments/assets/7bd07e82-156f-4e51-a504-100d388b0eae" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p><br/>

<b>Install HeidiSQL</b></br>
HeidiSQL allows you to connect to and manage databases.
1. Go to https://www.heidisql.com/.
2. Click on the <b>Downloads</b> tab next to the <b>Home</b> tab. Close out any ad pop-up windows.
3. Click on the <b>Installer, 64 bit</b> link. Go to the <b>Downloads</b> folder and double-click on <b>HeidiSQL_12.10.0.7000_Setup</b>.
4. Select <b>Install for all users (recommended)</b>. Accept the agreement and click <b>Next</b> until you get to the <b>Ready to Install</b> section.
5. Click `Install`. Click `Finish`.
6. In the <b>HeidiSQL 12.10.0.7000 - Session manager</b> window, click <b>New</b> on the bottom left side. Use the word <b>root</b> as a password.
7. Click `Open`. Right-click on <b>Unnamed</b> and select <b>Create new</b> > <b>Database</b>.
8. Type <b>osTicket</b> and click `OK`.
9. You will see the new database, <b>osTicket</b>, under the <b>Unnamed</b> panel. However, if you click it, you won't see anything inside of it in the right-side panel.

<p>
<img src="https://github.com/user-attachments/assets/a732121f-c155-4caf-a75d-e5c8420678a3" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p><br/>

<b>Continue Setting up osTicket in the browser</b></br>
1. Go back to the (http://localhost/osTicket/setup/install.php) browser tab.
2. Under the <b>Database Settings</b> section, under <b>MySQL Database:</b>, type the word <b>osTicket</b>.
3. For <b>MySQL Username:</b> type the word <b>root</b> and for <b>MySQL Password:</b> also type <b>root</b>.
4. Click `Install Now!`

<p>
<img src="https://github.com/user-attachments/assets/73a6418f-11b6-4905-ba7b-daa26a6e9280" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p><br/>

<p>
<img src="https://github.com/user-attachments/assets/9a3a8e2a-aaae-4f2e-b4e2-71c7ff82daa4" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p><br/>

<b>Finalizing the installation</b></br>
1. Once the <b>Congratulations!</b> message appears on the osTicket browser tab, right-click on <b>osTicket</b> in the <b>Unnamed\osTicket\ - HeidiSQL 12.10.0.7000</b> window and select <b>Refresh</b>. You should see all the osTicket files on the right-side panel.
2. You can close the <b>HeidiSQL</b> window now.

<p>
<img src="https://github.com/user-attachments/assets/935ac7db-2e86-46cb-8373-d75678fc966f" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p><br/>

<b>Cleanup</b></br>
1. Go to the <b>Windows search box</b> and paste this path <b>C:\inetpub\wwwroot\osTicket</b> and press <b>Enter</b>.
2. Right-click on the <b>setup</b> folder and select <b>Delete</b>.
3. In that same window, open the <b>include</b> folder.
4. Right-click on `ost-config.php` and select <b>Properties</b>. In the <b>General</b> tab, go to the <b>Attributes</b> section.
5. Click on the <b>Read-Only</b> box. Click `Apply` and then `OK`.
6. You can now close any open file windows.

<p>
<img src="https://github.com/user-attachments/assets/e54b9982-d0f5-4532-98f8-0fec023df326" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p><br/>

<p>
<img src="https://github.com/user-attachments/assets/30a1df91-6309-425a-aaf5-e0e8a5ee6153" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p><br/>

<b>Log in to osTicket as an Administrator</b></br>
1. Open a browser tab and paste this URL, http://localhost/osTicket/scp/login.php.
2. Using the name and password you created (this was done in the <b>Continue Setting up osTicket in the browser</b> step), log in as an administrator. 

<p>
<img src="https://github.com/user-attachments/assets/28d37b92-8265-4df6-8ceb-edcf702a7837" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p><br/>

<p>
<img src="https://github.com/user-attachments/assets/01f877d5-acb7-4856-869e-b94ec5ecfa3e" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p><br/>

<b>Open the End User browser tab</b></br>
1. Open a browser tab and paste this URL, http://localhost/osTicket/.
2. This is where an end user would submit a request.

<p>
<img src="https://github.com/user-attachments/assets/f15b7508-8807-4efc-bcdc-d365ee168ed4" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p><br/>

<b>One last thing...</b></br>
If you have any issues logging in, especially while using Edge or Chrome, clear your browser's cache.


### 📍 Part 1: Prerequisites & osTicket Installation
### 👉 [Part 2: Post-Installation Configuration](https://github.com/derickayala25/post-install-config)
### 👉 [Part 3: Ticket Lifecycle Demo](https://github.com/derickayala25/ticket-lifecycle)

