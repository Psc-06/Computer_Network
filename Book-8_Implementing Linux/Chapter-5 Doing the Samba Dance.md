Samba refers to a file- and printer-sharing program that allows Linux to mimic a Windows file and printer server so that Windows computer can use shared Linux directories and printers
# Understanding Samba
There are two many differences between the windows client computer and Linux directories. Some of the differences are :
- Linux filenames are case sensitive, whereas filenames are not
- In Linux, periods aren't used to denote file extensions. Linux filenames don't use extensions
- Windows has file attributes like read-only and archive. Linux doesn't have these
Windows networking uses the Server Message Block (SMB) protocol to manage the exchange of file data among file servers and clients. 
Linux doesn’t have SMB support built in.
Samba is a program that mimics the behavior of a Windows-based file server by implementing the SMB protocol. So when you run Samba on a Linux server, the Windows computers on your network see the Linux server as if it were a Windows server.
Like a Windows server, Samba works by designating certain directories as shares. A share is simply a directory that’s made available to other users via the network.
Each share has the following elements:
- Name: The name by which the share is known over the network.
- Share names should be eight characters whenever possible.
- Path: The path to the directory on the Linux computer that’s being shared, such as \Users\Doug.
- Description: A one-line description of the share.
- Access: A list of users or groups who have been granted access to the share.
## Installing Samba
To install Samba, open a console or terminal window and enter the following command
![[Pasted image 20250714110834.png]]
==TIP==
	One sure way to render a Samba installation useless is to enable the default Linux firewall settings on the computer that runs Samba. The Linux firewall is designed to prevent users from accessing network services, such as Samba. It's designed to be used between the Internet and your local network — not between Samba and your local network. Although you can configure the firewall to allow access to Samba only to your internal network, a much better option is to run the firewall on a separate computer. That way, the firewall computer can concentrate on being a firewall, and the file server computer can concentrate on being a file server.
## Starting and Stopping Samba
Before you can use Samba, you must start its two daemons
Daemon is the Linux term for service a program that runs as a background task
- smb
- nmb
![[Pasted image 20250714111023.png]]
Whenever you make a configuration change, such as adding a new share or creating a new Samba user, you should stop and restart the smb service with this command:
![[Pasted image 20250714111044.png]]
If you prefer, you can stop and start the service with separate commands:
![[Pasted image 20250714111055.png]]
If you're not sure whether Samba is running, enter this command:
![[Pasted image 20250714111108.png]]
To configure Samba to start automatically when you start Linux, use this
command:
![[Pasted image 20250714111121.png]]
To make sure that the chkconfig command worked right, enter this
command
![[Pasted image 20250714111144.png]]
The output will look like this
![[Pasted image 20250714111200.png]]
==TIP==
	You can independently configure services to start automatically for each of the six boot levels of Linux. Boot level 3 is normal operation without an X Server; level 5 is normal operation with an X Server. So setting SMB to start for levels 3 and 5 makes SMB available — regardless of whether you're using a graphical user interface (GUI).
## Editing the smb.conf File
To configure Samba you need to edit the Samba configuration file which is called smb.conf & is usually located in the /etc/samba directory
THE smb.conf FILE
![[Pasted image 20250714111418.png]]
Any line in the smb.conf file that begins with a hash mark(#) or semicolon (;) is a comment
==TIP==
	You can find a version of the smb.conf file that is loaded with comments to help you understand the settings at /etc/samba/smb.conf.example. Plus, many configuration options are commented out — these configuration lines are marked with a semicolon to distinguish them from explanatory text lines, which begin with a hash mark.
The overall structure of the smb.conf file is something like this 
![[Pasted image 20250714111831.png]]
#### Configuring global settings
To make your Samba server is visible on the network, you need to configure its server settings by editing the [Global] section of the smb.conf file.
The settings that you should change are : 
- workgroup: The workgroup name must match the name of the workgroup or domain used by the computers that will access this Samba server.
- server string: You can enter any descriptive text you want for this setting.
- interfaces: Indicates which network interface the Samba server uses. You can omit this option if the computer has just one interface. security: The security model used by the Samba server. The options are as follows:
	- ADS (Active Directory Security): This mode configures the Samba server to use a Windows domain controller to verify the user. If you specify this option, the domain controller will be determined based on the computer's DNS settings.
	- Domain: This mode configures the Samba server to use an old-style Windows NT domain. You should use this option only if your network hasn't been upgraded since Bill Clinton was president.
	- Server: This mode configures Samba to use another Samba server to authenticate users. If you have more than one Samba server, this feature lets you set up user accounts on just one of the servers. Specify the name of the Samba server in which you want to perform the authentication in the Authentication Server text box.
	- Share: This mode authorizes users separately for each share that they attempt to access.
	- User: This is the default mode. It requires that users provide a valid username and password when they first connect to a Samba server. That authentication then grants them access to all shares on the server, subject to the restrictions of the account under which they are authorized.
#### Creating a share
To be useful, a file server should offer one or more shares  directories that have been designated as publicly accessible via the network.
For example, you can use the following command to create a directory named myshare:
![[Pasted image 20250714112137.png]]
Then, to grant full access to all users of this folder, use this command:
![[Pasted image 20250714112151.png]]
After you've created a directory to share, you can create the Samba share by adding a share definition to the end of the smb.conf file. For example:
![[Pasted image 20250714112209.png]]
## Using the Samba Client
It includes a program called smbclient that lets you access Windows file servers from a Linux computer.
The smbclient program works much like an FTP client
smbclient is a command line tool, so you need to log on to a virtual
console or open a terminal window. Then, enter the smbclient
command, followed by the server and share name, like this:
![[Pasted image 20250714112319.png]]
COMMONLY USED SMBCLIENT COMMANDS
![[Pasted image 20250714112353.png]]
![[Pasted image 20250714112358.png]]
{
To configure Samba to start automatically when Linux boots, you use `sudo chkconfig --level 35 smb on`. What do 'level 3' and 'level 5' specifically refer to in this context?
Level 3 is normal operation without an X Server; level 5 is normal operation with an X Server.
Right answer
The document clearly defines these as 'normal operation without an X Server' and 'normal operation with an X Server' respectively.
Semicolons mark configuration options that are commented out, while hash marks mark explanatory text lines.
That's right!
The document states that 'many configuration options are commented out - these configuration lines are marked with a semicolon to distinguish them from explanatory text lines, which begin with a hash mark'.
Which of the following `smbclient` commands would you use to copy a file named `report.txt` from the remote shared directory to your local Linux computer, saving it as `local_report.txt`?
get report.txt local_report.txt
That's right!
`get remote-file local-file` is the correct syntax for copying a remote file to a local destination.
}