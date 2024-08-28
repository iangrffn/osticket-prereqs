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






