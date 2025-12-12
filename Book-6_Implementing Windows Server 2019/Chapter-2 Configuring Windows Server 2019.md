# Using the Administrator Account
Windows comes with a built-in account named Administrator that has complete access to all the features of the server
==REMEMBER==
	Write down the administrator account password and keep it in a secure location
You cannot delete or disable the administrator account.
==TIP==
	As much as possible, you should avoid using the Administrator account. Instead, you should create accounts for each of your system administrators and grant them administrator privileges by assigning their accounts to the Administrators group.
To hide the true administrator account follow these steps : 
1. Rename the administrator account
2. Create a new account name administrator and assign it a strong password but don't give this account any significant privileges
	This new account will become a "decoy" Administrator account
# Using Remote Desktop Connection
One of the most useful tools available to system administrator is a program called remote desktop connection or RDC.
RDC lets you administer your server computers from your own office
### Enabling remote access
Before you can use remote desktop connection to access a server, you must enable remote access on the server to do That follow these steps : 
1. Open the control panel and click system
2. Click the remote setting link
	![[Pasted image 20250709105504.png]]
3. Select the allow remote connections to this computer radio button 
4. Click ok
Few point to keep in mind using remote access are : 
- You can click the select user button to create a list of users who authorized to access the computer remotely. Note that all members of the administrators group are automatically granted access, so you don't have to add administrators to this list
==WARNING==
	There's no question that RDC is convenient and useful. It’s also inherently dangerous, however. Don’t enable it unless you’ve taken precautions to secure your Administrator accounts by using strong passwords; also, you should already have a firewall installed to keep unwanted visitors out of your network.
### Connecting remotely
To connect through remote desktop client follow these steps
1. Click start, type remote and then choose remote desktop connection
	![[Pasted image 20250709111014.png]]
2. Enter the name of the computer you want to connect to
3. Click the connect button
4. Log on and use the computer
Few tips for working with the remote desktop connection client
- When you’re using the Remote Desktop Connection client, you can’t just Alt+Tab to another program running on the client computer. Instead, you must first minimize the RDC client’s window by clicking its minimize button. Then you can access other programs running on your computer.
- If you minimize the RDC client window, you have to provide your logon credentials again when you return. This security feature is there in case you forget that you have an RDC session open.
==TIP==
	If you use RDC a lot on a particular computer (such as your own desktop computer), I suggest that you create a shortcut to RDC and place it on the desktop or pin the Remote Desktop Connection program to your Start menu or to your taskbar (or both).
- RDC has several useful configuration options that you can access by clicking the options button
# Using Microsoft Management Console
Microsoft Management Console, also known as MMC, is a general purpose management tool that's used to administer many different types of object on a windows system.
It is a framework that accepts management snap-ins which do the actual managing
The main point of MMC is that it provides a consistent framework for building management snap-ins so that all the snap-ins behave in similar ways
we can create own custom management console with just the right combination of snap-ins
### Working with MMC
To access the MMC press the windows key and then select administrative tools
we can also start via a command prompt just type mmc
To open a specific console type the path of the console file after mmc![[Pasted image 20250709111555.png]]
![[Pasted image 20250709111603.png]]
MMC window consists of two panes
- The pane on the left is a tree pane that displays a hierarchical tree of the objects that you can manage
- The pane on the right is a details pane that shows detailed information about the object that's selected in the tree pane
#### Taking an overview of the MMC consoles
Brief overview of the most important consoles are : 
- Active Directory Domains and Trusts: Manages the domain and trust relationships for the server.
- Active Directory Sites and Services: Manages Active Directory services.
- Active Directory Users and Computers: Lets you create and modify user accounts.
- Component Services: Lets you manage how COM+ (Component Object Model) services work on the server. You mess with this console only if you’re involved in developing applications that use COM+ services.
- Computer Management: Provides access to several useful tools for managing a server. In particular, 
  the Computer Management console provides the following management tools:
	- Event Viewer: Lets you view event logs.
	- Shared Folders: Lets you manage shared folders for a file server. In addition to finding out what shares are available, you can use this tool to find out which users are connected to the server and which files are open.
	- Local Users and Groups (available only on servers that aren’t domain controllers): Lets you manage local user and group accounts. For a domain controller, you use the Active Directory Users and Computers console to manage user accounts.
	- Performance: Lets you monitor system performance counters.
	- Device Manager: Lets you manage the hardware devices connected to a server. You’ll probably use it only if you’re having a problem with the server that you suspect may be hardware-related.
	- Disk Management: Lets you view the physical disks and volumes that are available to the system. You can also use this tool to create and delete partitions, set up RAID volumes, format disks, and so on.
	- Services: Lets you manage system services. You can use this tool to start or stop services such as Exchange email services, TCP/IP services such as DNS and DHCP, and so on.
	- WMI Control: Lets you configure Windows Management Instrumentation services, which track management data about computers, users, applications, and other objects in large Enterprise networks.
- DHCP: Manages the DHCP server.
- DNS: Manages the DNS server.
- Domain Controller Security Policy: Lets you set security policy for a domain controller.
- Event Viewer: Lets you view event logs.
- Group Policy Management: Lets you set system policies that can be applied to objects such as users and groups. Internet Information Services (IIS) Manager: Lets you manage the services provided by IIS (Microsoft’s web server) if IIS is installed on the server.
- ODBC Data Sources: Manages database connections that use ODBC. You’ll probably use this console only if you’re a developer or database administrator.
- Performance Monitor: Lets you monitor a server’s performance and twiddle with various settings that can have positive or negative effects on performance.
- Services: Lets you start and stop Windows services. (It’s also available via the Computer Management console.)
## Customizing MMC
![[Pasted image 20250709112114.png]]
First create empty MMC console
To create a custom console, first start Microsoft Management console without loading the console by pressing the windows key typing cmd and pressing enter to open a cmd prompt and then entering the command mmc
To customize an empty console follow these steps : 
1. Choose file => Add/Remove snap-in
	![[Pasted image 20250709112308.png]]
2. Select the snap-in you want to add and then click add button
3. Repeat step 2 if you want to add other snap-ins to the console
4. Click ok