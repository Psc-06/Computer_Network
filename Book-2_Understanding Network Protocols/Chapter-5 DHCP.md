DHCP automatically configures the IP address for every host on a network, thus assuring that each host has a valid unique IP Address.
## DHCP
The DHCP server keeps track of which IP addresses are already assigned so that when a computer requests an IP address, the DHCP server offers it an IP address that's not already in use
#### Configuration Information provided by DHCP
The additional information consisting DHCP options are : 
- The router address, also known as the default gateway address
- The expiration time for the configuration information
- Domain Name
- Domain Name server (DNS) server address
- Windows Internet Name Server (WINS) server address
### DHCP servers
It can be a server computer located on TCP/IP network.
Lease is a term used by DHCP to indicate that an IP address has been temporarily given out to a particular computer or other device
For smaller networks a file server can share duty as a DHCP server
==TIP==
	Most networks require only one DHCP server. Setting up two or more servers on the same network requires that you can carefully coordinate the IP address ranges (known as scopes) for which server is responsible. If you accidently set up two DHCP servers for the same scope, you may end up with duplicate address assignments if the server attempt to assign the same IP address to two different host (there will be network instability, operating system warnings etc.)
### How DHCP actually works
The Steps that how DHCP configures TCP/IP hosts are :
1. When a host computer starts up, the DHCP client software sends a special broadcast packet, known as DHCP Discover message 
	-This message uses the subnet's broadcast address (all host ID bits set to one) as the destination address and 0.0.0.0 as the source address
==TIP==
	The client has to specify 0.0.0.0 as the source address because it doesn't yet have an  IP address, and it specifies the broadcast address as the destination address because it doesn't know the address of any DHCP servers. In effect, the DHCP discover message is saying "Hey! I am new here". Are there any DHCP servers out there?
2. The DHCP server receives the broadcast DHCP discover message and responds by sending a DHCP offer message 
	-The DHCP discover message, the DHCP offer message is send to the broadcast address. This makes sense because the client to which the msg is being sent doesn't yet have an IP address and won't have one until it accepts the offer. In effect the DHCP offer msg is saying "Hello there whoever you are. Here's an IP address you can use, if you want it . Let me know"
	What if the client never receives a DHCP offer msg from a DHCP server? In that case, the client waits for a few seconds and tries again. The client will try four times - at 2,4,8 and 16 seconds. If it Still doesn't get an offer, it will try again after five min.
3. The client receives the DHCP Offer message and sends back a message known as a DHCP Request message. 
	-At this point, the client doesn’t actually own the IP address: It’s simply indicating that it’s ready to accept the IP address that was offered by the server. In effect, the DHCP Request message says, “Yes, that IP address would be good for me. Can I have it, please?”
4. When the server receives the DHCP Request message, it marks the IP address as assigned to the client and broadcasts a DHCP Ack message.
	-The DHCP Ack message says, in effect, “Okay, it’s all yours. Here’s the rest of the information you need to use it.”
5. When the client receives the DHCP Ack message, it configures its TCP/IP stack by using the address it accepted from the server.
## Understanding Scopes
A scope is simply a range of IP addresses that a DHCP server is configured to distribute.
While creating scope the properties to take in mind are : 
- A scope name, which helps you to identify the scope and its purpose
- A scope description, which lets you provide additional details about the scope and its purpose
- A starting IP address for the scope
- An ending IP address for the scope
-  A subnet mask for the scope
- One ore more ranges of excluded address
- One or more reserved addresses
- The lease duration, which indicates how long the host will be allowed to use the IP address
- The router address for the subnet also known as default gateway address
- The domain name and the IP address of the network's DNS server and WINS (Windows Internet Name Service)server
### Scopes, subnets and VLANs
DHCP relay is a routing function that forwards DHCP traffic across VLANs. 
DHCP relay is a layer 3 function, so switches that provide this feature are considered to be layer 3 switches
#### Feeling Excluded?
In the case of DHCP scopes, exclusions can help you to prevent IP address conflicts and can enable you to divide the DHCP workload for a single subnet among two or more DHCP servers
An exclusion is a range of addresses that are not included in scope
Reasons for excluding IP addresses from a scope are :
- The computer that runs the DHCP service itself must usually have a static IP address assignment. As a result the address of the DCHP server should be listen as an exclusion
	-Static IP address means that the IP address that is manually configured or permanently assigned to a device or network interface
- Some hosts, such as a server or a printer, may need to have a predictable IP address. In that case, the host will require a static IP address. By excluding its IP address from the scope, you can prevent that address from being assigned to any other host on the network
	==TIP==
	Holding back some IP address at the bottom and top of subnet is always a good idea. After all, the future is hard to predict. Even through you may not need the static IP space now, things change fast in our business. Here's typical configuration for a subnet that allows for this breathing room : 
	![[Pasted image 20250624011916.png]]
	Here the two exclusion ranges means that the scope will assign the IP address that ranges from 10.0.101.20 to 10.0.101.219
### Reservations Suggested
Disadvantages of configuring the host with a Static IP address (Feeling excluded) : 
- TCP/IP configuration supplies more than just the IP address. If you use static configuration, you must manually specify the subnet mask, the Default Gateway address, the DNS server address, and other configuration information required by the host. If this information changes, you have to change it not only at the DHCP server, but also at each host that you configured statically.
- You must remember to exclude the static IP address from the DHCP server’s scope. Otherwise, the DHCP server won’t know about the static address and may assign it to another host. Then, you’ll have two hosts with the same address on your network.
A better way to assign a fixed IP address to a particular host is to create a DHCP reservation.
A reservation simply indicated that whenever a particular host requests an IP address from the DHCP server, the server should provide it the address that you specify in the reservation.
The host won’t receive the IP address until the host requests it from the DHCP server, but whenever the host does request IP configuration, it will always receive the same address.
![[Pasted image 20250624012557.png]]
==TIP==
	To create a reservation you associate the IP address that you want assigned to the host with the host's MAC address. As a result you need to get the MAC address from the host before you create the reservation.
==REMEMBER==
	If you set up more than one DHCP server, each should be configured to serve a different range of IP Addresses. Otherwise the servers might assign the same address to two different hosts
#### How long to lease
The default lease is for eight days
Situation in which a longer or shorter interval may be appropriate are : 
- The more stable your network, the longer the lease duration can safely exist. If you only periodically add new computers to the network or replace existing computers you can safely increase the lase duration past eight days
- The more volatile the network, the shorter the lease duration should be. For ex ,  a wireless network in a university library is used by students who bring their laptop computers into the library work for a few hours at a time for them the lease duration such as one hour may be appropriate
==WARNING==
	Don’t configure your network to allow infinite duration leases. Some administrators feel that this cuts down the workload for the DHCP server on stable networks. However, no network is permanently stable. Whenever you find a DHCP server that’s configured with infinite leases, look at the active leases. I guarantee you’ll find IP leases assigned to computers that no longer exist.

## Configuring a windows DHCP client
1. Open the Control Panel..
2. Open Network and Sharing Center.
3. Click the link for your wired or wireless network adapter. The adapter’s Status dialog box shows useful information about the adapter If you just want to find out your IP address, click the Details button.
![[Pasted image 20250624014710.png]]
4. Click Properties. This brings up the adapter’s Properties dialog box
 ![[Pasted image 20250624014739.png]]
 5. Select Internet Protocol Version 4; then click Properties. The Internet Protocol Version 4 (TCP/IPv4) Properties dialog box
  ![[Pasted image 20250624014801.png]]
  6. Select Obtain an IP Address Automatically and Obtain DNS Server Address Automatically.
7. Click OK to apply the changes and dismiss the Internet Protocol Version 4 (TCP/IPv4) Properties dialog box.
8. Keep clicking OK to close all the other dialog boxes you’ve opened.\

### Automatic Private IP addressing 
if a windows computer is configured to use DHCP but the computer can't obtain an IP address from a DHCP server, the computer automatically assigns itself a private address by using a feature called automatic private IP addressing (APIPA)
To renew the lease sooner we will use the command `ipconfig /renew`
in command prompt
&
To release a DHCP leave we will use the command `ipconfig /releas`e command in command prompt
