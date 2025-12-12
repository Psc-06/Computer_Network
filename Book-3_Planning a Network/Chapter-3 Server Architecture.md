The smallest network require at least 2 domain controllers plus additional servers to satisfy the needs of your users.
Consolidating server functions into a smaller number of servers can save in licensing and administration costs. For example, if you can support all your functions on 6 servers rather than 12, you only need to purchase 6 licenses of Windows Server and you only need to keep 6 servers up to date rather than 12.
On the other hand, overloading several functions on a single server increases risk. For one thing, the more complicated a server is, the more likely it is to malfunction. And if you need to reboot the server or take the server down for repairs, you’ll have downtime on multiple functions
Active directory and email should be isolated on their own server
## Deciding Which Servers You need
#### Domain Controllers
Your active directory infrastructure should have at least two domain controllers
In addition, you should isolate the domain controller function to single purpose servers to minimize any required downtime. For example, if a domain controller doubles as a file server, you may have to take the server down to add disk space. That’s a routine operation for a file server, but you don’t want to impose the need to take down Active Directory just to increase disk space on a file server. Best to keep the domain controllers on separate servers.
Note that DNS and Active Directory are pretty much intertwined and dependent on one another, so it’s common to enable DNS on a domain controller. In fact, Microsoft actually recommends that you combine DNS and Active Directory on your domain controllers, because Active Directory depends on DNS for name resolution.
#### DHCP servers
DHCP is a core service that is required for every network to run smoothly.
Most DHCP implementations on routers aren't suitable for larger networks
Technically, you can run DHCP on one of your domain controllers, but Microsoft recommends against it for two reasons:
- Performance : On a large network, DHCP can suck a lot of performance from a server, which can slow down active directory
- Security : Running DHCP on a domain controller can potentially Compromise the security of the domain controller
Its recommended to set up a separate server devoted to DHCP
#### Mail servers
A mail server is a server that handles the network's email needs.
Some of Its configure with email server software such as Microsoft Exchange Server.
Exchange server is designed to work with Microsoft Outlook, the email client software that comes with Microsoft office
Some of the features of Exchange server are :
- Calendaring and scheduling meetings
- Collaboration features that simplify the management of collaborative projects
- Audio and Video Conferencing
- Chat Rooms and Instant Messaging (IM) services
- Microsoft Exchange forms designer, which lets you develop customized forms for application such as vacation requests or purchase order
It is always a mistake to combine exchange with any other server role email should always be installed on its own dedicated server
Many organization are not installing exchange on their own servers and instead using the exchange online feature of office 365 for their email.
#### File servers
File servers provide centralized disk storage that can be conveniently shared by client computers on the network.
The most common task of a file server is to store shared files and programs
File servers must ensure that two users don't try to update the same file at the same time. The file server locked the file when a user updates the file.
And the file server locked the whole document for document files
For database files, the lock can be applied just to the portion of the file that contains the record being updated
#### Print Servers
Although it isn’t necessary, a server computer can be dedicated for use as a print server, the sole purpose of which is to collect information being sent to a shared printer by client computers and print it in an orderly fashion.
The printer function of high speed multifunction copier can be managed through printer server
if we don't want to setup the print server we can also connect the printer through IP addresses too
Server disadvantages of that are :
- You have to manage drivers for each computer separately. If you have 50 users connected to a printer and you need to update the driver, you’ll have to update 50 computers.
- Some users will inevitably mess up their print driver configuration. You’ll get called to fix it.
- You lose overall control of the printer. There is no centralized print queue and no ability to manage all your printers from a single point.
#### Web servers
A web server is a server computer that runs software that enables the computer to  host an internet website.
The two most popular web server programs are :
- Microsoft's Internet Information Services (IIS)
- Apache (Managed by apache software foundation)
However, it’s very common to set up internal web servers for your company’s intranet  that is, for web pages that are meant to be used within your company, not by users outside your company. If you intend to support a company intranet, you’ll need to set up a separate web server for it.
#### Database Servers
A database server is a server computer that runs database software such as Microsoft's SQL server 2017
Database servers are usually used along with customized business applications, such as accounting or marketing systems
#### Application Servers
An application server is a server computer that runs a specific application. For example, you might use an accounting application that requires its own server. In that case, you’ll need to dedicate a server to the accounting application. Again, application servers are typically complicated enough and important enough to merit their own servers. It’s not a good idea to bundle your accounting server with your print server; you don’t want the entire accounting department calling your desk if you need to reboot the print server.
#### Backup Servers
Depending on the backup software you use, you may need to provide a separate server that is devoted strictly to backing up your other servers. This is especially true if you back up to tape, as most tape devices don’t connect via the network, but instead connect directly to a server. Isolating the important backup functions to a separate server is a great idea so backups don’t interfere with other server processes, and vice versa.
#### License Servers
Some organization use software that requires licenses that are distributed form a centralized license server.
For example, engineering firms often use computer-aided design (CAD) software such as AutoCAD, which requires a license server. In that case, you'll need to set up a server to handle the licensing function
#### Deployment Servers
A deployment server is a server dedicated to the task of automatically installing windows images on network computers.
it means installing the entire operating systems from scratch. Used for brand new computers, replacing a faulty OS, or standardizing many computers
Updating windows software. Applying patches, fixes of feature upgrades to an already installed operating system
Microsoft provides support for this  capability built in to windows server through a server role called Windows deployment services
Other companies that provide similar services that are more comprehensive and easier to use include Symantec ghost (it is a disk cloning and backup tool) and acronis snap deploy (Acronis Snap Deploy is a comprehensive disk imaging and deployment software solution designed to streamline the process of provisioning and re-provisioning multiple computers)
#### Update servers
An update server is a server devoted to managing updates to windows computer
The simplest and easiest way to set up an update server is to use Windows Server Update Services (WSUS), a built-in component of all windows server operating system
#### Virtualization management platform
If you’re using a virtualizing platform (and you should be!), you’ll need a server dedicated to managing all your virtual servers, network, and storage. For VMware, this management server is called vCenter. For Hyper-V, it’s System Center Virtual Machine Manager. Either way, you’ll want to devote one server to the management of your virtualization environment.
## Connecting Your Servers
Its the best to use the fastest connection speed possible for each server
CONNECTING SEPARATE PHYSICAL SERVERS TO MULTIPLE CORE SWITCHES CAN GET COMPLICATED
![[Pasted image 20250701192205.png]]
Two core switches for all the servers and providing a separate connection from each server to each of the core switches.

| Feature        | Switches                                                          | Core Switches                                                                           |
| -------------- | ----------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| Primary Role   | Connect and devices to the network provide network access         | High-speed backbone fast reliable forwarding of large data volumes                      |
| Network Layer  | Edge of the network closest to the users                          | Center/core of the network connects distribution switches, data centers                 |
| Typical Speed  | 10/100/1000 Mbps gigabit ethernet for end devices                 | 10,40,100 Gbps or higher for network links                                              |
| Port Density   | High for many end devices                                         | May have fewer physical ports, but highly modular for high-speed links                  |
| Layer function | Primarily layer 2, some basic layer 3                             | Primarily layer 3 advanced routing protocols                                            |
| Key Features   | VLANs, PoE, port security, basic Qos                              | High Backplane capacity, Advanced layer 3 routing, redundancy, advanced QoS Scalability |
| Reliability    | Designed for local segment reliability                            | Critical for network uptime, often have redundant components                            |
| Cost           | Generally less expensive per port                                 | Significantly more expensive due to specialized hardware and features                   |
| Analogy        | Local streets in a neighborhood connecting houses to bigger roads | Major expressways and highway interchanges                                              |
PoE(Power over Ethernet) is a technology that allows ethernet cables to transmit both data and power simultaneously using a single network cable
QoS(Quality of server) is a set of technology that work on a network to guarantee its ability run high-priority applications and traffic under limited network capacity