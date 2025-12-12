# Planning a Linux Server Installation
To install the Linux Server some basic things that needed to be done before and that things are :
#### Checking System Requirement
Minimum requirements for Linux are : 
- A 1Ghz Processor or faster
- 1GB of RAM or more
- A hard drive with enough free space to hold the packages that you need to install
- A CD or DVD-ROM drive from which to install operating system
- Just about any video card and monitor combination
- An Ethernet network interface
#### Choosing a distribution
Because the kernel (that is, the core operating functions) of the Linux operating system is free, several companies have created their own distributions of Linux, which include the Linux OS along with a bundle of packages, such as administration tools, web servers and other useful utilities, as well as printed documentation
Some popular Linux Distributions are : 
- Fedora: One of the popular Linux distributions. You can download Fedora free from http://getfedora.org. You can also obtain it by purchasing any of several books on Fedora that include the Fedora distribution on DVD or CD-ROM.
  Fedora comes in two editions: a Workstation edition and a Server edition. The main difference between the two is that the Workstation edition includes a graphical user interface (GUI), whereas the Server edition relies on the command-line interface. Because the GUI is easier to work with when you’re learning Linux, I recommend you use the Workstation edition.
- Ubuntu: A Linux distribution that has gained popularity in recent years. It focuses on ease of use. For more information, go to www.ubuntu.com.
- SUSE: Pronounced SOO-zuh, like the name of the famous composer of marches; a popular Linux distribution sponsored by Novell. You can find more information at www.suse.com.
- Slackware: One of the oldest Linux distributions and still popular, especially among Linux old-timers. A full installation of Slackware gives you all the tools that you need to set up a network or Internet server. See www.slackware.com for more information.
#### Going Virtual
Another common way to install Linux is in a virtual machine running within the Windows operating system.
#### Deciding on your TCP/IP configuration
Some things that you need to find out before installing the OS and that are : 
- The public IP subnet address and mask for your network
- The domain name for the network
- The host name for the server
- Whether the server obtains its address from DHCP
- Whether the server has a static IP address — and if so, what
- Whether the server is a DHCP server
![[Pasted image 20250713110817.png]]
![[Pasted image 20250713110838.png]]
- The default gateway for the server — that is, the IP address of the network's Internet router
- Whether the server is a DNS server
==TIP==
	If the server will host TCP/IP servers you'll probably want to assign the server a static IP address
## Installing Fedora Server
To Install fedora server follow these steps : 
1. Download the Fedora Server 32 .iso file from the Fedora project's download page, connect it to the virtual machine's optical drive, and start the virtual machine  ![[Pasted image 20250713111047.png]]
2. Choose your language and continue
   The page lets you access a variety of configuration options for your Linux server installation and that configuration are : 
	- Installation Destination
	- Network and Host Name
	- Time & Date
	- Software Selection
	- Root Password
	- User Creation
	![[Pasted image 20250713111215.png]]
3. Click Installation Destination![[Pasted image 20250713111232.png]]
4. If necessary, adjust the installation destination settings
5. Click Done
6. Click Time & Date![[Pasted image 20250713111309.png]]
7. Select the correct time zone and location and then click Done
8. Click Software Selection![[Pasted image 20250713111338.png]]
9. Select any optional add-ons you want to include, and then click Done
10. Click Network & Host Name![[Pasted image 20250713111404.png]]
11. Click Configure![[Pasted image 20250713111415.png]]
12. Close the editor window, and then click Done
13. Click Root Password![[Pasted image 20250713111431.png]]
14. To enable the root user, uncheck the Lock Root Account check box, and enter a strong password for the root user
15. Click Done
16. Click User Creation![[Pasted image 20250713111502.png]]
17. Enter the information for the new user
18. Click Done
19. Click Begin Installation![[Pasted image 20250713111535.png]]
20. Click Reboot System![[Pasted image 20250713111549.png]]
![[Pasted image 20250713111611.png]]
![[Pasted image 20250713111631.png]]
