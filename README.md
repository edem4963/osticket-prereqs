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

- Create a virtual machine in azure
- Install / Enable IIS in Windows
- Install PHP manager
- Install PHP
- Download and install MySQL
  
<h2>Installation Steps</h2>
<h4>Install osTicket v1.15.8</h4>

- Download osTicket
- Extract and copy “upload” folder to c:\inetpub\wwwroot
- Within c:\inetpub\wwwroot, Rename “upload” to “osTicket”
  
<br />

![osticket1](https://github.com/edem4963/osticket-prereqs/assets/112492837/e64bf415-cc19-4196-9d9a-9f204c348ed6)

<h4>Reload IIS (Open IIS, Stop and Start the server)</h4>
<br />

![osticket2](https://github.com/edem4963/osticket-prereqs/assets/112492837/48fc5bbc-ba8c-4e31-908a-17fa315cd713)

<br />

<h4>Go to sites -> Default -> osTicket</h4>

- On the right, click “Browse *:80”

<br />

![osticket3](https://github.com/edem4963/osticket-prereqs/assets/112492837/c9802a04-77b6-4ad6-ab5b-773f2bda39ff)

<br />

<h4>Note that some extensions are not enabled</h4>

- Go back to IIS, sites -> Default -> osTicket
- Double-click PHP Manager
- Click “Enable or disable an extension”
- Enable: php_imap.dll
- Enable: php_intl.dll
- Enable: php_opcache.dll
- Refresh the osTicket site in your browse, observe the changes

<br />

![osticket4](https://github.com/edem4963/osticket-prereqs/assets/112492837/36beb5dc-298c-4216-80d9-3f7591a56431)

<br />

<h4>Rename: ost-config.php</h4>

- From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
- To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

<h4>Assign Permissions: ost-config.php</h4>

- Right click ost-config.php go to properties
- Go to security tab
- Disable inheritance -> Remove All
- New Permissions -> Everyone -> All

<br />

<h4>Heidi Sql</h4>

Heidi SQL is a database client. It enables our databases to connect the mySQL. This is required for osticket to keep a database of all support tickets that will be created.

- Click on "New" at the bottom left of Heidi SQL
- Use password and username that you created when installing MySQL

<br />

![osticket6](https://github.com/edem4963/osticket-prereqs/assets/112492837/8cb613a1-4795-4e84-9982-6a4141d3ee44)


<br />

- Create "osTicket" database inside heidi (right click inside left panel -> Create New -> Database)

![osticket7](https://github.com/edem4963/osticket-prereqs/assets/112492837/b9f4a029-9faf-4a55-a032-26a6a09340da)


<br />

<h4>Continue Setting up osTicket in the browser (click Continue)</h4>

- Name Helpdesk
- Default email (receives email from customers)
- Admin account information
- MySQL database information

<br />

<h2>Congrats!! You have a help desk ticketing system</h2>
