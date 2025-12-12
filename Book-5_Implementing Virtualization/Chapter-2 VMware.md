## Looking at vSphere
vSphere is an umbrella term for VMware's virtualization platform.
The features and technologies that vSphere provides are : 
- ESXi: ESXi is the core of vSphere; it is a Type-1 hypervisor that runs on host computers to manage the execution of virtual machines, allocating resources to the virtual machines as needed. ESXi comes in two basic flavors:
	- Installable: The Installable version of software can be installed onto the hard drive on a host computer, much as an other operating system can be installed.
	- Embedded: The Embedded version runs as firmware that is actually built into the host computer. It’s preinstalled into read-only memory by the manufacturer of the host computer.
- vCenter Server: vCenter Server is a server application that runs on Windows Server installed in a virtual machine. vCenter is the central point for creating new virtual machines, starting and stopping virtual machines, and performing other management tasks in a vSphere environment.
- vCenter Client: vCenter Client is a Windows application that you use to access the features of a vCenter Server remotely. vCenter Client is the tool you’ll work with most when you manage a vSphere environment.
- VMFS: VMFS, which stands for Virtual Machine File System, is the file system used by vSphere to manage disk resources that are made available to virtual machines. With VMFS, you can create data stores to access physical disk devices, and you can then create volumes on these data stores to make disk storage available to virtual machines.
## Getting started with VMware workstation Pro
VMware workstation pro is a simplified version of the vSphere environment that provides many of vSphere's feature but does not utilize the Type-1 ESXi hypervisor.
Instead
VMware workstation pro is a Type-2 hypervisor that runs within a windows environment
VMware WORKSTATION PRO MAIN SCREEN
![[Pasted image 20250707124108.png]]
The prompt to press Ctrl+Alt+Del illustarates one of the peculiar details of running a virtual machine within a host operating system
This means that when you press it, Windows tries to ensure that it's you the user who is pressing it and not some malicious program trying to fake a login screen or take control 
![[Pasted image 20250707124417.png]]
If you want to break the bonds of the virtual machine and return to the host computer. press Ctrl + Alt
## Creating a Virtual Machine
When you have your .iso file or installation disc ready to go, you can create a new virtual machine by following these steps : 
1. Click Create a New Virtual Machine on the VMware workstation pro home screen
	![[Pasted image 20250707124611.png]]
2. Choose the installation option you want to use 
	You have two choices ; 
	- Typical : Select this option to create a virtual machine using the most common options. This is the default choice and the one I demonstrate here
	- Custom : Select this option to specify advanced option for your virtual machine
3. Click next
	![[Pasted image 20250707124731.png]]
4. Choose your installation mode and select the installation image 
	You have three choices 
	- Installer Disc : Select this option and then choose from the drop-down list the drive you'll install from if you want to install from an actual CD or DVD
	- Install Disk Image File (iso) : Select this option click the browse button, and browse to the .iso file that contains the installation image
	- I will install the Operating System later  : Select this option if you want to create the virtual machine now but install the operating system later
5. Click Next
	![[Pasted image 20250707124945.png]]
6. If you have a windows sever product key enter it now
7. In the version of windows to install field, choose windows server standard core
8. Enter your full name and password
9. Click Next
	![[Pasted image 20250707125031.png]]
10. Enter a name for the virtual machine
11. Enter the location of the virtual machine's disk file
12. Click Next
	![[Pasted image 20250707125057.png]]
13. Set the size of the virtual machine's hard drive
14. Click Next
	![[Pasted image 20250707125115.png]]
15. Click Finish
	![[Pasted image 20250707125125.png]]
16. Follow the steps to install the operating system
## Installing VMware Tools
When you've installed an operating system into a VMware virtual machine, you should install an important application called VMware Tools before you do anything else. 
VMware tools provides a variety of important functions for a VMware virtual machine :
- Significantly improved graphics performance
- Shared folders, which lets you share folders between the virtual machine and the host, making it easy to exchange files between the two
- A shared clipboard, which lets you copy and paste between the virtual machine and the host
- Synchronized time between the guest and host
- Better control of the mouse between guest and host
To install VMware Tools follow these steps : 
1. Start the virtual machine
2. One the menu of the VMware console window, choose Workstation pro => Manage => Install => VMware Tools
	![[Pasted image 20250707125416.png]]
3. Double-click the DVD drive with the VMware Tools installer mounted 
	![[Pasted image 20250707125436.png]]
==TIP==
	If the setup program doesn't automatically start, press Windows + R, type d:\setup.ext and press enter. This will manually start the setup program
4. Follow the instructions in the setup program to install VMware tools

