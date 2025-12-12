AWS is the grandfather of cloud-based infrastructure providers, it got its start way back in 2002.
## Looking at What Amazon Web Services Can Do
Several categories are there in amazon web services and that are : 
- Compute : Provides cloud-base virtual computing resources. The main service in this category is Amazon's Cloud-based virtualization platform, known as Amazon Elastic Computer Cloud (EC2)
	With EC2, you can create and manage VMs that run at Amazon's data centers
- Networking & Content Delivery : Lets you set up virtual networks that enable your AWS cloud components to communicate with one another and also with your physical network. Amazon Virtual Private Cloud (VPC) lets you set up a private network at Amazon's data centers so that you can extend your own private network into Amazon's cloud, allowing EC2 machines to seamlessly integrate into your own network, in addition, this category includes server specialized features for delivering various types of content
- Storage : Amazon Elastic File System (EFS) is a cloud-based storage system designed to work with EC2 VMs to provide cloud-based data storage
- Database : Relational Database Service (RDS) provides basic relational database capabilities similar to Microsoft SQL Server and several other database offering provide non-relational database services
- Business Application : Features such as Alexa for Business, email and Chime (a cloud-based phone system)\
- Security, Identity & Compliance : Provides basic directory and security services for AWS
- Developer Tools: Provides features for developers creating and managing custom applications on AWS.
- Management & Governance: Features for managing the AWS environment.
- Machine Learning: A variety of tools for artificial intelligence (AI).
- Analytics: Features for managing and analyzing large data sets.
- End-User Computing: Provides several features aimed at end users, including a desktop virtualization solution called Workspaces and a document-management solution called WorkDocs.
AWS also includes Internet of Things (IOT) solutions for managing home appliances
## Creating an Amazon web Service account
To set up your account, just browse to http://aws.amazon.com and
follow the links to set up a free account.
Here's what you get your first year with the free account : 
- 750 hours per month of compute usage on a small VM called a micro instance, which has just one processor core and 1GB of RAM)
- 5GB of EFS storage
- 750 hours per month of Amazon RDS relational database
- An assortment of other free services, too detailed to list here
## Examining the Amazon Web Services Console
To access the AWS console follow these steps : 
1. Go to http://aws.amazon.com
	![[Pasted image 20250708103149.png]]
2. Click the Sign In to the console button
3. Enter your username and click next
4. Enter your password and click sign in
	![[Pasted image 20250708103214.png]]
	AWS CONSOLE
![[Pasted image 20250708103222.png]]
THE SERVICES MENU
![[Pasted image 20250708103239.png]]
EC2 DASHBOARD
## Creating a Windows Virtual Machine
To create a VM, navigate to the EC2 dashboard and follow these steps : 
1. Click the launch instance button
	![[Pasted image 20250708103334.png]]
2. Click the Microsoft Windows Server 2019 Base Image
	![[Pasted image 20250708103414.png]]
	CHOOSING AN INSTANCE TYPE
3. Select the t2.micro instance type and click next, configure instance details
	![[Pasted image 20250708103441.png]]
4. Select the configuration options you want
	The following options are available on this page
	- Number of Instances: Use this option if you want to create more than one VM instance.
	- Purchasing Option: This option doesn’t apply to the t2.micro instance type.
	- Network: Select the virtual network you want to use. If you haven’t yet created a virtual network, you can click Create New VPC to create one.
	- Subnet: Select the subnet you want to use.
	- Auto-Assign Public IP: Use this option to enable automatic assignment of an IP for the instance.
	- Placement group: If you have a large number of VMs, you can place them in separate groups to simplify management, provide redundancy, or improve performance. Leave this option unchecked for now.
	- Capacity Reservation: Lets you choose among several options for reserving capacity for your instance. The default setting, Open, is suitable for most VMs.
	- Domain Join Directory: Use this option to join an Active Directory domain. (Click Create New Directory to create a new directory if one doesn’t already exist.)
	- IAM Role: To join a directory, you must select an IAM role to authenticate your identity. To create one, click Create New IAM Role.
	- CPU Options: Lets you customize the number of processor cores and threads per core.
	- Shutdown Behavior: Use this option to select what happens when the host OS is shut down. The options are Stop or Terminate; in most cases, you should leave this setting set to Stop.
	- Stop – Hibernate Behavior: If you enable hibernation, space is set aside on the OS volume to store the contents of RAM when the computer is stopped.
	- Enable Termination Protection: Enable this feature to prevent the instance from being stopped. If you enable this feature, you’ll have to disable it before you can shut down the machine.
	- Monitoring: Enables monitoring, which gathers statistics about the machine’s performance. Amazon charges for monitoring, so enable this option only if you’re sure you need it.
	- Tenancy: Use this option to select whether you want this instance to run in shared hardware or on dedicated hardware. Amazon charges more for dedicated tenancy, so select shared tenancy unless you specifically need dedicated hardware.
	- Elastic Graphics: Provides high-quality graphics. Most servers do not require this.
	- Credit Specification: If you check Unlimited, your instance is allowed to temporarily burst beyond its normal performance specification without additional charge, provided the hourly average stays within the performance spec of the instance type you selected.
	- Advanced Details: There are also several advanced details you can provide. For demonstration purposes, you can skip these details.
5. Click Next, add Storage
	![[Pasted image 20250708103910.png]]
6. Configure the storage for the VM
	By default a single disk volume called the root volume is created for the instance.
7. Click Next, Add tags
	![[Pasted image 20250708103958.png]]
8. If you want add one or more tags to the instance
9. Click Next, configure security group]
	![[Pasted image 20250708104050.png]]
10. Configure the firewall rules
	The default security group provides a single firewall rule that allows remote desktop protocol (RDP) access from any IP address
==TIP==
Change the source drop-down from anywhere to My IP, AWS will figure out the IP address of your computer and set the rule to allow access only from that IP Address
11. Click Review and launch
	![[Pasted image 20250708104215.png]]
12. Review the settings
13. Click Launch 
	AWS prompts you to select a key pair to provide security for your instance.
	A key pair is combination of a public key that AWS keeps and a private key stored in a file that you're responsible for storing
	![[Pasted image 20250708104358.png]]
	CREATING A KEY PAIR
14. Enter a name for the key pair
15. Click Download key pair
16. Save the key pair file to a safe location
17. Click Launch Instances
	![[Pasted image 20250708104434.png]]
## Managing an Amazon Web Services Virtual Machine
You can manage your VM instances by opening the EC2 Dashboard and then clicking Instances in the menu that appears at the left side of the Dashboard page. 
This brings up a list of all EC2 VM instances,
To manage an instance, right click anywhere in the row for the instance you want to manage. This brings up a context menu with the following commands
![[Pasted image 20250708104614.png]]
- Launch Instances: Lets you create a new AWS instance.
- Launch Instances from Template: Lets you create a new AWS instance from a template.
- Connect: Connects to the instance using Remote Desktop Connection.
- Stop Instance: Shuts down the OS.
- Start Instance: Starts the VM.
- Reboot Instance: Reboots the VM.
- Hibernate Instance: Hibernates the instance, if allowed.
- Terminate Instance: Terminates the instance. This permanently deletes the instance, so use this option only when you no longer need the instance.
- Instance Settings: Lets you change settings for the instance. Note that if the instance is stopped, you can change the instance type to increase the amount of RAM or the processor resources available to the instance.
- Networking: Changes network settings for the instance.
- Image and Templates: Create an image of the instance that you can later use to create new instances. Or, create a template from this image so you can easily create other similar instances.
- Monitor and Troubleshooting: Enables monitoring services for the instance.
## Connecting to an Amazon Web Services Virtual Machine
When an AWS VM is up and running, you can connect to it remotely using remote desktop connection, just as you can connect to any other VM.
The easiest way to do so is to follow these steps ; 
1. In the EC2 Instance dashboard, right-click the instance you want to connect to and choose connect, and then click the RDP client tab
	![[Pasted image 20250708104905.png]]
2. Click Download Remote Desktop FIle
3. Save the RDP file to your computer
4. Back in the connect to your instance dialog box, click get password
	![[Pasted image 20250708104947.png]]
5. Click the browse button, navigate to your key path file, select it and click open
6. Click Decrypt Password
	![[Pasted image 20250708105028.png]]
==TIP==
	Notice that the password generated by AWS consists of 32 random characters. You’ll never in a lifetime commit that to memory, and you should under no circumstances copy and paste this password into a document on your computer. My recommendation is that when you log in to the server, you change its Administrator password to something you can remember without writing down.
7. Navigate to the .rdp file you saved and double-click to open it
8. Enter the username(administrator) and password and click ok