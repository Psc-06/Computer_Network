## Connecting to the Internet
Choosing an ISP and negotiating a contract is a basic first step in setting up a WAN connection for your private network.
The following sections describe the most commonly used methods of connecting network users to the internet
#### Connecting with cable or DSL
Two most popular methods of connecting to the internet are cable and digital Subscriber line (DSL).
Cable and DSL connections are often called broadband connections
Cable Internet access works over the same cable that brings 40 billion TV channels into your home, whereas DSL is a digital phone service that works over a standard phone line. Typical cable and DSL speeds range from 50 Mbps to 1 Gbps.
Disadvantages with DSL and cable providers are :
- Cable and DSL are asymmetrical technologies, which means that their download speeds are much faster than their upload speed
- Business-class cable and DSL provide "best effort" service levels
- Cable and DSL access aren't available everywhere
#### Connecting with T1 lines
Telephone providers such as AT&T, Time Warner, and others offer Internet service over dedicated copper phone lines using a time-proven technology called T1.
The original T1 service was developed in the 1960s
T1 line carries data at a speed of 1.44 mbps
Newer version such as T3 provide faster service at a speed to 44.184 mbps but is is expensive
Service-level agreement (SLA) it is a agreement that will give you priority service if a problem occurs
==TIP==
	You may be wondering whether T1 or T3 lines are really any faster than cable or DSL connections. After all, T1 runs at 1.544 Mbps and T3 runs at 44.184 Mbps, and cable and DSL claim to run at much faster speeds, at least for downloads. But there are many differences that justify the substantial extra cost of a T1 or T3 line. In particular, a T1 or T3 line is a dedicated line — not shared by any other users. T1 and T3 are higher-quality connections, so you actually get the 1.544 or 44.184 connection speeds. In contrast, both cable and DSL connections usually run at substantially less than their advertised maximum speeds because of poor-quality connections and because the connections are often shared with other users.
### Connecting with fiber
The fastest, most reliable, best and of course most expensive form of internet connection is fiber-optic
Fiber-optic cable uses strands of glass to transmit data over light signals at very high speeds. Because the light signals traveling within the fiber cables are not subject to electromagnetic interference, fiber connections are extremely reliable  about the only thing that can interrupt a fiber connection is if someone physically cuts the wire.
==TIP==
	Phone service can be delivered via a fiber connection and bundled for one price. That can work to your advantage, because the provider will be more willing to bargain on the overall deal if the phone service is included.
### Connecting with a cellular network
The most widely used generation of cellular technology (4G) can consistently achieve speeds in the neighborhood of 10 to 12 Mbps for download, with peak speeds approaching 50 Mbps. Upload is a bit slower, usually in the 5 Mbps range.
## Choosing a Router
The provider you select for your internet connection will give you an ethernet handoff, which is simply an ethernet port that you can use to connect to your private network.
The router is the device that provides the link between your private network and the ethernet handoff that leads to the internet
### Choosing a small office router
For a small office you can probably get by with a consumer-grade router that you can purchase at a local electronics retailer such as best buy.
For example a Linksys WRT1900AC. This router has the following specifications : 
- A WAN connection that lets you connect to your ISP’s Ethernet handoff.
- A four-port 1 Gbps Ethernet switch. You can use this to connect up to four PCs, or to connect to an external switch for additional computers.
- A Wi-Fi Access Point that works with most 802.11 Wi-Fi standards, including 802.11ac.
- A USB 3.0 port that lets you connect a USB disk drive to provide storage accessible throughout your network.
- Built-in firewall capability.
A LINKSYS WRT1900AC ROUTER
![[Pasted image 20250701121150.png]]
### Choosing an enterprise router
For larger networks where greater throughput and more control is needed, you’ll want to select an enterprise-grade router. There are many brands to choose from, but most professionals select a Cisco router.
CISCO ASA 5500-X ROUTERS
![[Pasted image 20250701121311.png]]
These routers range from small tabletop units to powerful rack-mounted units that are capable of serving networks of all sizes. ASA stands for Adaptive Security Appliance; as the name suggests, these devices aren’t just routers but incorporate state-of-the-art firewall capabilities.
ASA 5500-X MODELS
![[Pasted image 20250701121435.png]]
### Choosing a cellular router
If you opt to use a cellular connection for Internet, either as your office’s primary connection or as a fail-over connection in case your primary connection goes down, you’ll need a router that can interface with a cellular modem. Cellular modems are usually USB devices, so your router will need to provide a USB external port to connect the cellular modem to.
## Securing Your Connection with a Firewall
A firewall is a security-conscious router that sits between the Internet and your network with a single-minded task, preventing them from getting to us. The firewall acts as a security guard between the Internet and your private network. All network traffic into and out of the private network must pass through the firewall, which prevents unauthorized access to the network.
==WARNING==
	Some type of firewall is an absolute must if your network has a connection to the Internet, whether that connection is broadband (cable modem or DSL), T1, fiber, cellular modem, smoke signals, carrier pigeon, or anything else. Without it, sooner or later a hacker will discover your unprotected network and tell his friends about it, and within a few hours, your network will be toast.
Setting up firewall :
- Firewall appliance : The easiest way, and usually the best choice. A firewall appliance is basically a self-contained router with built-in firewall features
  Most firewalls appliances include web-based interfaces that enable you to connect to the firewall from any computer on your network by using a browser. You can then customize the firewall setting to suit your needs
- Server Computer : Can be set up to function as a firewall computer. The server can run just about any network operating system, but most dedicated firewall system run Linux
A FIREWALL ROUTER CREATES A SECURE LINK BETWEEN A NETWORK AND THE INTERENT 
![[Pasted image 20250701122520.png]]
The term perimeter or edge is sometimes used to describe the location of a firewall on your network. In short, a firewall is like a perimeter fence that completely surrounds and protect the edge of your property and forces all visitors to enter through the front gate
==WARNING==
	In large networks, figuring out exactly where the perimeter is located can be a little difficult. If your network has two or more Internet connections, make sure that every one of those connections connects to a firewall — and not directly to the network. You can do this by providing a separate firewall for each Internet connection or by using a firewall with more than one Internet port.
==TIP==
	Some firewall routers can also enforce virus protection for your network
## Providing Redundancy for Your Internet Connection
If an internet connection goes down money is lost for every minute to solve this problem 
You'll want to provide at least two pathways to the internet 
- A primary Internet connection 
- Backup Internet connection
The backup connection is often called a fail-over connection because it comes into play only when the primary connection fails.
If you do use a backup Internet service, you’ll need to ensure that your
router can support automatic fail-over. That means you’ll need to use an enterprise-grade router such as the Cisco ASA 5500-X series
==TIP==
	If you use a backup Internet service with automatic fail-over, be sure to test it periodically. The easiest way to do that is simply to unplug the cable from the primary Internet Ethernet handoff to the router, and then see if your router has switched over to the backup connection. If you can still reach the Internet, your fail-over is working. (If you want to keep what friends you have at your company, I suggest conducting this test after hours.)
## Securing Connections to Remote Locations and Remote Users
NETWORK WITH FOUR VPN CONNECTIONS
![[Pasted image 20250701123659.png]]
The solution to all these situations is a virtual private network. A VPN works by establishing a secure tunnel between two devices that are connected to the Internet. For the private network at your main office, the gateway router will provide the VPN capability. Remote users can run VPN software on their computers to connect to the main office VPN; remote sites such as branch offices should use gateway routers that can permanently (and transparently) connect to the VPN.
## Connecting Remote Offices with an Ethernet Private Line
ISP may be able to provide you with a point-to-point fiber link between two office locations. This type of connection is called an Ethernet private line (EPL).
An EPL is effectively the same thing as a VPN, except that the Internet provider manages all the details necessary to maintain the privacy and security of the point-to-point link
The circuit presents itself to you as a standard Ethernet connection, which doesn’t require a firewall on either end. So, you plug both ends of the EPL circuit into a switch rather than a firewall.
TWO BRANCH OFFICE CONNECTED WITH EPL CIRCUITS
![[Pasted image 20250701124331.png]]
This setup shows that two remote offices connect to a home office with EPL circuits. The home office in Raleigh connects to two remote offices in Mount Pilot and Mayberry. The Raleigh and Mount Pilot offices have direct Internet connections, but users in the Mayberry office must access the Internet through the home office’s Internet connection.