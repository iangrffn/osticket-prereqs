<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com/watch?v=ikG959Q5t9E)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used</h2>

- Windows 10 (21H2)

<h2>List of Prerequisites</h2>

- Azure Virtual Machine
- Internet Information Services (IIS)
- PHP Manager
- Rewrite Module
- VC Redist
- MySQL
- Heidi SQL
- osTicket v1.15.8
Link to downloads: https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6

<h2>Installation Steps</h2>

1.) The first thing you are going to want to do is create a virtual machine by going to https://portal.azure.com/. Setup your virtual machine with Windows 10 Pro, version 22H2. Note, you will want to create a virtual machine with atleast 2 vcpus and 16 gbs of memory.

2.) Once you have created your virtual machine you will want to conncet to it by using the public ip address the vm is setup with. You will connect using the remote desktop connection app.


![image](https://github.com/user-attachments/assets/bd31375a-d5bb-443e-848b-4c8416bcffac)

![image](https://github.com/user-attachments/assets/f8763c9c-4363-425b-b56c-8fbac446c740)


3.) Once you have connected to your virtual machine you will want to go to your control panel. From the control panel open up programs. Select, Turn Windows features on and off.

![image](https://github.com/user-attachments/assets/80c06496-824c-4427-9f24-ca2b15fcfc3e)

![image](https://github.com/user-attachments/assets/5447eabf-a94a-4249-8142-46b80f4a3443)

4.) You will want to install / enable IIS in Windows with CGI and Common HTTP Features

World Wide Web Services -> Application Development Features -> [X] CGI [X] Common HTTP Features

![image](https://github.com/user-attachments/assets/de3d6810-7b8a-4521-8e33-c22f691ac0f2)

![image](https://github.com/user-attachments/assets/5e3dcfc0-d136-4629-8449-08c0dc5d2519)

NOTE Make sure all Common HTTP Features are checked.

To make sure the IIS is installed / enabled go to a browser of your choice and search for 127.0.0.1 It should look something like this.

![image](https://github.com/user-attachments/assets/25c80b6a-f73c-47c9-b343-66bb97c346f5)

5.) Now that the IIS is enabled, From the Installation Files, download and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi) Go through the install wizard and complete the install.

6.) Next from the Installation Files, download and install the Rewrite Module (rewrite_amd64_en-US.msi)

7.) Create a folder in the C drive called PHP.

8.) From the Installation Files, download PHP 7.3.8 (php-7.3.88-nts-Win32-VC15-x866.zip) and unzip the contents into C:\PHP

!! ATTENTION !! If this appears, choose to “Keep” the file:

![image](https://github.com/user-attachments/assets/2492a310-9d82-4540-8324-0eb76cd4c603)

![image](https://github.com/user-attachments/assets/4eb5e76e-4eb0-44f4-a935-be9d04c184d1)

9.) Once you have downloaded and extracted the zip file into the PHP folder on the C drive, download and install the VC_redist.x86.exe from the installation files. Go through the setup wizard to finish setting up and installing the VC_redist.x86.exe.

10.) Download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi) Run the setup wizard: Typical Setup -> Launch Configuration Wizard (after install) -> Standard Configuration ->

Make the new root password: Password1

![image](https://github.com/user-attachments/assets/ec13b0a7-58c6-47e9-9a12-97f712ca2308)

Execute the process on the next page.

![image](https://github.com/user-attachments/assets/0aa21e12-9494-4aa7-bc22-29748abfc7e0)

11.) Now that we have the files downloaded and installed we will want to search for IIS in the windows search bar. Open IIS as an administrator. The program should look like this.

![image](https://github.com/user-attachments/assets/5f4ad5a7-128a-4581-ae2a-6b687c3417af)

12.) We will now want to register PHP from within IIS. Click on PHP Manager

![image](https://github.com/user-attachments/assets/ea6de51c-cf1c-443d-9951-e5a8978d395e)

Register new PHP version.

![image](https://github.com/user-attachments/assets/b8cb1c8f-e471-4d71-b9e0-bea11a5d315d)

You will want to provide a path to the php executable file (php-cgi.exe)). Go to C Drive -> PHP -> click on php-cgi file.

![image](https://github.com/user-attachments/assets/7a98bea9-c9ca-4957-ad43-dbf650b17781)

Restart the IIS server.

![image](https://github.com/user-attachments/assets/3177540a-598a-4c9a-944a-16670cffbfb4)

13.) Install osTicket v1.15.8 -Download osTicket from the Installation Files Folder -Extract and copy "upload" folder to c:\inetpub\wwwroot -Within c:\inetpub\root, Rename "upload" to "osTicket"

Reload IIS again.

14.) On IIS go to sites -> Default -> osTicket -On the right, click “Browse *:80”

![image](https://github.com/user-attachments/assets/14ac9a8b-fe25-4b97-8bfe-657f925e2a5d)

Some extensions are not enabled on the osTicket browser

![image](https://github.com/user-attachments/assets/0c799b86-7d13-43a7-b5fb-65c82bf255d5)

To enable the extensions: -Go back to IIS, sites -> Default -> osTicket -Double click PHP manager -Click "Enable or disable an extension"

![image](https://github.com/user-attachments/assets/24998949-cf3c-430c-9379-03c5eb80e04a)

![image](https://github.com/user-attachments/assets/adf0aaaf-5671-4369-9dcb-cec012f22297)

We will want to enable three extensions from here.

1.) php_imap.dll

2.) php_intl.dll

3.) php_opcache.dll

![image](https://github.com/user-attachments/assets/5c2751ca-819d-418c-aad0-24cee096af78)

15.) Once we have those extensions enabled in IIS, we are going to want to rename one of the files in our osTicket folder. Go into the file explorer and search for C;\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php

We are going to rename the ost-sampleconfig.php to ost-config.php

Now that we have renamed the files, right click on the file and go to properties. From there click security, click on advance, and disable the inheritance. We will select Remove all inherited permissions from this object.

Now we will add new permissions.

Click Add

![image](https://github.com/user-attachments/assets/0edd6c25-b0e5-4404-9749-febbdbdaece7)

Select a principal
![image](https://github.com/user-attachments/assets/ccf440cc-37cf-4255-9ab8-45be41c80b03)

Type "Everyone" in the box.
![image](https://github.com/user-attachments/assets/6ebc4c72-6088-4c2e-aedc-1538aa78ea54)

Make sure Full Control and all the other boxes are checked.
![image](https://github.com/user-attachments/assets/e33e20fc-8a41-4f58-a1e2-ebc8ce4f3043)

Click Apply and Ok.

![image](https://github.com/user-attachments/assets/f71978d5-2be5-482c-8f49-f748487c87e5)

Once that is done we will continue to setup osTicket in the browser. Click Continue on the osTicket browser page. Fill out the page as required except the Database Settings at the bottom of the page. We will get to that.

We will want to download and install HeidiSQL from the Installation Files.
![image](https://github.com/user-attachments/assets/b8fb71ec-0d9a-4705-ac7d-8ab57b2b2372)

When the program is open we will create a new session in it.
![image](https://github.com/user-attachments/assets/44024626-0f14-40e7-90e3-96cbb8ea60f2)


We want to make sure the username is root and the password is Password1.
![image](https://github.com/user-attachments/assets/6d822f1f-e631-4129-9cfc-0c4d116810b5)

Once we are connected to the session we will go back to the browser to finish setting everything up. Under the Database Settings in the browser the username will be root and the password will be Password1.

We will now create a new database within HeidiSQL. In Heidi right click on the left side where is says "Unnamed", select "create new", and then select "database". Name the new database osTicket. Once we have the new database setup go back to the osTicket browser and under MySQL Database type in osTicket.

![image](https://github.com/user-attachments/assets/3aac514a-9352-4c17-b9bc-91afb816b81f)

The last step is to do some clean up. We will want to delete the setup folder in our system. -Delete: C:\inetpub\wwwroot\osTicket\setup Only delete the setup folder and nothing else.

We then will want to set the permissions back to "Read" only in the ost-config.php file.

![image](https://github.com/user-attachments/assets/efedb96d-f426-456b-baf4-e0f76dd2fad9)

![image](https://github.com/user-attachments/assets/0ad295b3-92f8-4f2a-b75b-617aed8940c4)

The last step after that is to login to osTicket on the browser.

![image](https://github.com/user-attachments/assets/07e7c345-c610-4e7c-98d4-11453073fad2)

Congrats! You have now successfully installed and setup osTicket!






























