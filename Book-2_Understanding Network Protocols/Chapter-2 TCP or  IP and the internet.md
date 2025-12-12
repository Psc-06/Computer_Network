The fist internet was ARPANET built by the department of defense in 1969 to link defense installation. 
ARPANET was split into two networks
- One for military use renamed as MILNET
- Original ARPANET for non military use
AI Glore claimed that he invented the internet
## TCP/IP Standards & RFCs
The TCP/IP protocol standards that define how the internet works are managed by the IETF
An internet standards is published in the request for comments(RFC )Document. 
When a document is accepted for publication, it is assigned an RFC number by the IETF. 
The various types of RFC documents are :
- Internet Standards Track
- Experimental Specification
- Information Specification
- Historic Specifications
- Best Current Practice (BCP)
MY LEVELATURITS FOR INTERNET STANDARDS TRACK RFCs
![[Pasted image 20250620111249.png]]

RFCs FOR KEY INTERNET STANDARDS
![[Pasted image 20250620111409.png]]

==TIP==
	My favorite RFC is 1149, an experimental specification for the “Transmission of IP datagrams on avian carriers.” The specification calls for IP datagrams to be written in hexadecimal on scrolls of paper and secured to “avian carriers” with duct tape. (Not surprisingly, it’s dated April 1, 1990. Similar RFCs are frequently submitted on April 1.)

## The TCP/IP Protocol Framework
It has four layers
![[Pasted image 20250620111732.png]]

#### Network Interface Layer
The lowest level of the TCP/IP architecture is the network interface layer
It corresponds to the OSI Physical and data link layers.
It is assumed to be unreliable

#### Network layer
This layer is where data is addressed, packaged and routed among networks.
Several important internet protocol operate at the network layer are
- Internet Protocol (IP) : A routable protocol that uses IP addresses to deliver packets to network devices. IP is an intentionally unreliable protocol, so it doesn't guarantee deliver of information 
- Address Resolution Protocol (ARP) : Resolves IP addresses to hardware Media access Control (MAC ) addresses , which uniquely identify hardware devices
- Internet Control Message Protocol (ICMP) ; Sends and receives diagnostic messages. ICMP is the basis of the ubiquitous ping command 
		It means that Ping command which is one of the most commonly used tools for network troubleshooting relies entirely on the internet control message protocol (ICMP) to function
- Internet Group Management Protocol (IGMP) : Used to multicast messages to multiple IP addresses at once
#### Transport Layer
It is the layer where sessions are established and data packets are exchanged between hosts.
Two Core protocols are found at this layer :
- Transmission Control Protocol (TCP) : Provides reliable connection-oriented transmission between two hosts. TCP establishes a session between hosts, and then ensured delivery of packets between the hosts
- User Datagram Protocol (UDP) : Provides connectionless, unreliable, one-to-one or one-to many delivery
#### Application layer
A few of the most popular application layer protocols are
- Hypertext transfer protocol (HTTP) : The core protocol of the World Wide Web
- File Transfer Protocol (FTP) : A protocol that enables a client to send and receive complete files from a server
- Telnet : The protocol that lets you connect to another computer on the internet in a terminal emulation mode
- Simple Mail Transfer Protocol (SMTP) : One of the several key protocols that are used to provide email services
- Domain Name System (DNS) : The Protocol that allows you to refer to other host computers by using names rather than IP addresses or numbers 

