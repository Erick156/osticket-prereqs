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

- Windows 10</b> (22H2)

<h2>List of Prerequisites</h2>

- Virtual Machine
- Internet Information Services
- PHP Manager
- VC redist
- MySQL
- Heidi SQL

<h2>Installation Steps</h2>

![image](https://github.com/user-attachments/assets/7f5ba5ab-eb90-4a8f-aa3c-cc9c02859058)


</p>
<p>

1.Log into your Azure account.
2.Create a Resource Group.
3.Within the Resource Group, create a Windows 10 Virtual Machine with 4 virtual CPUs.
4.Once the virtual machine is created, use Remote Desktop to connect to it.
</p>
<br />

![image](https://github.com/user-attachments/assets/59d5ae80-defb-4e25-924f-afe296dc291a)

</p>
<p>

1.Connect to the virtual machine.
2.Access the Control Panel.
3.Click on the Programs tab.
4.Click on the "Turn Windows features on or off" option.
5.Check the boxes as shown in the reference image on the right side.
6.Confirm that IIS is activated by typing 127.0.0.1 in the web browser, as shown in the reference image on the left side.
</p>
<br />

![Installation Files](https://github.com/BenW618/osticket-prereqs/assets/140227052/aba984c9-74b8-47f9-b717-4a01cfc936ac)

</p>
<p>

1.Begin the next step, which involves installing several files. The list of files to download is provided below:

PHPManagerForIIS_V1.5.0.msi
rewrite_amd64_en-US.msi
2.Before proceeding with the rest of the installations, create the directory C:\PHP.

3.Continue downloading and installing the following files:

php-7.3.8-nts-Win32-VC15-x86.zip
VC_redist.x86.exe
mysql-5.5.62-win32.msi

  
</p>
<br />


![Register PHP](https://github.com/BenW618/osticket-prereqs/assets/140227052/c6b0055b-d677-4ea4-81b8-79f15a2a8256)

</p>
<p>
1.After installing the files, open the IIS Manager as an administrator.
2.Click on the PHP Manager tab.
3.Select "Register new PHP version."
4.Enter C:\PHP\php-cgi.exe as the path.
</p>
<br />


![Install osTicket](https://github.com/BenW618/osticket-prereqs/assets/140227052/b4c36fb3-f67a-4390-864e-fc0e478915e1)

</p>
<p>

1.After registering PHP, install the osTicket file.
2.Once the file is installed, extract it.
3.Copy the "upload" folder to C:\inetpub\wwwroot.
4.Within C:\inetpub\wwwroot, rename the "upload" folder to "osTicket".
5.Restart IIS Manager.
6.Click on "Sites" in the IIS Manager.
</p>
<br />


![Screenshot (7)](https://github.com/BenW618/osticket-prereqs/assets/140227052/5e5dcc25-8dfb-4286-9314-f658c1ab4b54)

</p>
<p>
1.Before continuing, fix some of the PHP extensions:
2.Open IIS Manager and click on the "PHP Manager" tab under "osTicket."
3.Enable the following extensions:
4.php_imap.dll
5.php_intl.dll
6.php_opcache.dll
7.Refresh the osTicket page to ensure that some of the errors have disappeared.
</p>
<br />


![Screenshot (9)](https://github.com/BenW618/osticket-prereqs/assets/140227052/bdf586d0-dc26-4cd2-aefa-e3e6c9a0e349)

</p>
<p>
1.Press "Continue" on the osTicket page.
2.Fill out the required information until you reach the "Database Setting" section.
3.Download and install HeidiSQL to create a new session.
4.Enter the session information into the "Database Setting" section.
5.Click on the "Install Now" tab to proceed.
</p>
<br />


![Screenshot (10)](https://github.com/BenW618/osticket-prereqs/assets/140227052/6096f8ec-9d04-4a52-88d2-61993341c00c)

</p>
<p>
Browse to the help desk login page: http://localhost/osTicket/scp/login.php.
</p>
<br />


![Screenshot (11)](https://github.com/BenW618/osticket-prereqs/assets/140227052/05af93eb-f4a1-4da1-acf2-b921cbfddf16)

</p>
<p>
</p>
<br />
