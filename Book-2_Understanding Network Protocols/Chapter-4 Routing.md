Router is a device that works at layer 3.
Routing means when a router receives a packet from one network that is destined for a device on another network, the router determines the best way to get the packet to its destination
There are three most important uses for routers and that are :
1. Connecting to the internet
2. Connecting remote offices to each other via the internet
3. Managing Traffic in extremely large network

## Important/ Common uses for routers are :
### Connecting to the Internet
A router is required for any network that needs access to the Internet
Such a device is called as an Internet gateway because it serves as the "gateway" to the internet
Components of routers are :
- A router used to connect your private network to your ISP's network
- A small switch typically providing from three to eight ports to connect wired devices such as computer and printers
- A wireless access point (WAP) is used to connect wireless devices such as laptops or smartphones
- A firewall is used to provide protection from intruders seeking to compromise your network
- A DHCP server to provide IP address for the computers and other devices on your network 
This is the setup for Home or Residential network to the internet
![[Pasted image 20250621184736.png]]
This is the type of setup in which ISP provides a cable into your house that connects the to a cable modem which provides a single ethernet port to connect to the residential gateway.
This is the setup for a larger business network to the internet
![[Pasted image 20250621184909.png]]
As we know in large business network the internet speed should be good 
So in this setup the ISP delivers a high speed fiber optic feed to the Ethernet handoff, And that Ethernet handoff provides a cable to gateway router to connect to the switch and wireless access point
The Ethernet handoff establishes what is called the demarcation point usually called simply the demark
The demark is simply dividing line that establishes who is responsible for what For example the ISP is responsible everything between the internet and the demark and the customer is responsible for everything on the private network side of the demark
A gateway router provides several features and that features are:
- Router
- Small switch 
- A firewall
Characteristics of gateway router :
- it has small number of network interfaces
- At min it needs just two interfaces
	1. External Interface
	2. Internal Interface
External interface often labeled WAN on the device, connects to the ISP's feed that means it is the entry and exit point of internet connectivity
The internal interface connects to the private network
If the device includes a switch it will have more than one internal interface
### Connecting remote locations
Routers is used to connect geographically separated offices to form a single network that spans multiple locations.
It means that the creation of WAN that links multiple LANs together
We can do this with the help of pairing a gateway routers to create a secure VPN
CONNECTING TWO NETWORKS via VPN
![[Pasted image 20250621190701.png]]
The routers are configured to provide a VPN that securely connects two networks

### Splitting up Large Networks
Large networks often have need for routes that are internal to the network itself
For Ex : Consider a company that employs several thousand employees on a single campus that consists of sever dozen buildings. For a network like this, routes are used to manage the network by dividing it into smaller, more manageable networks all connected with routers.
INTERNAL ROUTER
![[Pasted image 20250621191021.png]]
This is called an internal routers because it doesn't connect a private network to a public network instead it connects two portions of a larger networks 

## Routing Tables
Routers work by maintaining an internal list of networks that can be reached via each of the router's interfaces. This list is called a routing table
To create a routing table a gateway router that connects a private network to the internet the routing table is created manually with static routes
*Dynamic Routes : GPS that constantly updates based on traffic 
Static Routes : A fixed permanent instruction you've drawn on a map for the router*

To gain the information of an external interface all you need is the IP address, subnet mask and gateway address provided by the ISP
&
To gain the information of internal interface all you need is the network address and subnet mask of the private network for the internal interface.
For complicated environments we use to build dynamic routes. We use dynamic routes because in this route the updates get changed instantly

We will gain the deep knowledge through example & the above photo has the private network for the business and the IP address for the network is 10.0.1.0

for example let assume that in the above picture the six computers in the private network have IP address 10.0.101.1 through 10.0.101.6
& the internal interface on the gateway have the IP address 10.0.1.254
now let's assume that  the ISP provides you with the following information for your ethernet handoff
	IP address: 205.186.181.97
	Subnet mask : 255.255.255.255
	Default gateway : 107.0.65.31
In this example the routing table will looks like this
![[Pasted image 20250622011512.png]]
- Entry : The entry number
- Destination network IP : This is the IP address of the destination network. This column is used in conjunction with the subnet mask column to determine the network to which the packet's destination IP address belongs
- Subnet Mask : it is applied to the destination IP address to determine the destination network
- Gateway : The address of the router that the packet should be forwarded to
- Interface : The interface that the packet should be forwarded through. Here, Internal means the interface to which the internal private network is connected and external means the interface on which the ISP's handoff is connected (in many gateway devices these interfaces are labelled LAN and WAN respectively)
NOW LET'S HAVE A LOOK AT THE FOUR ENTRIES IN THIS ROUTING TABLE
- Entry 1: This entry tells the router what to do with packets whose destination is on the internal network (10.0.1.x). The IP address of the internal network is 10.0.1.0 and the subnet mask is 255.255.255.0. These packets will be sent to the internal interface, whose IP address is 10.0.1.254.
- Entry 2: This entry handles packets whose destination is the gateway’s external interface, which has been assigned the IP address 205.186.181.97 by the ISP. These packets are forwarded to the gateway address on the external interface.
- Entry 3: This entry handles packets whose destination is the ISP’s gateway (107.0.65.31). The 255.255.255.255 subnet mask means that the destination is a specific IP address, not a network. These packets are forwarded to the ISP’s gateway on the external interface.
- Entry 4: This entry handles everything else. The network IP address 0.0.0.0 with no subnet mask means that all packets that aren’t caught by any of the other rules are forwarded out to the ISP’s gateway router (107.0.65.31) on the external interface.