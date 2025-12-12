The version of Hyper-V that comes with the desktop windows is called Client Hyper-V.
Client Hyper-V uses the same type-1 hypervisor as the server-grade Hyper-V
## Understanding the Hyper-V Hypervisor
==REMEMBER==
	Don't be confused by the fact that Hyper-V is an integral part of Windows : Although Hyper-V is built into Windows, Hyper-V is not a Type-2 hypervisor that runs as an application within Windows. Instead Hyper-V is a true Type-1 Hypervisor that runs directly on the host computer hardware. This is true even for the Client Hyper-V versions that are included with desktop version of Windows
In Hyper-V each virtual machine runs within an isolated space called partition. 
Each partition has access to its own processor, RAM, disk, network and other virtual resources
There are two types of partitions in Hyper-V
- A parent partition
- One or more child partition
The Parent partition that hosts the windows operating system that Hyper-V is associated with
Child Partitions host additional virtual machines that you create as needed
When you activate the Hyper-V feature, the hypervisor is installed and the existing Windows Operating system is moved into a virtual machine that runs in the parent partition
Then. Whenever you start the host computer, the hypervisor is loaded, the parent partition is created and Windows is started in a virtual machine within the parent partition
## Understanding Hyper-V virtual Disk
A virtual disk is nothing more than a disk file that resides in the file system of the host operating system.
The file has two extensions that are : 
- .vhd : And older format that has maximum virtual disk size of 2 TB
- .vhdx : A newer format that can support virtual disks up to 64TB

Hyper-V lets you create two different types of virtual disk and that are :
- Fixed-Size Disk : A virtual disk whose disk space is preallocated to the full size of the drive when you create the disk. For example, if you create a 100GB fixed-size disk using the .vhdx format, a .vhdx file of 100GB will be allocated to the drive. Even if the drive contains only 10GB of data, it will still consume 100GB of space on the host system's disk drive.
- Dynamically expanding disk : A virtual disk that has a maximum disk space, but that actually consumes only the amount of disk space that is required to hold the data on the disk. For example, if you create a dynamically expanding disk with a maximum of 100GB but only put 10GB of data on it, the .vhdx file for the disk will occupy just 10GB of the host system's disk drive.
==TECHINCAL STUFF==
	Actually, there's a third type of disk called differencing disk, Which can be used to track changes made to another virtual disk
==TIP==
	Don’t be confused by the names fixed-size and dynamically expanding. Both types of disks can be expanded later if you run out of space. The main difference is whether the maximum amount of disk space allowed for the drive is allocated when the drive is first created or as needed when data is added to the drive. Allocating the space when the drive is created results in better performance for the drive, because Hyper-V doesn’t have to grab more disk space every time data is added to the drive. Both types of drives can be expanded later if necessary.
## Enabling Hyper-V
To enable Hyper-V on a desktop version of Windows, follow these steps
1. Open control panel
2. Choose Programs and Features
3. Click Turn windows feature on or off
	![[Pasted image 20250707114517.png]]
4. Select the Hyper-V feature and click ok
5. When prompted, restart the computer
## Getting Familiar with Hyper-V
To manage Hyper-V there is Hyper-V manager
![[Pasted image 20250707114609.png]]
The Hyper-V manager window is divided into five panes : 
- Navigation : On the left side of the window is a navigation pane that lists the Hyper-V hosts, which Hyper-V calls virtualization servers. There is  just one host is listed my Windows computer. In an enterprise environment where you have more than one host, each of the hosts will be listed in this pane.
- Virtual Machine : This pane lists the virtual machines that are defined for the selected host. you can see several of the Hyper-V virtual machines including several Linux machines and several Windows Server 2019 machines. All of these machines are currently turned off.
- Checkpoints : In Hyper-V, a checkpoint is a recovery point for a virtual machine. You can create a checkpoint when you’re going to make a modification to a virtual machine. Then, if something goes wrong, you can revert to the checkpoint. There are no checkpoints.
- Virtual Machine summary pane : Below the Checkpoints pane is a pane that provides summary information for the virtual machine selected in the Virtual Machines pane. This pane has three tabs: Summary, Memory, and Networking. In the figure, the Memory tab is selected so you can see the memory that has been allocated to the machine.
- Actions : The Actions tab contains buttons you can click to initiate actions for the selected host (DOUG-WIN10) and the selected machine (FED32-01).
## Creating a Virtual Switch
To create a Virtual switch use the virtual switch manager . Here are the steps : 
1. In Hyper-V Manager, Click virtual switch manager
	![[Pasted image 20250707115426.png]]
2. Select the type of virtual switch you want to create.
	Hyper-V Lets you creates three types of switches : 
	- External : A virtual switch that binds to a physical network adapter, which allows virtual machines to communicate with each other, as well as with other computers on your physical network. This is usually the type of switch you should create
	- Internal  : A virtual switch that does not bind with a physical network adapter. This type of switch lets the virtual machine on this computer communicate with each other and with the host commuter, but not with other computers on your physical network
	- Private : A virtual switch that lets virtual machines communicate with each other but not with the host computer or with any computers on your physical network
3. Click Create virtual switch
	![[Pasted image 20250707115742.png]]
4. Type a name for the new virtual switch in the name field
5. Select the physical network adapter you want to bind the virtual switch to
6. If your network has multiple VLANs, click the enable virtual LAN identification check box and enter the VLAN ID for the VLAN you want this switch to connect to 
7. Click Ok
## Creating a Virtual Disk
Here are the steps to create virtual disk : 
1. In Hyper-V manager, click new and then choose hard disk
	![[Pasted image 20250707120041.png]]
2. Click Next
	![[Pasted image 20250707120050.png]]
3. Select VHDX, and then click Next
	![[Pasted image 20250707120111.png]]
4. Select the disk type you want to use 
5. Click Next
	![[Pasted image 20250707120134.png]]
6. Specify the name and location of the new disk
	Type any name you want for the virtual disk drive. Then, click the browse button to browse for the disk location where you want Hyper-V to create the .vhdx file 
==TIP==
	Make sure you choose a location that has enough disk space to create the .vhdx file. If you're creating a dynamically expanding disk, you should ensure that the location has enough space to accommodate the drive as it grows.
7. Click Next
	![[Pasted image 20250707120318.png]]
8. Specify the maximum size for the disk drive
==TIP==
	This page also allows you to copy data either from an existing physical disk drive or from an existing virtual disk drive. Copying data from an existing physical drive is a quick way to convert a physical computer to a virtual computer; just copy the physical disk to a virtual disk, and then use the new virtual disk as the basis for a new virtual machine.
9. Click next
10. Click Finish
## Creating A virtual Machine
To create a virtual machine follow the steps : 
1. From Hyper-V manager, choose new and then choose virtual machine
	![[Pasted image 20250707120555.png]]
2. Click Next
	![[Pasted image 20250707120607.png]]
3. Enter the name you want to use for your virtual machine
4. Specify the location of the virtual machine's configuration file
5. Click next
	![[Pasted image 20250707120638.png]]
6. Specify the generation you want to use for the new virtual machine
7. Click Next
	![[Pasted image 20250707120757.png]]
8. Indicate the amount of RAM you want to allocate for the new machine
	Dynamic Memory == Memory performance
9. Click Next
	![[Pasted image 20250707120805.png]]
10.  Select the virtual switch you want to use for the virtual machine
11. Click Next
	![[Pasted image 20250707120834.png]]
12. Click Next
	![[Pasted image 20250707120858.png]]
13. Click Next
14. Click Finish
## Installing an Operating System
Download the .iso file of that operating system from the browser and after download the .iso (an .iso file is a disk image of a CD or DVD drive)file follow the steps  :
1. From the Hyper-V manager, choose the new virtual machine and click settings
	![[Pasted image 20250707121008.png]]
2. Click SCSI controller in the hardware list. Then click DVD Drive and click add
	![[Pasted image 20250707121031.png]]
3. Click the Image file option, click browse and select the .iso file that contains the operating system's installation program.
4. Click OK
5. With the new virtual machine still selected click connect
	![[Pasted image 20250707121208.png]]
6. Click connect
7. Click start
8. When prompted to press a key to boot from the CD or DVD press any key
9. Follow the instruction of the installation program to install the operating system
