# Planning a Windows Server Installation
To install windows server operating system several choices need to make and that choices are : 
#### Checking System Requirements
MINIMUM HARDWARE REQUIREMENTS FOR WINDOWS SERVER 2019 (STANDARD EDITION)
![[Pasted image 20250709095859.png]]
There is no 32-bit version of Windows server 2019. 
64 bit processor is required
To install windows server 2019 on a virtual machine 800MB or ram is needed
#### Reading the release notes
The release notes are available at 
https://docs.microsoft.com/enus/windows-server/get-started-19/rel-notes-19.
#### Deciding whether to upgrade or install
Windows offer two installation modes 
- Full installation 
- Upgrade installation
A full installation deletes any existing operating system it find on the computer and configures the new operating system from scratch.
An upgrade installation assumes that you already have a previous windows server 2016 installation in place. The operating system is upgraded to windows server 2019, preserving as many settings from the previous installation as possible
You cannot upgrade Windows Server 2008 or earlier to Windows Server 2019
Here are some point to ponder before you perform an upgrade installation
- You can't upgrade a client version of windows to a server version
- With an upgrade installation, you don't have to reinstall any applications that were previously installed on the disk
- Always perform a full backup before doing an upgrade installation
#### Considering your license options
Two types of licenses are required to run a windows server operating system
- Server license : Which grants you permission to run a single instance of the server
- Client Access Licenses (CALs) : Which grants user or devices permission to connect to the server
There are two distinct types of CALs 
- Per-user
- Per-device
Per-user CALs : limit the number of users who can access a server simultaneously, regardless of the number of devices (such as client computers) in your organization
Whereas
Per-device CALs : limit the number of unique devices that can access the server regardless of the number of users in your organization
#### Thinking about multiboot
Windows include a multiboot feature that lets you set up the computer so that it has more than one operating system
==TIP==
	Although you may be tempted to use the multiboot features to maintain previous operating system installations, I recommend against it. A much better alternative is to install Windows Server into a virtual machine using virtualization technology such as Microsoft’s Hyper-V or VMware. Virtualization allows you to install a complete operating system such as Windows Server 2019 within an already-installed operating system. (Note that the Windows Server 2019 installation illustrated in this chapter and throughout this book is installed on a Hyper-V virtual machine running within Windows 10.)
#### Planning your partitions
Partitioning enables you to divide a physical disk into one or more separate units called partitions
Each disk can have up to four partitions
All four of the partitions can be primary partitions
A primary partition contains one and only one file system
Windows server 2019 offers you two file systems : 
- NTFS 
- ReFS
NTFS is the tried and true file system that has been the standard file system for going on 20 years.
The partitions that windows server 2019 boots from must be NTFS.
Most common approach to set up the partition are :
- Allocate the entire disk as a single partition that will be formatted with NTFS
- Divide the disk into two partitions
==TIP==
	Note that the disk partitioning scheme is independent of any hardware-based RAID configuration your server may employ. Your server may actually include five physical hard drives that are combined by the hardware disk controller to form a single logical drive, for example. Within this logical drive, you can create one or more operating-system partitions.
#### Deciding your TCP/IP configuration
Before you install the operating system, you should have a plan for implementing TCP/IP on the network. Here are some of the things you need to decide or find out:
- What are the IP subnet address and mask for your network?
- What is the domain name for the network?
- What is the host name for the server?
- Will the server obtain its address from DHCP?
- Will the server have a static IP address? If so, what?
- Will the server be a DHCP server?
- What is the Default Gateway for the server (that is, what is the IP
- address of the network’s Internet router)?
- Will the server be a DNS server?
==TIP==
	In almost all cases, you should assign the server a static IP address
#### Choosing Workgroups or domains
A domain is a method of placing user accounts and various network resources under the control of a single directory database
A workgroup is a simple association of computers on a network that make it easy to locate shared files and printers
Workgroups should be used only for very small networks with just a few users
In installing windows server, always opt for domains
Two basic decision for choosing domains are : 
- What will the domain name be
- What computer will be the domain controllers for the domain
==TIP==
	You can always change the role of a server from a domain controller to a member server, and vice versa, if the needs of your network change. If your network has more than one server, it’s always a good idea to create at least two domain controllers. That way, if one fails, the other one can take over.
# Before You Install
The next topics are applied only to upgrades not for installing windows server 
#### Backing up
Do a complete backup of the server before you begin. 
Although windows setup is reliable, sometimes, something serious goes wrong and data is lost
==TIP==
	You don't have to back up the drive to external media, such as tape. If you can find a network disk share with enough free space, back up to it
#### Checking the event logs
Look at the even logs of the existing server computer to check for recurring errors.
You may discover that you have a problem with a SCSI device or your current TCP/IP configuration 
#### Applying updates
Make sure that the server you’re upgrading to Windows Server 2019 is current with all the most recent Windows updates. Click Start, search for “Updates,” and select Check for Updates. Then apply any updates that are pending.
#### Disconnecting UPS devices
If you’ve installed an uninterruptible power supply (UPS) device on the server and connected it to your computer via a USB cable, you should temporarily disconnect the serial cable before you run Setup. When Setup is complete, you can reconnect the UPS device.
# Running Setup
To install the ISO image of windows server 2019 follow these steps : 
1. Configure the new virtual machine with the specifications you want to use, mount the installation ISO file on the virtual DVD drive, and start the VM
2. Click Next
	![[Pasted image 20250709103015.png]]
3. Click Install Now
	![[Pasted image 20250709103023.png]]
	Four editions are available : 
	- Windows Server 2019 Standard (also known as Server Core), a streamlined version of the operating system that does not have a graphical user interface (GUI). You must manage this edition of the server remotely using PowerShell or Windows Management Console.
	- Windows Server 2019 Standard (Desktop Experience), a more user-friendly version of the server with a GUI modeled after Windows 10.
	- Windows Server 2019 Datacenter, a more advanced (and more expensive) version, without the GUI.
	- Windows Server 2019 Datacenter (Desktop Experience), the Datacenter version with the GUI.
4. Select the edition you want to install and then click Next
5. Click I accept the license term and then click next
6. Click the installation option you want to use
7. Select the partition on which you want to install windows and then click next
8. Enter the Administrator password twice and then click finish
	![[Pasted image 20250709103252.png]]
==REMEMBER==
	Be sure to write the password down somewhere and keep in a secure place. If you lose this password, you won't be able to access your server
	![[Pasted image 20250709103337.png]]
9. Press Ctrl + Alt + Del and log in using the administrator account
	![[Pasted image 20250709103402.png]]
	The server manage dashboard provides link that let you complete the configuration of your server. Specifically, you can
	- Click Configure : This local server to configure server setting such as the computer's name and the domain it belongs to network settings such as the static IP address, and so on
	- Click add roles and features to add server roles and features
	- Click add other servers to manage to manage other servers in your network
	- Click create a server group to create a customized group of servers
	- Click connect this server to cloud services if you integrate cloud services with your server
## Considering your next steps
Follow steps before doing anything else :
1. Rename the server
2. Join it to your domain
3. Apply updates
4. Deploy your antivirus solution 
5. Assign a static IP
# Adding server roles and features
Server roles are the roles that your server can play on your network roles such as file server, web server, or DHCP or DNS server
Features are additional capabilities of the windows operating system itself, such as the .NET framework or Windows Backup
To install server roles follow these steps : 
1. Click add roles and features on the server manager dashboard
	![[Pasted image 20250709103935.png]]
2. Click Next
3. Click Next
	![[Pasted image 20250709103951.png]]
4. Select the server you want to manage and then click next
	![[Pasted image 20250709104010.png]]
5. Select one ore more roles to install 
	![[Pasted image 20250709104027.png]]
6. Click Next
	![[Pasted image 20250709104034.png]]
7. Select the features you want to install 
8. Click Next
9. Click Install
10. Click ok