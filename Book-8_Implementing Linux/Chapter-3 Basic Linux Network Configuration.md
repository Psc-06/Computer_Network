# Using Cockpit to configure Network Interfaces
By default, Linux server is configured to use Dynamic Host Configuration Protocol (DHCP), which means that your server has a dynamic and unpredictable IP address.
Before we begin to configure network interfaces it is highly recommended to decide static IP address for the server. And when decided follow these steps : 
1. Open Cockpit by browsing to the address shown in the web console line after you log in to the server
2. Login to Cockpit
3. Click Networking in the navigation bar on the left  ![[Pasted image 20250713184153.png]]
4. Click the etho0 interface![[Pasted image 20250713184208.png]]
5. Click Automatic (DHCP)![[Pasted image 20250713184223.png]]
6. Use the drop-down list to switch from Automatic(DHCP) to Manual   ![[Pasted image 20250713184244.png]]
7. Enter the static IP, Netmask (The subnet mask), and gateway
8. Add DNS servers
==TIP== 
	If you’re setting up this computer to be the gateway router  that will manage traffic between your local network and the Internet,  use a static address that’s easy to remember, such as 192.168.1.1.  
	The subnet mask should be the mask that’s appropriate for the IP  address you choose. For a 192.168.x.x address, use 255.255.255.0.  
	The default gateway address should be the address of the gateway  router that links your network to the Internet. 
	If this computer is the  gateway router, specify the gateway address provided to you by your  Internet service provider (ISP).
9. Enter the IP addresses for the DNS servers that you want to use in the DNS server text box
10. Click Apply    ![[Pasted image 20250713184437.png]]
## Working with Network Configuration Files
LINUX NETWORK CONFIGURATION FILES
![[Pasted image 20250713184541.png]]
#### The Network file
The Network file, which lives in /etc/sysconfig, specifies networkwide
configuration settings for your network. Here's a typical Network
file
![[Pasted image 20250713184607.png]]
This file specifies that networking is enabled, the computer's host name is LSERVER, and the default gateway address is 10.0.0.1.
Now we will tell the validity of the file changes : 
- NETWORKING: Specifies YES or NO to enable or disable networking for the computer.
- HOSTNAME: Specifies the host name for this computer. You should also specify this name in /etc/hostname, although that file is considered obsolete and is used only by some old programs. Note that this can be a simple host name (like LSERVER) or a fully qualified domain name (like Lserver.LoweWriter.com).
- FORWARD_IPV4: Specifies YES or NO to enable or disable IP forwarding. Specify FORWARD_IPV4=YES to set up a router.
- GATEWAY: Specifies the IP address of the computer's Default Gateway. If the network has a gateway router, specify its address here. If this computer is the network's gateway router, specify the gateway IP address provided by your ISP.
- GATEWAYDEV: Specifies the interface (such as eth0) that should be used to reach the gateway.
#### The ifcfg files
Each network interface has an ifcfg configuration file located in
/etc/sysconfig/network-scripts.
The device name is added to the end of the filename
For example, the configuration file for an interface named p2p1 is called ifcfg-p2p1
Here is a typical ifcfg file for an interface that has a static IP address : 
![[Pasted image 20250713184924.png]]
Here is an example for an interface that uses DHCP :
![[Pasted image 20250713184937.png]]
Here, the ifcfg file doesn't have to specify the IP address information because the interface gets that information from a DHCP server.
Now we will discuss the information that we will be seeing in the file : 
- DEVICE: The name of the device, such as eth0 or eth1.
- USERCTL: Specifies YES or NO to indicate whether local users are allowed to start or stop the network.
- ONBOOT: Specifies YES or NO to indicate whether the device should be enabled when Linux boots up.
- BOOTPROTO: Specifies how the device gets its IP address. Possible values are NONE for static assignment, DHCP, or BOOTP.
- BROADCAST: The broadcast address used to send packets to everyone on the subnet: for example, 192.168.1.255.
- NETWORK: The network address: for example, 192.168.1.0.
- NETMASK: The subnet mask: for example, 255.255.255.0.
- IPADDR: The IP address for the adapter.
#### The Hosts file
The Host file is a simple list of IP addresses and the host names associated with each address.
The default Linux Hosts file looks something like this 
![[Pasted image 20250713185154.png]]
Here is an example of a Hosts file that has some additional entries
![[Pasted image 20250713185213.png]]
#### The resolv.conf file
The resolv.conf file lists the DNS nameservers that can be consulted to perform DNS lookups
A typical resolv.conf file look like this 
![[Pasted image 20250713185345.png]]
# Displaying your Network Configuration with the ifconfig Command
Linux doesn't have an ipconfig command like Windows.
Instead, the command that you use to display information about your network configuration is ifconfig
Ifconfig without any parameter will look like this 
![[Pasted image 20250713185520.png]]
There are two important bits of information that unfortunately aren't imported by ifconfig : 
- The gateway address
- The DNS servers
You can find the gateway by running the route command that will look like this
![[Pasted image 20250713185656.png]]
To find the gateway address, enter the following command
![[Pasted image 20250713185720.png]]
This lists the contents of the resolv.conf file, which identifies the DNS servers.