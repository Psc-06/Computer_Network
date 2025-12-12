Protocols make it possible for the various components of a network to communicate and standards make it possible for difference manufacture network components to work together
## Protocols
Protocol is used to communicate through network 
==REMEMBER==
	Computer network depends upon many different types of protocols. These protocols are very rigidly defined and for good reason. Network interfaces must know how to talk to other network interfaces to exchange information operating systems must know how to talk to network interfaces to send and receive data on the network and application programs must know how to talk to operating systems to know how to retrieve a file from a network server 
Protocols come in many different types. At the lowest protocol it represent an electrical signal as 1 and 0. And at the highest level protocol say a computer user to send an email to another computer 
==TIP==
	Protocols tend to be used together in matched sets called protocol suites. The two most popular protocol suites for network are TCP/IP and Ethernet. TCP/IP originally developed for UNIX networks, is the protocol of the internet and most local area networks (LANs) Ethernet is a low-level protocol that spells out the electrical characteristics of the network hardware used by most LANs
## Standards
A standard are industry-wide protocol that allows to match and mix equipment from different protocol this equipment will last if the standard protocols suits that standards. It should be able to coexist on the same network
The five most important organizations are :
- American National Standard Institute (ANSI) : It is the official standards organization in the united states
- Institute of electrical and electronics engineers (IEEE) : it's an international organization that publishes several key networking standards
- International organization for standardization (ISO) : A federation of more than 100 standards organizations throughout the world
	-==TECHNICAL STUFF==
		if you're wondering why the acronym for international organization for standardization is ISO and not IOS the answer is simple : ISO is truly an international organization and although it is known as the international organization for standardization in English-Speaking countries, it goes by different names in non-English-Speaking countries
- Internet Engineering Task force (IETF) : The organization responsible for the protocols that drive the internet
- World Wide Web Consortium (W3C) : An international organization that handles the development of standards for the world wide web
## OSI Reference Model
It is not a networking standard Rather OSI model is a framework into which the various networking standards can fit. The OSI models specifies what aspects of a network's operation can be addressed by various network standards
In Short OSI model is sort of a standard of standards
SUMMARIZATION OF SEVEL LAYER OF OSI MODEL
![[Pasted image 20250619191234.png]]
The first three layers are called the lower layers they deal with the mechanics of how information is sent from one computer to another over a network
Layer 4 through 7 are sometimes called the upper layers. They deal with how application software can relate to the network through application programming interfaces
==REMEMBER==
	The seven layers of the OSI model are a somewhat idealized view of how networking protocols should work . In the real world, actual networking protocols don't follow the OSI model to the letter. The real world is always messier. Still the OSI model provides a convenient if not completely accurate conceptual picture of how networking works
#### The physical layer
The  bottom layer of the OSI model is the physical layer. 
Another aspect of the physical layer is the electrical characteristics of the signals used to transmit data over the cables from one network node to anther. it only transmit the basic values of 1 and 0.
One type of physical layer device commonly used in networks is a repeater which is used to regenerate the signal whenever you need to exceed the cable length allowed by the physical layer standard.
Previously we used to use physical layer called hubs. Hubs are known as multiport repeaters 
The network adapter (NIC) installed in each computer on the network is a physical layer device 
To access the adapter's properties dialog box in windows 
control panel >  network and internet >  network and sharing center > Change adapter settings
![[Pasted image 20250619195457.png]]
#### The Data link Layer
The data link layer is the lowest layer at which meaning is assigned to the bits that are transmitted over the network. 
It address things such as the size of each packet of data to be sent, each packet is delivered to the intended recipient and way to ensure that two or more nodes don't try to transmit data on the network at the same time
It also provides basic error detection and correction to ensure that the data sent is the same as the data received 
To access MAC address for a computer's network adapter follow the steps
Command windows > ipconfig/all
![[Pasted image 20250619195824.png]]
The physical address section is the MAC address of a computer network 
==TECHNICAL STUFF==
	One of the most important function of the data link layer is to provide a way for packets to be sent safely over the physical media without interference from other nodes attempting to send packets at the same time. The two most popular ways to do this are CSMA/CD And token passing (CSMA stands for Carrier Sense Multiple Access / Collision Detection) Ethernet networks use CSMA/CD and token ring network use token passing 
	CSMA/CD and Token Passing are both methods used to control how devices on a shared network access the communication medium (like an Ethernet cable).
	Imagine a single road where many cars (data) want to travel. How do you decide which car goes when, and what happens if two cars try to go at the same time? CSMA/CD and Token Passing are different "traffic laws" for this road.
	
| Feature        | CSMA/CD                                                         | Token Passing                                                                 |
| -------------- | --------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| Access Methods | Contention-based(listen, then transmit)                         | Controlled access (pass token)                                                |
| Collisions     | Possible and detected handles by backoff                        | Eliminated by design                                                          |
| Determination  | Non-deterministic (can't guarantee access time)                 | Deterministic(Predictable access time)                                        |
| Efficiency     | High under light load degrades with collisions under heavy load | Good under heavy load some overhead even under light load (waiting for token) |
| Complexity     | Simpler hardware implementation                                 | More complex hardware/software for token management                           |
| Common use     | Older Wired Ethernet(half-duplex)                               | Token Ring, Token bus, FDDi                                                   |
| Current Status | Largely obsolete in modern full-duplex Ethernet                 | Largely obsolete, replaced by Ethernet                                        |

[[Data-link layer]]

Two types of data link layer devices are commonly used in networks : 
- **Bridge** : An intelligent repeater that's aware of the MAC address of the nodes on either side of the bridge and can forward packets accordingly
- **Switch** : An intelligent hub that examines the arriving packets to determine which port to forward the packets to 

Another imp layer 2 concept is the idea of virtual local area networks (VLANs). It allows you to create separate isolated networks that share devices

#### The network layer
It handles the task of routing network message from one computer to another.
The two most popular layer 3 protocols are IP and IPX (internet packet exchange)
Network layer protocols provide two important functions 
- Logical addressing 
- Routing
###### -Logical addressing
Logical addressing means that you can access a network device by using an address that you assign
==REMEMBER==
	Another way to display system information of network is to press windows key and search for system information 
	![[Pasted image 20250619220210.png]]
###### -Routing
Routing comes into play when a computer on one network needs to send a packet to a computer on another network. 
An important feature of routers is that you can use them to connect networks that use different layer 2 protocols

#### Transport Layer
It is the layer where you find two of the most well-known networking protocols 
- TCP (Typically paired with IP)
- SPX (sequenced packet exchange) (Typically paired with IPX)
The main purpose of the transport layer is to ensure that packets are transported reliably and without errors.
TCP is connection-oriented transport layer protocol
The connectionless protocol that woks alongside TCP is user datagram protocol (UDP)
To view the information about the status of TCP and UDP connections : Run the Netstat command in cmd
![[Pasted image 20250619221056.png]]

To see the numeric network address instead of the names 
Write the command Netstat /N
![[Pasted image 20250619221233.png]]

==REMEMBER==
	TCP is a connection-oriented transport layer protocol. UDP is a connectionless transport layer protocol
#### Session layer
It establishes conversations/ sessions between networked devices
A session is an exchange of connection-oriented transmissions between two network device
Each transmission is handled by the transport layer protocol
The session itself is managed by the session layer protocol
The session layer allows three types of transmission modes :
- Simplex : Data flows in only one direction
- Half-Duplex : data flows in both directions but only in one direction at a time
- Full-Duplex : data flows in both directions at the same time
#### Presentation layer
It is responsible for how data is represented to applications
The most common representation for representing character data today is called UTF-8 which uses 8-bit sets to represent characters found in wester alphabets
UTF-8 is compatible with an older standard called ASCII

#### Application layer
The highest layer of the OSI model, it deals with the techniques that application programs use to communicate with the network
it represents the programming interfaces that application programs use to request network services
Some of the better-known application layer protocols are :
- Domain Name System (DNS) : For resolving internet domain names
- File Transfer Protocol (FTP) : for files transfer
- Simple Mail Transfer Protocol (SMTP) : For email
- Server Message Block (SMB) : For file sharing in windows networks
- Network File System (NFS) : For file sharing in the Unix networks
- Telnet : For terminal emulation (emulator like bluestacks)

---
DATA TRAVELLING THROUGH SEVEN LAYERS
![[Pasted image 20250619222309.png]]
## Ethernet Protocol
Ethernet is the most popular set of protocols for the physical and data link layers
==REMEMBER==
	Network transmission speed refers to the maximum speed that can be achieved over the network under ideal conditions. In reality the actual throughput of an Ethernet network rarely reaches this max speed

Ethernet divides the data link layer into two separate layers
- The logical link control (LLC)
- Medium access control (MAC)
If MAC is about how to access the medium, LLC is about what to do with the data once you have access
![[Pasted image 20250619222737.png]]

## TCP/IP Protocol Suite
The internet engineering task force (IETF) manages the TCP/IP protocol suite
It is based on a four-layer model of networking similar to seven layer OSI model 
TCP/IP and the OSI MODEL
![[Pasted image 20250619223042.png]]
#### IP
Internet Protocol (IP) is a network layer protocol responsible for delivering packets to network devices, 
Address Resolution Protocol (ARP) handles the task of converting IP addresses to MAC addresses 
IP is routable Protocol
IP can forward a packet to another network if the host isn't on the current network 
An internet is just a series of two or more connected TCP/IP networks that can be reached by routing

#### TCP 
Transmission control protocol (TCP) if a connection-oriented transport layer protocol. 
It lets a device reliably send a packet to another device on the same network or on a different network
HTTPS send a request via TCP to a web server

#### UDP
User datagram Protocol (UDP) is a connectionless transport layer protocol 
UDP doesn't guarantee that the packet arrives at its destination
The best known application layer protocol that uses UDP is the domain name system (DNS)

---

### Another Protocols

- Network Basic Input / Output System (NetBIOS): The basic application programming interface for network services on Windows computers. It’s installed automatically when you install TCP/IP, but doesn’t show up as a separate protocol when you view the network connection properties. NetBIOS is a session layer protocol that can work with transport layer protocols, such as TCP, SPX, or NetBEUI.
- Network BIOS Extended User Interface (NetBEUI): A transport layer protocol designed for early IBM and Microsoft networks. NetBEUI is now considered obsolete.
- IPX/SPX: A protocol suite made popular in the 1980s by Novell for use with its NetWare servers. TCP/IP has become so dominant that IPX/SPX is rarely used now.
- AppleTalk: An obsolete suite of network protocols introduced by Apple in the 1980s and finally abandoned in 2009. The AppleTalk suite included a physical and data link layer protocol called Local Talk, but could also work with standard lower-level protocols, including Ethernet and token ring.
- Systems Network Architecture (SNA): An IBM networking architecture dating back to the 1970s, when mainframe computers roamed the earth and PCs had barely emerged from the primordial computer soup. SNA was designed primarily to support huge terminals such as airline reservations and banking systems, with tens of thousands of terminals attached to central host computers. Now that IBM mainframes that support TCP/IP and mainframe terminal systems have all but vanished, SNA is beginning to fade away. Still, many networks that incorporate mainframe computers have to contend with SNA.