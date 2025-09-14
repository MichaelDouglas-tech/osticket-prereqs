# osticket-prereqs<p align="center">
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

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Enable IIS
- PHP
- Install my SQl
- Install url Rewrite
- Configure permission Installed osticket

<h2>Installation Steps</h2>

<p><img width="804" height="923" alt="image" src="https://github.com/user-attachments/assets/d7a569bb-c1c3-4e51-a257-707737640ff8" />





IIS Stands for internet Information Service this is the web server that we run osticket on,so you have to hit the start button then control panel,then from there ,windows feature on ,then enable iis and CGI,Think of IIS as the stage where osTicket will perform. It handles all the web requests so users can access the helpdesk system in their browser.”
</p>
<br />

<p><img width="481" height="371" alt="image" src="https://github.com/user-attachments/assets/446f83f9-5753-49e1-b7ce-740bc31d0814" />


</p>
<p>
Next, we install PHP, because osTicket is written in this language. PHP is the translator that lets the web server understand and run osTicket’s code, turning it into the dynamic pages and forms we interact with.”
</p>
<br />

<p>
<<img width="479" height="438" alt="image" src="https://github.com/user-attachments/assets/78e2e909-c5e8-420f-bc3d-598aef9afe34" />

</p>
<p>
After that, we set up MySQL, the database system. This is where osTicket stores everything — tickets, users, logs, and settings. Without MySQL, the system has no memory. We’ll also create a database and user that osTicket connects to..
</p>
<br /><img width="469" height="354" alt="image" src="https://github.com/user-attachments/assets/21e53faa-53d7-4340-902a-404b0a895008" />
Finally, we enable the URL Rewrite Module in IIS. This makes the web addresses clean and user-friendly, like /tickets/open instead of long confusing strings. It’s essential for navigation and for osTicket to process requests correctly.                                                                                                                                                       <img width="789" height="604" alt="image" src="https://github.com/user-attachments/assets/364e525b-84ac-4f31-b9f8-d45e299ccc5a" />                  
 
When you’ve finished installing osTicket, one of the final and most important tasks is to configure file and folder permissions correctly. If permissions aren’t set right, osTicket won’t be able to read/write necessary files, which can cause errors during setup or while running the helpdesk. Here’s a clear breakdown you can use (almost like a checklist when explaining it to others):

🔑 1. Set Permissions on the include/ost-config.php File

During installation, osTicket needs write access to the configuration file (include/ost-config.php) so it can save your database and system settings.

Step: Grant read/write permissions temporarily for the web server user (on Windows, that’s usually IUSR or IIS_IUSRS; on Linux, often www-data).

After installation is complete, set this file back to read-only. This prevents attackers from overwriting or corrupting your config file.

📂 2. Set Permissions on the Uploads Directory

osTicket stores attachments (files uploaded by staff or users) in the scp/attachments or osticket/uploads folder depending on version.

Step: Grant the web server user read/write/execute permissions here so attachments can be uploaded, saved, and retrieved.

🗂️ 3. Database User Permissions

The MySQL user account created for osTicket should have:

Full rights (CREATE, SELECT, INSERT, UPDATE, DELETE, ALTER) on the osTicket database.

Avoid giving it global admin rights; limit it to the specific osTicket database for security.

🔒 4. Harden Permissions After Install

Revert any temporary write permissions once the setup is complete.

Ensure sensitive files (ost-config.php, core PHP files) are not world-writable.

Confirm that only the web server user has the necessary permissions, not all system users.
