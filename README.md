
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
Tutorial for prerequisites and installation of the open-source help desk ticketing system osTicket.<br />
<br />
Part 1: Creating the virtual environment in Azure.<br />
Part 2: Installation of software dependencies and osTicket.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Microsoft Azure Active Subscription (Creation of Reasearch Group, VMs, Virtual Networks, Subnets)
- Enable Internet Information Services(IIS)
- PHP Manager
- Rewrite Manager
- C++ Redistributbal
- MySQL Server
- Install osTicket
- Assigning Permissions






<h2>Installation Steps (Part 1) Steps: 1 - 12</h2>


![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/a00701b7-fa87-49f7-9808-097780c5c0e7)
<p>
Step 1: Navigate to "portal.azure.com/#home" to create a Resource Group. Search for Reasearh Groups. This group will house the Virtual Network and Subnet. 
</p>
<br />


![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/e924987f-8d09-4d24-be57-8eaf95e6456f)
<p>
Step 2: Click "Create" to create the Resource Group
</p>
<br />

![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/88dae17e-6acc-4cda-84f5-26d115ff0d06)
<p>
Step 3: Name the resource group (ex: RGosTicket). Choose a region. Choose a region close to your primary user base to minimize latency. Also ensure that the region complies with local laws regarding data residency and privacy. Click Review + create.
</p>
<br />

![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/cb6d7724-bfed-41d2-910a-d8a0b3b97e29)
![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/01984bf3-2172-491c-9c26-5c1e969504ee)
<p>
Step 4: Search for Virtual Machines. Click Create. Select Azure virtual machine.
</p>
<br />

![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/2d704268-737a-468a-9f02-f2c7dc65e589)
<p>
Step 5: Select the Research Group we created (RGosTicket). Name the Virtual Machine (ex: vmOsTicket). Choose a Region (ex: (US) East US). Choose an image (ex: Windows 10 Pro, version 22H2 - x64 Gen2 (free services eligible)). 
</p>
<br />

![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/8faa301e-1ca1-447f-966f-3d393adaa08c)
<p>
Step 6: Choose a size (ex: Standard_D4s_v3 - 4 vcpus, 16 GiB memory ($140.16/month)) note: limited subscriptions cannot use more than 4 vcpus. Choose a Username and Password (Username ex: jamesuser). Check the Licensing box, and click Next: 
</p>
<br />

![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/c23a438e-7315-43ec-8017-9837fc8277db)
<p>
Step 7: Click Next again to navigate to Networking
</p>
<br />

![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/a992ab4f-0500-42a1-b48d-c51701aa872c)
<p>
Step 8: Azure will create a new Virtual Network and Subnet automatically (ex: (new)vmOsTicket-vnet / ex: (new)default(10.0.0.0/24)). Click Review + Create
</p>
<br />

![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/a3278296-1dc1-4253-8961-62604f8071f8)
<p>
Step 9: Once Validation is passed. Click Create.
</p>
<br />

![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/3155374b-544a-430a-b340-69a5dbb64009)
<p>
Step 10: When deployment is complete. Navigate to Virtual Machines. Click the Virtual Machine name (ex: vmOsTicket) to see VM information.
</p>
<br />

![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/5ba30669-0b74-4065-aadb-5e7231e63408)
<p>
Step 11: Copy the Public IP address(ex: 52.168.84.82). Open Remote Desktop Connection. Paste the Public IP address into bar. Click Connect.
</p>
<br />

![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/daa843e1-4251-4635-8924-ffd54c87b95d)
<p>
Step 12: Enter Username/Password we created in Step 6 (Username ex: jamesuser). Click Ok.
</p>
<br />

![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/c2d8fc54-2f24-44a2-9a91-653abb9bf360)
<p>
Screen should look similar to this.
</p>
<br />
<br />

<h2>Installation Steps (Part 2) Steps:  13 - 47</h2>


![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/2712a469-9053-4107-becd-4a8bf735d894)
![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/2ae77e51-192e-4378-b48b-68c2e413d227)
<p>
Step 13: Right click the start menu and select "Run". Type 'control' and hit enter to open the Control Panel.
</p>
<br />

![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/0f5ff643-63fa-464f-892f-5e0893dac3e3)
<p>
Step 14: Click "Programs"
</p>
<br />

![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/5222a443-46e5-456e-a71a-a4c4319c3543)
<p>
Step 15: Click "Turn Windows features on or off"
</p>
<br />

![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/c62f3b83-c862-45bc-b8df-2d37e9028d3c)
<p>
Step 16: Check the box for "Internet Information Services"
</p>
<br />

![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/faa69f3b-afac-4720-8335-698abce825ef)
<p>
Step 17: Expand "Internet Information Services". Expand "World Wide Web Services". Expand "Application Development Features". Check the box for "CGI"
</p>
<br />

![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/4976952a-085a-4359-ba6e-e844c528317c)
<p>
Step 18: Collapse "Application Development Features". Expand "Common HTTP Features". Select all boxes and hit ok.
</p>
<br />

![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/9c235930-66ba-4025-be8d-aaa63cfede7f)
<p>
Step 19: Ensure IIS enabling was successful by opening a browser. Enter 127.0.0.1 in the bar. Result should look like this. If unsucessful, see step 19.5, else go on to step 20.
</p>
<br />

![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/187bcb23-4d34-4ed6-a94d-5000976107be)
![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/a08be245-8dc8-4e41-9228-96c7eae36ccb)
![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/9292168e-9100-4aac-ad35-83ba39e65b2a)
<p>
Step 19.5: If unsuccessful. Navigate back to "Programs". Click "Uninstall a program". Click "Turn Windows Features on or off". Uncheck Internet Information Services. Click Ok. Restart process from Step 13. 
</p>
<br />

![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/25096401-4cc7-43b0-8fb6-fe173b3951c5)
<p>
Step 20: Download and install PHP manager https://drive.google.com/file/d/1RHsNd4eWIOwaNpj3JW4vzzmzNUH86wY_/view?usp=share_link (PHPManagerForIIS_V1.5.0.msi)
</p>
<br />

![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/d29df45d-f4d1-4bb1-8e82-e52724902fcc)
<p>
Step 21: Download and install the Rewrite Module https://drive.google.com/file/d/1tIK9GZBKj1JyUP87eewxgdNqn9pZmVmY/view?usp=share_link (rewrite_amd64_en-US.msi)
</p>
<br />

![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/2f7ca269-391d-4b75-891b-907a0f78ab39)
<p>
Step 22: Navigate to C: drive from File Explorer. Create a new folder called PHP.
</p>
<br />

![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/9402741a-7d78-46de-ab79-dc995145f121)
<p>
Step 23: Download PHP. https://drive.google.com/file/d/1snNMtLdCOpMtkCyD4mvl9yOOmvVIp9fP/view?usp=share_link (php-7.3.8-nts-Win32-VC15-x86.zip). 
  Unzip the contents into C:\PHP 
</p>
<br />

![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/cf720607-6007-4c61-bc7d-0e5d93a864d3)
<p>
Step 24: Download and install C++ Redistributable https://drive.google.com/file/d/1s1OsGF3-ioO0_9LYizPRiVuIkb3lFJgH/view?usp=share_link
</p>
<br />


![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/fbd07b0e-a590-4fc4-b3da-26132b31266f)
![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/ca8aca01-ad29-47cf-a4ca-f59dd63aa022)
![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/22ab78d7-5691-45cf-a0bb-c0b7124c96b4)
<p>
Step 25: Download and install MySQL Server. https://drive.google.com/file/d/1_OWh9p7VQLcrB0q_V7qT8yHl0xo5gv7z/view?usp=share_link (mysql-5.5.62-win32.msi). Choose Typical Setup. Choose Standard Configuration. Create a Password
</p>
<br />

![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/9cbc8af3-8d32-495c-b8a4-1543805321a7)
<p>
Step 26: Click Start. Type IIS. RIGHT-click Internet Information Services and choose "Run as Administrator"
</p>
<br />

![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/90b3d9f7-b465-480f-8505-2afa5188f190)
<p>
Step 27: Double Click PHP Manager
</p>
<br />

![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/c0844deb-683f-43f4-a215-9339b3ee2572)
<p>
Step 28: Register new PHP version. Provide the path: "php-cgi" inside the PHP folder
</p>
<br />

![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/83a23692-c897-473b-93a3-e834445aca7a)
<p>
Step 29: Click the server (ex: vmOsTicket(vmOsTicket\jamesuser)). Click "Restart" under Manage Server
</p>
<br />

![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/b487ccac-368d-4749-b5e7-07af9357de2c)
<p>
Step 30: Download osTicket. https://drive.google.com/file/d/1cQIErIgsuKE-E-sD_6SO0EBcV9bt4uJh/view?usp=drive_link (v1.15.8). Drag "upload" folder into c:\inetpub\wwwroot 
</p>
<br />

![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/3d06bb9b-3f7a-4569-8d0b-11d16435048e)
<p>
Step 31: Rename "upload" to "osTicket"
</p>
<br />

![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/2b2757e1-e9ed-40e5-a84f-696d2299abf1)
<p>
Step 32: Click "Restart" inside of IIS
</p>
<br />

![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/9f2d13ae-bd71-41e2-81a4-421ab07602af)
<p>
Step 33: Click the server (ex: vmOsTicket/jamesuser). Navigate to Sites -> Default Web Site -> click osTicket
</p>
<br />

![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/c2a50ee8-c0cf-45ad-9267-b00dd51ae444)
<p>
Step 34: Click Browse on the right side of IIS, then this window will open
</p>
<br />

![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/b06f6e78-c3ab-4161-ad60-d131434d4c3e)
<p>
Step 35: Double click PHP Manager. Click Enable or disable an extension
</p>
<br />

![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/53cd630a-bf10-4fb7-a202-dd802472a3df)
<p>
Step 36: Enable the following: php_imap.dll, php_intl.dll, php_opcache.dll - Refreshing browser should look like this. 
</p>
<br />

![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/ff8d7d67-764a-415a-8f7b-c6c5d8ac9f10)
<p>
Step 37: Navigate to ost-sampleconfig.php then rename this file ost-config.php
</p>
<br />

![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/5dbbe8a5-30d1-4377-a81e-6fd6203d7959)
<p>
Step 38: ost-config.php -> Properties -> Security -> Advanced -> Disable inheritance -> Remove all inherited permissions from this object
</p>
<br />

![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/c4063497-974a-437c-a6fc-bb825600a5da)
<p>
Step 39: Add -> Select a principal -> enter "everyone" in box -> Check Names -> click ok
</p>
<br />

![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/10396b9c-0754-4300-9fdb-cde7d0fca47d)
<p>
Step 40: Give everyone full control -> Press Ok -> Apply -> Ok
</p>
<br />

![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/6fa0d083-e82d-43af-807f-5be241a8cbf0)
<p>
Step 41: Click Continue on browser with osTicket open.
</p>
<br />

![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/1841fb65-e844-4a29-b979-601bec42f9a5)
<p>
Step 42: Download and install Heidi SQL. https://www.heidisql.com/installers/HeidiSQL_12.3.0.6589_Setup.exe This will allow us to connect to the SQL server and set up a database that osTicket will use.
</p>
<br />

![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/a153d2fe-7280-4643-8bb2-aa7f786374ba)
<p>
Step 43: Click New. Enter User(ex: root) and password. Click Open. This is the connection to the SQL server.
</p>
<br />

![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/11790663-192a-47d7-b338-1d3dd0559d5a)
<p>
Step 44: Right click "Unnamed" and create a new Database called "osTicket"
</p>
<br />

![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/908b39b4-864a-47c5-9e49-0f6983a4a46c)
![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/b400233d-11cc-44a7-bdad-c39bb45f9577)
![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/2728176d-0877-437b-bd04-72af77fc57e4)

<p>
Step 45: Fill out the osTicket installer form with the data you have chosen and click Install Now.
</p>
<br />

![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/8359838f-cebe-459a-a63f-3d7f86863a7f)
<p>
Step 46: Clean up. Navigate to This PC -> Windows(C:) -> inetpub -> wwwroot -> osTicket and delete the "setup" folder
</p>
<br />

![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/126e98bf-5680-4e7e-b9ea-f37a4ae8b465)
<p>
Step 47: Navigate to This PC -> Windows(C:) -> inetpub -> wwwroot -> osTicket -> include -> ost-config.php -> properties -> Security -> Advanced -> Click Everyone -> Edit -> Remove permissions: Full control, Modify, Write -> Ok -> Apply -> Ok -> Ok
</p>
<br />

![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/f0deba4c-2cd8-441e-9bb9-af265ed93b28)
<p>
Installation of osTicket is now complete!    
</p>
<p>
  URL for ADMIN: http://localhost/osTicket/scp/login.php
</p>
<p>
  URL for end users to create tickets: http://localhost/osTicket/
</p>
<br />

![image](https://github.com/jameswsm/osticket-prereqs/assets/170709350/bd2e65c5-99e1-4c2c-ab7f-d725257cbac9)
<p>
LOGIN as ADMIN will display:
</p>
<br />
