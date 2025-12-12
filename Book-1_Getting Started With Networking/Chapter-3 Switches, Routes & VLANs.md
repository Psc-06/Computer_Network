**VLANs** : is a fancy technique that lets you split a single physical network into two or more logical networks 
## Switches
Simple network with four computers connected via a hub (figure)
![[Pasted image 20250618110353.png]]
#### Ethernet Working System
The basic idea of ethernet is that data is sent over network cables in the form of packets. The key elements of the original Ethernet are as follows 
- All devices on the network can access all data sent over the network 
- Every Device on the network has a unique identifier called MAC address
- A data packet includes the MAC address of the packet's intended recipient as well as the MAC address of the sender
- Every device on the network receives every packet that is sent on the network and examines the destination MAC address to determine whether the packet is intended for it. 
	-If the device matches the MAC address it give a sign as "Mine" and if it doesn't it says "Hymph"
- If the destination MAC address is all one (represented as FF-FF-FF-FF-FF) the packet is called broadcast Packet
- Every once in a while two devices try to send a packet at the exact same time  is called collision
#### Disadvantages or Problems of Ethernet 
- The frequency of collisions rises exponentially with the number of devices added to the network 
	-Too many devices lead to collisions due to too many devices it spend many time to resend packets
- The frequency of broadcast packets can quickly increase as more devices are added to the network, further adding to the performance problem and the likelihood of collisions
- Security is difficult to enforce because every device on the network must examine every packet that comes its way. 
	-Even though devices are supposed to ignore packets that aren't meant for them, there is no way to ensure that they do so 
**SWITCH**
A switch is an intelligent hub that has the ability to send the packets to that particular computer.
HUB is a layer-1 device Meanwhile, Switch is a layer-2 devices 
A switch examines the destination MAC address of every packet it receives and forwards the packet only to the port that leads to the packet's intended destination 
Simple network connected with 4 computer via switch
![[Pasted image 20250618111622.png]]
#### Learning 
The switch learns what devices are reachable on each of its ports.
The process of building the MAC address table is called learning and it is one of the three basic functions of a switch. The other two are forwarding and flooding
So how does a switch knows which port wants the packet for that understanding we will take an example
If a switch receives a packet from computer C on port 3 the switch has learned that computer C is reachable on port 3. Then the switch adds the information of the MAC address tables, This table is sometimes referred as forwarding table. So now the switch knows which port needs the packet so the switch will send the packet to port 3 with the MAC address details in it. And if the switch receives a packet from port 3 with the MAC address it would add the following entry to the MAC address table
The table will look like this 
![[Pasted image 20250618112244.png]]
	IMP : A switch port might actually connect to more than one device. For example, suppose port 5 isn’t connected to a computer but to another switch, which in turn has three other computers connected to it. In that case, the first switch can receive packets from three different computers on port 5.
#### Forwarding
The switch forwards incoming packets just to the correct port based on the intended destination.
To understand the mechanism of  forwarding incoming packets we will take a example 
	if a switch receive a packet on port 1 with the intended MAC address given in MAC table, The switch will look up the MAC address in the MAC table and finds that MAC address and react the port that is registered on that  MAC address and then forwards the packet to that port. This process is called Forwarding. 
So there is a case if the destination port is busy sending some some packet that is received from a different port. Or vice-versa then when the port becomes free the switch will transmit the packet to its destination
it's important to understand that the switch does not modify the packet in any way prior to sending it
Switches does not rely on or even know about IP Address it is a layer-2 function and is concerned with MAC address. IP address are layer-3 concern
==TECHNICAL STUFFS== : Here’s where I have to tell you that I lied. It isn’t exactly true
	that switches don’t care about IP addresses. Many advanced switches have layer-3 features that do look at the IP address. But when they do, they’re acting more like routers than switches. Routers work at layer 3 and, therefore, deal with IP addresses.
#### FLOODING
The switch forwards incoming packets to all ports when it hasn’t yet learned how to reach the intended destination.
So if the switch doesn't recognize or is not able to find the MAC address in the MAC address table, The switch has no way to know what port to forward the packet to. So in this case the switch acts like a hub and send the packet to all the available ports. This is called Flooding
#### Collision
Switches minimize the frequency of collisions on the network.
For example if a port 1 receives a packet from computer 1 that is to be sent to computer 2 the switch will forward the packet to port 2 and at the same time if the port 3 receives a packet from computer 3 that is to be sent to computer 4 the switch will forward the packet to port 4. Both of these packets can travel on the network at the same time.
**A switch is a device that divides collision domains**
 Each collision domain consist of just two network interfaces and that are 
 - The port on the switch
 - The port on the destination device
 An eight-port switch divides a single collision domain with eight devices into eight separate collision domains, each with only two devices
### Bridging
A bridge is a device that typically has fewer ports.
The Primary purpose of a bridge is to provide a link between two network.
Bridging is used to connect two different types of network. 
	For Example : suppose your main network uses Cat-5e cable, but you also have a smaller network that uses fiber-optic cable. You can use a bridge to link these two types of networks. The bridge would have two ports: One Cat-5e port and one fiber-optic port. When the bridge receives a packet on the Cat-5e port, it forwards it to the fiber-optic port, and vice versa. 
#### SFP PORTS & UPLINKS
Some switches have special ports called small form-factor pluggable (SFP) ports.
It is used to connect a variety of different types of high-speed networks such as 100mbps with a 1gbps network
SFP is to connect switches to server computers
The interconnection between two switches is often called an uplink
Uplink ports are likely to be the busiest ports on the switch.
	For example : suppose you have a network with 80 computers in which 40 computer are connected to switch A and another 40 is connected to Switch B. Now if a computer on switch A sends a packet to Switch B, So the uplink ports will carry as much as 40 times the amount of traffic that the other ports carry
#### Broadcast Domains
broadcast domain is essentially the area or segment of a network where a broadcast packet will reach every device.
The most common type of broadcast packet is an Address Resolution Protocol(ARP)request. ARP is the protocol used to determine the MAC address of a given IP address. If one IP device wants to send a packet to another IP device, the sender needs to know the MAC address of the recipient. So, the sender broadcasts an ARP request, which is essentially the question “Does anyone know the MAC address of this particular IP address? If so, please let me know.”
## Routers
A router is a layer-3 device that means Routers know about IP address.
A router differs from a switch in following ways : 
- Switches work with MAC address and know nothing about IP address, meanwhile routers work with IP addresses
- Routers can facilitate communication between IP networks and different subnets
	-For example : if your organization has a
	10.0.100.x network and a 192.168.0.x network, a router can enable
	packets to get from the 10.0.100.x network to the 192.168.0.x
	network, and vice versa.
- Routers also enable a private network to communicate with the internet
	-For example : suppose you want to connect your network to the Internet via a broadband cable provider such as Comcast. The cable provider will give you a network interface that has a public IP address. You must then use a router to exchange packets from your private network to the Internet via the public IP address. A switch can’t do that for you.
- Switches split up collision domains
	-The segments created by switches are still part of the same broadcast domain. In contrast, routers split up broadcast domains. So, broadcast packets do not cross the boundaries created by routers.
- Switches typically have a large number of ports often as many as 48 in a single switch 
	-Routers usually have fewer ports, typically between two and eight. (However, routers for very large networks may have many more ports. For example, Cisco makes a router that can accommodate as many as 256 ports in a single chassis.)
	
TWO IP NETWORKS CONNECTED BY A ROUTER (FIGURE)
![[Pasted image 20250618121102.png]]
Now suppose that the computer on the left side of the figure (10.0.100.50) needs to send a packet over to the computer on the right side of the figure (192.168.0.50). The sending computer forms the packet and sends it to Switch 1. Switch 1, in turn, sends the packet to the router. The router examines the destination IP address and determines that the destination computer is on the 192.168.0.50 network, so it forwards the packet over to Switch 2. Switch 2, in turn, forwards the packet to the destination computer.

#### Network address translation
So if a router is connected to a private network, so the most important function of router is routing traffic from all the computers on the private side of the router of the public side which usually has just a single public IP address to accomplish this magic the router uses network address translation (NAT)

#### Virtual Private Network
A virtual Private network (VPN) is a secure connection between two private network over a public network
All the data that flows over the VPN is encrypted. 
VPN connections are often called tunnels because they provide an isolated pathway from one point to another through the internet
There are two common uses for VPNs : 
- To provide remote workers with secure access to your company network ; To do that, you set up a VPN on the router, and then provide your remote workers with the credentials necessary to access the VPN. The remote workers can run a software VPN client on their home computers or laptops to connect to your company network.
- To establish a tunnel directly between routers on two networks that are separated geographically : For example, suppose you have offices in Los Angeles and Las Vegas. You can use routers on both networks to establish a VPN tunnel between them. This effectively joins the networks together, so that devices on the Los Angeles network can freely exchange packets with devices on the Las Vegas network, and vice versa.![[Pasted image 20250618123557.png]]
## VLANs
Advanced switches allow you to create VLANs
It work at layer 2 of the OSI models 
A VLAN can divide a single switch into two virtual switches that behave
exactly as if they were separate switches. This means the following : 
- If a port on one VLAN receives a packet intended for a destination on the same VLAN, the switch forwards the packet to the destination port, the same as if VLANs were not in use.
- When a port on one VLAN receives a packet intended for a destination on the same VLAN that the switch has not yet learned , the switch will flood only those ports that are on the destination VLAN — not all the ports on the switch. Thus, VLANs can reduce traffic caused by flooding.
- When a broadcast packet is received, the switch will forward the packet only to those ports that are on the same VLAN. In other words, VLANs can break up broadcast domains in the same way that a router can.
- If a port on one VLAN receives a packet intended for a different VLAN, a router is required to link the networks. That’s because separate VLANs are, for all intents and purposes, separate networks.
That being said, most switches that support VLANs also support trunk ports, which can switch traffic between VLANs. 
A trunk port is a port that can handle traffic for two or more VLANs.
In VLAN terminology, a port that is configured to operate on a single VLAN is called an access port.
Ports that are configured to work on more than one VLAN are called trunk ports
Note that if you have more than one switch in your network, you can
configure VLANs to work across the switches. For example, you can
create a VLAN for your company’s accounting department — let’s call it
VLAN-Acct. Then you can configure ports on any of your switches as
access ports on VLAN-Acct. In this way, your entire accounting staff
can operate on the accounting VLAN.