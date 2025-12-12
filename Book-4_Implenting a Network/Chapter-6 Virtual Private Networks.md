## Understanding VPN
A Virtual Private network (VPN) is a type of network connection that creates the illusion that you're directly connected to a network when in fact, you're not. 
For example, suppose you set up a LAN at your office, but you also occasionally work from home. But how will you access the files on your work computer form home ? 
- You could simply copy whatever files you need from your work computer onto a flash drive and take them home with you, work on the files, copy the updated files back to the flash drive and take them back to work with you the next day
- You could email the files to your personal email account, work on them at home, and then email the changed files back to your work email account
- You could get a laptop and use the windows offline feature to automatically synchronize files from your work network with files on the laptop
Or, you could set up a VPN that allows you to log on to your work network from home. The VPN uses a secured Internet connection to connect you directly to your work network, so you can access your network files as if you had a really long Ethernet cable that ran from your home computer all the way to the office and plugged directly into the work network.
There are at least three situations in which a VPN is the ideal solution:
- One or more workers need to occasionally work from home (as in the scenario just described). In this situation, a VPN connection establishes a connection between the home computer and the office network.
- Mobile users  who may not ever actually show up at the office  need to connect to the work network from mobile computers, often from locations like hotel rooms, clients’ offices, airports, or coffee shops. This type of VPN configuration is similar to the home user’s configuration, except that the exact location of the remote user’s computer is not fixed.
- Your company has offices in two or more locations, each with its own LAN, and you want to connect the locations so that users on either network can access each other’s network resources. In this situation, the VPN doesn’t connect a single user with a remote network instead, it connects two remote networks to each other.
![[Pasted image 20250704104028.png]]
## Looking at VPN security 
The data that travels through the tunnel from one end to the other is secure as long as it is within the tunnel that is within the protection provided by the VPN
The private T1 line provided excellent security because it physically connected the two offices and could be accessed only from the two endpoints
VPN provides the same point-to-point connection as a private leased line, but does it over the internet instead of through expensive dedicated lines.
The most important of the VPN security protocols is Internet Protocol Security (IPSec), Which is a collection of standards for encrypting and authenticating packets that travel on the internet
In other words we can say that 
It provides a way to encrypt the contents of a data packet so that only a person who knows the secret encryption keys can decode the data
And it provides a way to reliably identify the source of a packet so that the parties at either end of the VPN tunnel can trust the packets are authentic
==TECHNICAL STUFF==
	Referring to the OSI reference Model. What that means is that the IPSec protocol has no idea what kind of data is being carried by the packets it encrypts and authenticates. The IPSec protocol concerns itself only with the details of encrypting the contents of the packets (sometimes called the payload) and ensuring the identity of the sender
Another commonly used VPN protocol is layer 2 tunneling protocol (L2TP). This protocol doesn't provide data encryption. 
Instead it designed to create end-to-end connections tunnel through which data can travel
L2TP is actually a combination of two older protocols : 
- Layer 2 forwarding protocol (L2FP, from cisco)
- Point-to-Point tunneling protocol (PPT, from Microsoft)
Many VPNs today use the combination of L2TP and IPSec : L2TP over IPSec. 
This type of VPN combines the best features of L2TP and IPSec to provide a high degree of security and reliability
## Understanding VPN servers and clients
The main difference between the server and the client is that the client initiates the connection with the server
& 
VPN client can establish a connection with one server at a time
However a server can accept connections from many clients
The VPN server is a separate hardware device, most often a security appliance such as Cisco ASA security appliance
AN IPSEC CONFIGURATION PAGE ON A CISCO ASA SECURITY APPLICANCE 
![[Pasted image 20250704105153.png]]
The most important item of information on this screen is the Pre-Shared key, which is used to encrypt the data sent over the VPN.
The client will need to provide the identical key in order to participate in the VPN
==REMEMBER==
	A VPN client is usually software that runs on a client computer that wants to connect to the remote network. The VPN client software must be configured with the IP address of the VPN server as well as authentication information such as a username and the Pre-share key that will be used to encrypt the data. If the key used by the client doesn't match they key used by the server, the VPN server will reject the connection request form the client
A VPN SOFTWARE CLIENT
![[Pasted image 20250704105430.png]]
A VPN client can also be a hardware device, like another security appliance. This is most common when the VPN is used to connect two networks at separate locations.
For example, suppose your company has an office in Pixley and a second office in Hooterville. Each office has its own network with servers and client computers. The easiest way to connect these offices with a VPN would be to put an identical security appliance at each location. Then, you could configure the security appliances to communicate with each other over a VPN.