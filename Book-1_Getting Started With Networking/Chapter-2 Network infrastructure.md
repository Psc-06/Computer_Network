#### Infrastructure of a network consist of physical elements and that elements are :
- **Cables** : These run through walls and ceiling to reach their destination 
- **Patch Panel** : These are used to organize the cables at the central location
- **Network Switch** : A switch is an intermediate device that sits between the network devices that allows those devices to communicate with each other 
- **Wireless Access Point (WAP)** : A WAP lets device connects wirelessly to the network.
- **At least one router** : A router enables the network to the outside world.  
## Understanding Network Protocols and Standards
The infrastructure of network consists of devices that confirm to well-known standards and protocols.
- #### Protocol
	Protocol is a sequence of steps that each element of a network must follow to enable communication
	Protocol also define the precise formal of all data that is exchanged in a network 
	The internet protocol (IP) defines the format of IP address : four eight-bit number called octets whose decimal values ranges from 0 to 255
- ####  Standard
	Networking standards are like a **universal rulebook or a common language** that all electronic devices (computers, phones, smart TVs, routers, etc.) agree to use so they can understand and talk to each other.	
- ### Open System Interconnection (OSI)
	Network Standards are organized into a framework called the OSI Reference Model. 
	OSI reference model is a type of hierarchy for protocols so that each protocol can deal with just one part of the overall task of data communication.
	It consist of seven distinct layers at which a protocol may operate
	 - **Physical (layer-1)** : it consist of physical components of mechanical and electrical details such as cables, connectors and network interfaces.
	 - **Data link (layer-2)** : Describes the basic techniques that networks use to uniquely identify devices on the network (typically via a MAC address) and the means for one device to send information over the physical layer to another device, in the form of data packets. Switches operate at the data link layer, which means that they manage the efficient transmission of data packets from one device to another.
	- **Network (layer-3)** : Handles the routing of data across networks. Routers operate at the network layer
	- **Transport (layer-4)** : Provides for reliable delivery of packets
	- **Session (layer-5)** : Establishes sessions between network applications
	- **Presentation (layer-6)** : Converts data so that system that use different data formats can exchange information.
	- **Application (layer-7)** : Allows applications to request network services

## Network Topology
The term network topology refers to the shape of how the computers and other network components are connected to each other. Types of network topologies are 
- **Node** : A node is a device that's connected to the network and is essentially any device or point of connection within a network that is capable of sending, receiving or forwarding data. It's a fundamental building block of any network. For example : hubs , routers and modems.
- **Packet** : A packet is a message that's sent over the network from one node to another node. The packet includes the address of the node that sent the packet, the address of the node the packet is being sent to and data.'
### - Bus Topology
In this topology the nodes are strung together in a line 
![[Pasted image 20250617193059.png]]
In bus topology every node on the network can see every packet that is sent on the cable. Each node looks at each packet to determine whether the packet is intended for it. 
Networks that uses switches have a bus tropology
it is suitable for small networks
### - Star Topology
In this topology each network node is connected to a central device called a hub or switch. They are commonly used with LANs
![[Pasted image 20250617193331.png]]
If a cable in star topology network breaks, only the node connected to that cable is isolated from the network. The other nodes can continue to operate without interruption. 
It is suitable for small networks
==TECHNICAL STUFF==
	Its important to understand the difference between a switch and a hub
	When a computer is connected to a hub it sends a packet to all its port that is connected from that port  
	Meanwhile  In switch when a computer is connected it sends a packet to that particular computer, that wants that packet.
 Only networks that use switches have a true star tropology
 In a star tropology, when a switch is used, each computer sees only those packets that were sent specifically to it, as well as packets that were specifically sent to all computers on the network (those types of packets are called broadcast packets)
### - Expanding Stars
For larger network its very common that we need to create more complicated topologies that combine stars and buses.
For example a bus can be used to connect several stars. In this case two or more hubs or switches are connected to each other using a bus. Each of these hubs or switches is then the center of a star that connects two or more computers to the network. This arrangement is used in buildings that have two or more distinct workgroups. The bus that connects the switches is sometimes called a backbone
Another way to expand a star tropology is to use a technique called daisy-chaining. In this chaining, a switch is connected to another switch as if it were one of the nodes on the star. Then this second switch serves as the center of a second star.
### - Ring Tropology
It is a third type of network tropology.
![[Pasted image 20250617195909.png]]
In ring tropology packets are send around the circle from computers to computer. Each computer looks at each packet whether it is needed or not. If not, the packet is passed on to the next computer in the ring.
Two popular networking technologies used rings that are 
ARCNET & Token ring
ARCNET is still used for certain applications such as factory automation, but its rarely used in business network.
Token Ring is still a popular network technology for IBM midrange computers.
### - Mesh Topology
Fourth type of network topology known as mesh
![[Pasted image 20250617200250.png]]
It has multiple connections between each of the nodes on the network.
The advantage of a mesh topology is that if one cable breaks the network can use an alternative route to deliver its packets
It is often used to link switches in a LAN
It is also very common for metropolitan or WANs

## Considering Cable
Network Cable is the most important components of layer 1 in OSI Reference Model.
- #### Twisted-Pair Cable
	We call this cable as twisted pair because inside the outer sheath of the cable are four pairs of small insulated wire. These pairs are color coded : blue, green , orange and brown.
	The Two wires that make up each pair are twisted together in a way that prevents the electrical signals within each pair from interfering with the other pairs
	Examples of twisted-pair cable are Cat-5e (data speed is about 1gpbs and the length of the cable is 100 meters) and Cat-6 (data speed is about 10gbps and the length of the cable is 55 meters) 
	They are also used to connect telephone lines with the router or the cable that we connect with printer is also a twisted-pair cable
- ####  RJ-45 Connectors
	Twisted-pair cable is attached to network devices using a special type of connector called an RJ-45. For the cable to meet the Cat-5e standards, the twists of the individual pairs must be maintained all the way up to the RJ-45 connector 
	![[Pasted image 20250617212537.png]]
	So the big one where the cable will get insert is female connector and the cable that will go inside is the male connector.
- #### Patch panels & Patch cables
	A **patch panel** is like a **centralized sorting station or a hub of wall jacks** for all the permanent network cables running throughout a building. Instead of having long cables directly connecting every computer to a router or switch, they all come to the patch panel. Then, short **patch cables** are used to make flexible connections between these permanent cables and the actual networking equipment (like switches), making the whole network much tidier, easier to manage, and simpler to troubleshoot.
	%% A patch panel by itself doesn’t actually do anything. Its job is
	simply to provide a central collecting point for all your network
	cables so that you can easily use patch cables to connect the cables
	to other devices, such as switches or servers. %%
- #### Repeaters & Hubs
	A repeater is a layer-1 device that is designed to overcome the max length limitation of twisted-pair network cables.
	It contains two RJ-45 Ports 
	A repeater is connected internally by an amplifier. Electrical signals received on either of the two ports are boosted by the amplifier and sent through the other port.
	A hub is a repeater with more than two ports. For example, a hub may have four or eight ports. These ports can each connect to another device on the network such as a client computer, a server, or a printer. A port on a hub can also connect to another hub, so that (for example) an eight port hub can connect to seven computers and another eight-port hub, which can connect to seven more computers. In this way, two eight-port hubs can connect 14 computers to each other.
	The second most important thing to know about hubs is that an electrical signal received on any of the hub’s ports is amplified and repeated on all the other ports in the hub. So, in an eight-port hub, any electrical signals received on port 1 are amplified and then sent out on ports 2 through 8. Any devices that are connected to ports 2 through 8 see the signals that were received on port 1. The same is true for signals received on any of the other ports; for example, any signals received on port 4 will be amplified and repeated on ports 1 through 3 as well as ports 5 through 8.
- #### Switches 
	A switch is a layer-2 device that is similar to a hub in that it allows you to connect more than one device, and packets received on one port are relayed to other ports.
## Pursuing Ports, Interfaces and MAC Addresses
Every network interface must have a unique identifier called a MAC address (MAC stands for media access control)
MAC addresses are important because they provide the means for a network to keep track of the devices that make up the network. Without MAC addresses, it would be impossible to know what devices are on the network. And it would be impossible to send information to a particular device or to know which particular device sent information.
Physical address == MAC address
%% MAC addresses are a part of layer 2 of the OSI Reference
Model, called the link layer. This layer is responsible for the
exchange of basic information on a network. The ability to uniquely
identify every device on a network is a key component of enabling
that to happen. %%
MAC addresses are of 48-bits in length. 
This is how a MAC address looks like 
E8-9E-B4-49-43-E5  
	==TIP== : **A MAC address is connected with the motherboard so the MAC address will never be changed but if a computer has separate NIC then the MAC address is a part of the card not the computer. So if we remove the NIC from one computer and install it in another the MAC address of the another card will be same as before we can say that MAC address travels with the card 

## Pondering Packets
When two or more devices connected to a network via cables they exchange information via packets which are relatively small units of data that are sent and received through the network interface and cables. A network packet always originates at a single network interface, called the sender and it's usually sent to a single network interface called destination.
==TECHNICAL STUFFS==
	The term frame is often used instead of packet, but technically they’re not quite the same. Every packet begins with a preamble, which consists of 56 bits of alternating zeros and ones. This preamble is used by the electronic circuitry of the interfaces to get their clocks synchronized properly so they can accurately read the rest of the packet. It’s the rest of the packet that is technically called the frame. In other words, a packet consists of a preamble followed by a frame. Because the preamble is of concern only to the electronic engineers that design network interfaces, most non engineers use the terms packet and frame interchangeably.
Ethernet has a standard packet format that all packets sent on an ethernet must follow. An Ethernet packets contains the following information 
- **Preamble**: The preamble consists of 56 bits of alternating ones and zeros and is used to synchronize the precise timing required to read packet data.
- **Start-of-frame marker**: A start-of-frame marker is a single byte that indicates that the frame is about to begin.
- **Destination MAC address (six bytes).**
- **Sender MAC address (six bytes).**
- **Tag**: The tag, which is used to support virtual local area networks (VLANs), is optional. A VLAN lets you divide two or more distinct LANs on a shared physical infrastructure.
- **Ethertype** **(two bytes)**: This field indicates the specific protocol that is contained in the payload.
- **Payload**: The payload contains the actual data being sent by the packet. The payload can be anywhere from 46 to 1,500 bytes. If the information that needs to be sent is longer than 1,500 bytes, the information must be broken into two or more packets, sent separately, and then reassembled when the packets reach their destination. (The tasks of breaking up and reassembling the data are handled by protocols at higher layers in the OSI framework; Ethernet itself has no understanding of what is in the packets it sends.)
- **Frame check sequence (four bytes)** : The frame check sequence (FCS) is used to ensure that the frame data was sent correctly. Basically, the interface that sends the packet uses an algorithm to calculate a four-byte number based on the contents of the frame and saves this number in the FCS field. When the packet is received, the receiving interface repeats the calculation, and then makes sure that the number recorded in the FCS portion of the packet matches the number it calculated. If the numbers disagree, the packet got garbled in transmission and is discarded.
**MAIN POINTS TO REMEMBER** : 
- Ethernet packets contain the MAC addresses of the sender and the receiver.
- The payload of an Ethernet packet is almost always a packet created by another higher-level protocol such as IP.
- Ethernet packets can contain a tag field used to implement VLANs, which provide an important means of organizing a large network into smaller parts that can be more easily managed.
## Dealing with Broadcast Packets
Some packets called Broadcast packets are intended to be received by every device on the network. Example of a broadcast Packet is FF-FF-FF-FF-FF-FF----
The interfaces will receive this packet inspect the destination and will send the packet up to the next higher protocol.
One of the most common users of broadcast packets is Dynamic Host configuration Protocol (DHCP) which allows computer that join a network to be assigned an IP address. 
When an interface card is connected to a network it send a broadcast msg. Every device on that network will see that msg but only THE DHCP will response