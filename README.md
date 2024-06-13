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


<h2>Installation Steps</h2>

<h2>Step 1: Install Internet Information Services (IIS) with CGI</h2>
<p>
IIS is a web server that allows the computer you are using to serve websites. osTicket runs on a website, so we need to set up and configure IIS in order to run osTicket. CGI allows us to install PHP Manager. PHP is a back-end web programming language that osTicket uses to run. 
</p>
<p>
  
1. Right click on the Start Menu, then click run
2. Type 'control panel', press enter
3. Click 'Programs', and then 'Turn Windows Features on or off' 
4. Find Internet Information Services, click on the box and then expand
5. Find World Wide Web Services; expand Application Developer 
6. Check CGI 
7. To test that the web server is working, open a browser and navigate to 127.0.0.1 
8. If the default Internet Information Services web pager loads, you have successfully installed IIS with CGI. 
</p>

<p>
<img src="https://i.imgur.com/mnWYcY0.png" width="25%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h2>Step 2: Download and install PHP Manager for IIS</h2>
<p>
  
1. Open a browser, and search the following: PHP Manger 1.5.0 for IIS 10 
2. Download and install
</p>


<p>
<img src="https://i.imgur.com/mnWYcY0.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h2>Step 3: Download and install Rewrite Module</h2>
<p>
Rewrite Module is a download requirement for osTicket that configures URLs. 

1. On your browser, search the following: rewrite_amd64_en-US.msi 
2. Download and install 
</p>

<p>
<img src="https://i.imgur.com/mnWYcY0.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h2>Step 4: Create a PHP folder on your C: drive</h2>


<p>
<img src="https://i.imgur.com/mnWYcY0.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h2>Step 5: Download PHP 7.3.8 </h2>
<p>
  
1. Download php-7.3.8-nts-Win32-VC15-x86.zip 
2. Right click the zip folder in Downloads and 'Extract All' the contents into C:\PHP folder that we just created
</p>


<p>
<img src="https://i.imgur.com/mnWYcY0.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h2>Step 6:  Download and install Microsoft Visual C++ Redistributable</h2> 
<p>
  
1. In a browser, search for VC_redist.x86.exe and download from the Microsoft site 
2. Install 
</p>


<p>
<img src="https://i.imgur.com/mnWYcY0.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h2>Step 7:  Download and install MySQL 5.5.62</h2>
<p>
MySQL installs a database on your computer that osTicket uses to store all of the application data

1. Navigate to the MySQL website and download mysql-5.5.62-win32.msi
2. During installation, choose a 'Typical Setup'
3. Launch Configuration Wizard after install
4. Choose a 'Standard Configuration'
5. Enter a root password; your User Name will be 'root'
</p>


<p>
<img src="https://i.imgur.com/mnWYcY0.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>


<h2>Step 8: Open IIS and Register PHP</h2>
<p>
  
1. Click on Start; type IIS
2. Right click and 'Run as administrator' 
3. Double click PHP Manager
4. Click register new PHP version
5. Browse to our PHP folder on the C: 
6. Choose php-cgi.exe 
7. Refresh the server 
</p>

<p>
<img src="https://i.imgur.com/mnWYcY0.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>


<h2>Step 9: Install osTicket v1.15.8</h2>
<p>
  
1. Download osTicket osTicket v1.15.8 download
2. Extract and copy the 'upload' folder into c:\inetpub\wwwroot
3. Within c:\inetpub\wwwroot, Rename the 'upload' to 'osTicket'
4. Go back to IIS and refresh the server again
5. Inside IIS, go to 'sites', then 'default', then 'osTicket' 
6. On the right-hand side, click 'Browse *80' 
7. If you see the 'Thanks for choosing osTicket' page, the install was successful 
</p>


<p>
<img src="https://i.imgur.com/mnWYcY0.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>


<h2>Step 10: Enable extensions</h2>
<p>
  
1. Go back to IIS and navigate to PHP Manager 
2. Click on 'Enable or disable an extension' towards the bottom of the page 
3. Enable: php_imap.dll, php_intl.dll, and  php_opcache.dll
4. Refresh the osTicket site in your browser, observe the changes
</p>


<p>
<img src="https://i.imgur.com/mnWYcY0.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h2>Step 11: Rename: ost-sampleconfig.php</h2>
<p>
  
1. In File Explorer, navigate to C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
2. Change ost-sampleconfig.php to ost-config.php 
3. Right click ost-config.php -> click the Security tab -> advanced -> Advanced -> Disable inheritance -> Remove All
4. Add -> Select a principal -> Everyone -> Full control 
</p>


<p>
<img src="https://i.imgur.com/mnWYcY0.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>


<h2>Step 12: Continue Setting up osTicket in the browser</h2>
<p>
  
1. Return to browser -> click Continue
2. Name your Helpdesk
3. Add a Default email that will receive email from customers
4. Add Admin user details 
</p>


<p>
<img src="https://i.imgur.com/mnWYcY0.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>


<h2>Step 13: download and install HeidiSQL</h2>
<p>
HeidiSQL is a database client that allows us to connect to the server and setup a database that osTicket will use

1. Download HeidiSQL (HeidiSQL_12.3.0.6589_Setup.exe)
2. Open Heidi SQL
3. Create a new session clicking 'New' button, use the User Name: root and your SQL password
4. Connect to the session
5. Right click 'unnamed' -> create new -> database -> call it 'osTicket' 
</p>


<p>
<img src="https://i.imgur.com/mnWYcY0.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h2>Step 14: Return to browser to continue setting up osTicket</h2>
<p>
  
1. MySQL Database: osTicket
2. MySQL Username: root
3. MySQL Password: (your password)
4. Click 'Install Now!'
</p>
Congratulations! You have successfully installed osTicket. 


<p>
<img src="https://i.imgur.com/mnWYcY0.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h2>Step 15: Browse to your help desk login page and End User page:</h2> 
<p>
  
1. http://localhost/osTicket/scp/login.php
2. http://localhost/osTicket/
</p>


<p>
<img src="https://i.imgur.com/mnWYcY0.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

<br/>
