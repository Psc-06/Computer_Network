Virtual Desktop Infrastructure (VDI)
## Introducing Desktop Virtualization
The term desktop virtualization refers to any software that separates an end-user's Windows desktop environment from the hardware that the environment runs on.
Here are just a few of the problems that desktop virtualization addresses : 
- Windows workstations must be configured individually for each user. If your organization has 100 workstations and you decide to update your accounting software, you have to figure out how to deploy the update to 100 computers.
- Windows software frequently needs to be updated. Updates are normally delivered via Windows Update. However, deploying Windows updates separately to all your desktop computers is fraught with peril. A particular Windows update might work well on 99 percent of all computers, which means that if your organization has 100 computers, that update is likely to not work on at least one of them. That means a trip to that computer to diagnose the problem caused by the update and get the user back up and running.
- If a user’s computer fails, that computer must be replaced. To replace the computer, you’ll need to rebuild the user’s profile, reinstall the user’s applications, and perform other configuration work to restore the user’s desktop environment.
- Windows computers have a dreaded thing called the C: drive. Any data stored on the C: drive belongs to that computer alone and is not easily backed up to the network. Thus, if the user's C: drive dies, its data is likely to die with it.
- If a user moves to another desk or office, the user must take her computer with her.
- If a user wants to work from home, the user can’t easily access her desktop environment from her home computer. There are solutions for this problem, such as remote access software like GoToMyPC (www.gotomypc.com), but those solutions introduce problems of their own.
- If a user has a laptop computer in addition to a desktop computer, the user must make a special effort to ensure that the data on the desktop computer is synchronized with the data on the laptop.
- The user may have devices with different platforms than his or her desktop computer. For example, a user might have a Windows computer at work, a MacBook Pro at home, and an Apple iPad for the road. These platforms aren’t compatible with one another, so the user can’t run the same software on all three.
The advantages of the VDI Technology are : 
- If the user’s computer dies, the user’s desktop does not die with it. You can replace the failed computer with any other computer and simply reconnect to the virtual desktop.
- Operating systems and application software can be centrally managed. There is no need to visit a user’s desk to install or update software.
- The user’s desktop can be accessed from different types of devices. So, a user can access his or her desktop from a Windows computer, a MacBook, an iPad, an Android table, or even from an iPhone or Android phone.
- You can use thin clients at users’ desks rather than full-blown Windows computers. A thin client is a small computer that has just enough processing power (CPU, RAM, and disk) to run the client piece of the desktop virtualization platform. Typically, the thin client runs an embedded version of Linux that is specially configured to run the client software that accesses the virtual desktop. In most cases, the end user is not even aware that this is happening — to the user, the experience is identical to having a standard Windows computer at his or her desk.
- In some desktop virtualization environments, multiple users share a common Windows environment, which means that an application needs to be installed only once for it to be available for multiple users, and operating system patches need to be applied just once rather than to multiple computers.
- All data is kept on the host computers, which means the data can be centrally managed and backed up.
## Considering Two approaches to desktop virtualization
There are at least two distinct approaches to implementing desktop virtualization.
- The first approach is to simply create a separate virtual machine for each user and provide a way for the users to efficiently connect to their virtual machines
	This approach is usually referred to as Virtual desktop infrastructure (VDI)
	VDI solutions are usually built using traditional virtualization process such as Microsoft's Hyper-V  or VMware's ESXi hypervisor
- The second approach is to use a single server that is designed to support multiple users and provide a way for each user to connect to his or her session on the server
	This approach is often called terminal services, because it's based on the terminal services role that is a standard part of all versions of windows server
==TECHNICAL STUFF==
	Technically, with Windows Server 2008, Microsoft changed the name of Terminal Services to Remote Desktop Services to emphasize the role of Terminal Services for virtualizing desktops. The IT industry is pretty reluctant to change its phraseology, however, so most IT professionals still call it terminal services even though that term has been obsolete for almost a decade.
## Looking at VMware's Horizon View
vSphere is designed to create and manage virtual servers that are typically accessed only by IT personnel
VMware offers a product called VMware Horizon View that builds on the core functions of vSphere and adds features specifically designed for desktop virtualization.
Here are short list of some of the most important features of horizon : 
- vSphere Desktop: A version of vSphere specifically designed for running up to tens of thousands of desktop virtual machines
- vCenter Desktop: A version of vCenter designed specifically for managing virtual resources such as hosts, RAM, processors, and disk storage in a virtual desktop environment
- Horizon View: A management tool designed to provision and deploy virtual desktops
- Horizon View Client: Client software for accessing virtual desktops on a variety of platforms, including Windows, Mac, iOS, and Amazon devices
- Horizon View Composer: A tool for cloning desktop VMs and for managing software and operating system updates on pools of similar desktop VMs
## Looking at Citrix XenApp
Citrix XenApp is a desktop virtualization environment that uses Windows Terminal Services to enable multiple users to access remote desktop from a variety of client devices, including Windows, Mac, IOS and amazon devices.
Unlike VMware's horizon view, XenApp does not create a separate virtual machine for each user.
Instead, when users connect to XenApp, they log in to separate terminal services session on a common windows server.
The user then have access to all the resources and application that are available to the Windows Server
![[Pasted image 20250708113211.png]]
CITRIX RECEIVER
![[Pasted image 20250708113239.png]]
CONNECTIN TO A DESKTOP
A user can connect to an individual application rather than to a desktop this feature is called application virtualization.
When you connect to an application, that application runs on the server but only that one application's window is shows on the user's device
![[Pasted image 20250708113400.png]]
VIEWING EXCEL ON AN IPHONE

