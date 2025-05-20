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

- Azure Virtual Machine
- osTicket Installation Files
- Heidi SQL


<h2>Installation Steps</h2>


![68747470733a2f2f696d6775722e636f6d2f66526c456a4d462e706e67](https://github.com/user-attachments/assets/52e30a45-3b6e-4f7c-9ae2-c5c16106b1b2)


</p>
<p>
Within the VM (osticket-vm), download the osTicket-Installation-Files.zip and unzip it onto your desktop. The folder should be called “osTicket-Installation-Files” We will use the files in this folder to install osTicket and some of the dependencies.
  Next go to Control Panel -> Programs -> Turn Windows Features on and off -> Install / Enable IIS in Windows WITH CGI World Wide Web Services -> Application Development Features -> [X] CGI
</p>
<br />


  ![image](https://github.com/user-attachments/assets/c3396cf5-2b00-449d-ad84-ef5cd9e088ac)

  ![image](https://github.com/user-attachments/assets/8e40a708-9090-45e4-b963-85d0285fa7e6)

From the “osTicket-Installation-Files” folder, install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi) & then install the Rewrite Module (rewrite_amd64_en-US.msi)

![image](https://github.com/user-attachments/assets/58a23d35-ff98-4afb-b4de-5bda74f68223)

Create the directory C:\PHP

![image](https://github.com/user-attachments/assets/07dbae53-c179-4886-aa25-dcd0f9c1c7a7)

![image](https://github.com/user-attachments/assets/4675fb4d-5562-475d-aebd-6629cc945882)

From the “osTicket-Installation-Files” folder, unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder & install VC_redist.x86.exe.

![image](https://github.com/user-attachments/assets/f619ee0e-2023-47ff-b2ed-95cebb94b8c6)
From the “osTicket-Installation-Files” folder, install MySQL 5.5.62 (mysql-5.5.62-win32.msi)

![image](https://github.com/user-attachments/assets/a718f1d5-8046-44a4-8b95-f9b7a87e60f1)

![image](https://github.com/user-attachments/assets/c373ee45-ef9a-467e-b4f4-041bbc10b52a)

From My SQL Server 5.5 Set up Window- Choose Type: Typical Setup-> Launch Configuration Wizard-> Standard Configuration -> Username & Password: root | execute -> Finish

![image](https://github.com/user-attachments/assets/fc3c8948-556d-4e82-aba3-5bcd1ba3f556)

Click start, open IIS as an Admin

![image](https://github.com/user-attachments/assets/70f08789-542b-4aff-a7ad-de8b6ea4e934)
![image](https://github.com/user-attachments/assets/ebc2314a-09a3-4ba7-b47a-1f08d97a0ffa)
![image](https://github.com/user-attachments/assets/f5d7a52d-11a2-45c5-8f37-3cdd2c3568ad)
![image](https://github.com/user-attachments/assets/be8930e9-517c-4fe6-afbe-14b5506769eb)
![image](https://github.com/user-attachments/assets/7083f12a-6d97-4f53-9724-12ca7588ca09)

Follow the photos to register PHP from within IIS

![image](https://github.com/user-attachments/assets/28d65f60-af15-41b4-9477-8c76afd518e2)
![image](https://github.com/user-attachments/assets/f75f5bca-fbc1-4c03-92e6-00118e9b6608)

Reload IIS (Stop & Start the server)

![image](https://github.com/user-attachments/assets/9de020a4-95e8-4bdc-a0d4-0079efb3abb3)
![image](https://github.com/user-attachments/assets/0d5c14be-1285-4438-b7d4-99d1bb86b028)
![image](https://github.com/user-attachments/assets/cf41f947-139f-4688-b61c-fc1ebeac3e1e)
![image](https://github.com/user-attachments/assets/6f4394fe-36ac-4a4b-9a80-7e52a9a55870)
![image](https://github.com/user-attachments/assets/b43c5a9c-747c-434d-aa58-e63360f9d0e5)

Install OsTicket by unzipping "osTicket-Installation-Files", unzip "osTicket-v1.15.8zip" and copy the "upload" folder into "c:\inetpub\wwwroot"(drag & drop), Rename "upload" to "osTicket". Then Reload IIS (Stop & Start the server) like in the previous step.

![image](https://github.com/user-attachments/assets/b4f666f5-4faf-4024-a182-83dd5ab7bb92)

Go to sites -> Default -> osTicket On the right, click “Browse *:80”

![image](https://github.com/user-attachments/assets/b690ef55-d6fa-4da4-8ed6-8b9628b63194)

***Notice that some extensions are not enabled***

![image](https://github.com/user-attachments/assets/5ca3472a-20eb-4cd8-ae61-1e129d1195e3)
![image](https://github.com/user-attachments/assets/8df71725-e196-4959-84c8-58c81cdd14c5)
![image](https://github.com/user-attachments/assets/3907d715-4971-43d5-a769-6a0009305689)

Go back to IIS, go to sites on the left side->Default->OsTicket. After that double click PHP Manager, Click “Enable or disable an extension” Enable: php_imap.dll Enable: php_intl.dll Enable: php_opcache.dll

![image](https://github.com/user-attachments/assets/6f88b5df-dfa1-418d-88ab-b026ffeb69dd)

Refresh the OsTicket Browser to observe the changes.

![image](https://github.com/user-attachments/assets/86aca96c-fb83-43b8-91bf-10d2fcae7810)

Rename: ost-config.php From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

![image](https://github.com/user-attachments/assets/ded95a3a-606c-4224-b0d9-6118f02e0087)
![image](https://github.com/user-attachments/assets/d42bf340-037f-4867-9fc5-f48acb102a15)
Assign Permissions: right click ost-config.php -> properties->  security -> advanced -> Disable inheritance -> Remove All inherited Permissions 

![image](https://github.com/user-attachments/assets/f4807a3a-370e-40b3-bf15-22a7ebe68c0d)
![image](https://github.com/user-attachments/assets/2d06e4b6-82fa-4247-bb27-b61b20d1effe)
![image](https://github.com/user-attachments/assets/7ef46990-39f6-4f55-ab7a-89aca1f3324e)

Assign new permissions -> Everyone -> All -> Apply -> OK

![image](https://github.com/user-attachments/assets/6fad5b3c-a502-4b17-8ea6-bec506edc917)
![image](https://github.com/user-attachments/assets/20e49a92-3786-456e-9066-d37aa1ed333a)

Click continue, start Setting up osTicket in the browser

![image](https://github.com/user-attachments/assets/bd355eb1-af31-4f5c-8f8d-4e9960bd96ce)
![image](https://github.com/user-attachments/assets/fe5360be-a1ed-4d00-be33-dabadf8e3051)

From the “osTicket-Installation-Files” folder, install HeidiSQL.

![image](https://github.com/user-attachments/assets/ba2ef54c-ee7d-4a08-80ba-d014fec7486b)
![image](https://github.com/user-attachments/assets/bf4c5d7b-7a4a-4948-abaa-d3e35ba7953c)
![image](https://github.com/user-attachments/assets/325c284a-d5cb-4b27-b688-56eb916ca7ae)
![image](https://github.com/user-attachments/assets/a6bdec51-5ffe-4f48-a1aa-34cefc42be71)

Open Heidi SQL and create a new session using the "root" username and password we previously created, connect to the new session and create a database called "osTicket"

![image](https://github.com/user-attachments/assets/6fd320ec-b4ba-42c9-8034-54850900aa93)

Continue Setting up osTicket in the browser MySQL Database: osTicket MySQL Username: root MySQL Password: root Click “Install Now!”

![image](https://github.com/user-attachments/assets/ce359589-920c-4080-b978-22630d2e41f5)

Congratulations, hopefully it is installed with no errors! 
Browse to your help desk login page: http://localhost/osTicket/scp/login.php 

