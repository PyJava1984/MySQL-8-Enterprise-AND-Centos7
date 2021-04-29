# MySQL-8-Enterprise-AND-Centos7

Step by step MySQL 8 Enterprise installation and configure in Centos 7/RHEL 7

#### Requirements
 - Centos 7/RHEL 7
 - MySQL 8 Enterprise

#### State-1: Install centos 7
CentOS is an open-source Linux distribution based on Red Hat Enterprise Linux (RHEL). CentOS 7 is viewed as the preferred option for web hosting due to its stability and active developer community.

In this tutorial, learn how to install CentOS 7 in a few simple steps.



Prerequisites

    Recommended minimum of 10GB of free disk space
    CentOS 7 ISO install file

Follow the Steps to Install CentOS 7

If you are only looking to update or upgrade CentOS, see How to Upgrade or Update CentOS.
Step 1: Download CentOS 7

To download the official and up-to-date CentOS 7 ISO file, navigate to https://www.centos.org/download/.

Our recommendation for non-enterprise environments is to download the DVD ISO option, which includes the GUI. We recommend the Minimal ISO option only for production enterprise environments.


Step 2: Create Bootable USB or DVD

Now that you have downloaded the ISO image, you can create a bootable USB, burn it on a DVD or load the image on a VM.

Several applications can help you create a bootable USB. We recommend using Etcher. Download the application for your system (Windows, macOS or Linux), install and run.

The setup is intuitive and easy:

    Select the CentOS 7 ISO image.
    Insert the USB flash.
    Find the USB and select it in the Select drive step.
    Click Flash.

Step 3: Boot the CentOS ISO File

Upon booting the CentOS 7 ISO file, you can begin the installation process. To do so, select Install CentOS 7. That will start the installer’s graphical interface.

If you are booting from a USB, click the Install to Hard Drive icon on the desktop. That will open the installation wizard.

Select Install CentoOS 7
Step 4: Install CentOS

Before starting the installation process itself, select which language you would like to use during installation. The default option is English.

Select the language to be used for the installation process.

Click Continue to confirm your selection.

Select and configure custom option for the installation.

There are a couple of settings you would want to configure. All items marked with a warning icon must be configured before you begin the installation.

System configurations outlined below may differ based on use case.
Set Date and Time

To set a date and time for the system, click the Date & Time icon under the Localization heading. Select a region/time zone on the map of the world as seen below. Once you have selected your time zone, hit Done to save your changes.
Select the Time zone and Date.
Keyboard Layout

Select the Keyboard option under the Localization heading to set the keyboard layout.

The system default is English (US) and the language you selected in the initial window. Click the plus icon to add more layouts. Move a layout to the top of the list to make it the default option.

Click the Options button to define a key combination for switching between keyboard layouts. When you are satisfied with the settings defined, select the Done button to confirm the changes.
System Language

Next, select the Language Support option under the Localization heading. The language selected in the Welcome to CentOS 7 window will be the default system language. If necessary, select additional languages and hit the Done button once you are finished.

Choose the language for the support service.
Software Selection

Select the Software Selection option under the Software heading. You will see a list of predefined Base Environment options and optional add-ons. This part entirely depends on your needs.

    Minimal Install. This is the most flexible and least resource-demanding option. Excellent for production environment servers. Be prepared to customize the environment.
    Predefined Server Options. If you are 100% certain about the role of your server and don’t want to customize it for its role, select one of the predefined server environments.
    GNOME Desktop and KDE Plasma Workspaces. These environments include a full graphical user interface.

Select option for base installation of CentOS 7.

When you have selected the base environment and optional add-ons, click the Done button. Wait for the system to check for software dependencies before you move on to the next option.
Select Installation Destination

Click the Installation Destination option under the System heading. Check your machine’s storage under the Local Standard Disks heading. CentOS 7 will be installed on the selected disk.

Partitioning

Option 1: Automatic Partitioning

Under the Other Storage Options heading, select the Automatically configure partitioning checkbox. This ensures the selected destination storage disk will automatically partition with the /(root), /home and swap partitions. It will automatically create an LVM logical volume in the XFS file system.

If you do not have enough free space, you can reclaim disk space and instruct the system to delete files.

When finished, click the Done button.

Option 2: Manual Partitioning

Select the I will configure partitioning checkbox and choose Done.

If you want to use other file systems (such as ext4 and vfat) and a non-LVM partitioning scheme, such as btrfs. This will initiate a configuration pop-up where you can set up your partitioning manually.

This is an advanced option that depends on your requirements.
Configuring KDUMP

KDUMP is enabled by default.

To disable the KDUMP kernel crash dumping mechanism, select the KDUMP option under the System heading and uncheck the Enable kdump checkbox. Click the Done button to confirm your changes.

Note: KDUMP captures system information at the time of a crash. It helps you diagnose the cause of the crash. When enabled, kdump reserves a portion of system memory.
Network and Hostname

Click the Network & Host Name option under the System heading.

For the hostname, type in the fully qualified domain name of your system. In our example, we will set the Hostname as my_server.phoenixnap.com, where my_server is the hostname while phoenixnap.com is the domain.

Configure ethernet settings.

Select Configure… and select to add IPv4 settings or IPv6 settings depending on what you have. Add static IP addresses to help identify your computer on the network. Bear in mind that your network environment’s settings define these values.

IPv4 and Ipv6 settings durring CentOS installation.

To add a static IP address:

    Select Manual from the Method drop-down.
    Click the Add button to add a static IP address.
    Enter the information for your network domain.
        IP Address
        Netmask Address
        Gateway Address
        DNS Servers Address
    Click Save to confirm your changes.

By default, all detected Ethernet connections are disabled. Click the ON/OFF toggle to enable the connection. After the installation of CentOS, follow our guide to learn more details about configuring your network settings.

Note: Is CentOS the best option for your server? Refer to the Ubuntu VS CentOS article to see a comparison between the two and decide which one is best for you.
Security Policy

Select the Security Policy option under the System heading. Choose a profile from the list and hit Select profile. Hit the Done button to confirm your selection.
Start the Installation Process

Once everything is set up according to your liking, hit Begin Installation to start the install. This will start the initial installation process.

How to define root user and password.
Define Root Password

To define the root user, select the Root Password icon.

Select a Root Password and re-enter it in Confirm field.

Root user accounts should consist of at least 12 characters, including uppercase and lowercase letters, numbers, and special characters. We cannot stress enough the importance of a well-defined root password.

Click the Done button to proceed.

Define root password for administering the system.
Create User

To begin, select the User Creation option.

Add a new system account user by defining the full name, user name, and password. We recommend you check the Make this user administrator and Require a password to use this account checkboxes. This will grant the user root privileges.

Create user durring CentOS 7 installation.

After you fill in all of the fields and define a secure password, select Done in the upper-left corner of the screen.

Wait for the installation process to complete.

Reboot system after CentOS 7 installation.

Before you start using your new CentOS installation, reboot the system. Click the Reboot button.

Log into the system by using the credentials you defined previously.

#### State-2: Install MySQL 8 Enterprise

Download MySql from "https://edelivery.oracle.com/osdc/faces/Home.jspx" using oracle approved user name and password.

Download package of MySQL Server "V1008574-01".

Step 1. Install MySQL 8 Enterprise

yum install all package of "V1008574-01"

Step 3. Start MySQL Service

Use this command to start mysql service:

service mysqld start

Step 4. Show the default password for root user

When you install MySQL 8.0, the root user account is granted a temporary password. To show the password of the root user account, you use this command:

grep "A temporary password" /var/log/mysqld.log

Here is the output:

[Note] A temporary password is generated for root@localhost: hjkygMukj5+t783

Note that your temporary password will be different. You will need this password for changing the password of the root user account.
Step 5. MySQL Secure Installation

Execute the command mysql_secure_installation to secure MySQL server:

mysql_secure_installation

It will prompt you for the current password of the root account:

Enter password for user root:

Enter the temporary password above and press Enter. The following message will show:

The existing password for the user account root has expired. Please set a new password.

New password:
Re-enter new password:

You will need to enter the new password for the root‘s account twice. It will prompt for some questions, it is recommended to type yes (y):

Remove anonymous users? (Press y|Y for Yes, any other key for No) : y

Disallow root login remotely? (Press y|Y for Yes, any other key for No) : y

Remove test database and access to it? (Press y|Y for Yes, any other key for No) : y

Reload privilege tables now? (Press y|Y for Yes, any other key for No) : y

Step 6. Restart and enable the MySQL service

Use the following command to restart the mysql service:

service mysqld restart

and autostart mysql service on system’s startup:

chkconfig mysqld on

Step 7. Connect to MySQL

Use this command to connect to MySQL server:

mysql -u root -p

It will prompt you for the password of the root user. You type the password and press Enter:

Enter password:

It will show the mysql command:

mysql>

Use the SHOW DATABASESto display all databases in the current server:

mysql> show databases;

Here is the output:

+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| sys                |
+--------------------+
4 rows in set (0.05 sec)


```

 
