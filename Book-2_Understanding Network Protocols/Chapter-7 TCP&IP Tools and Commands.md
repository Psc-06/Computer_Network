## ARP Command
It allows you to display and modify the address resolution protocol (ARP) cache which is simple mapping of IP addresses to MAC addresses.
To Display the ARP cache entry for a specific IP address, use an -a switch followed by the IP addresses for example
![[Pasted image 20250627003510.png]]
ARP cache without -a will look like this
![[Pasted image 20250627003535.png]]
==TIP==
	ARP is sometimes useful when diagnosing duplicate IP assignment problems. For example, suppose you can't access a computer that has an IP address of 192.168.1.100. You try to ping the computer, expecting the ping to fail, but lo and behold — the ping succeeds. One possible cause for this may be that two computers on the network have been assigned the address 192.168.1.100, and your ARP cache is pointing to the wrong one. The way to find out is to go to the 192.168.1.100 computer that you want to access, run ipconfig /all, and make a note of the physical address. Then return to the computer that's having trouble reaching the 192.168.1.100 computer, run arp -a, and compare the physical address with the one you noted. If they're different, two computers are assigned the same IP address. You can then check the Dynamic Host Configuration Protocol (DHCP) or static TCP/IP configuration of the computers involved to find out why
## Hostname Command
It displays the computer's host name 
For example
![[Pasted image 20250627003704.png]]
## IPconfig Command
Using the ipconfig command displays information about a computer's TCP/IP configuration
IT can also be used to update DHCP and Domain Name System (DNS) setting
#### Display basic IP configuration
To display the basic IP configuration for a computer, use the ipconfig command without any parameters like this
![[Pasted image 20250627003900.png]]
==TIP==
	If your computer indicates an IP address in the 169.254.x.x block, odds are good that the DHCP server isn't working. 169.254.x.x is the Class B address block that Windows uses when it resorts to IP autoconfiguration. This usually happens only when the DHCP server can’t be reached or isn’t working.
#### Display detailed configuration information
To display detailed IP configuration information by using an /all switch with the ipconfig command like this
![[Pasted image 20250627004017.png]]
Information that Ipconfig/all gives are
- The computer's host name 
- The computer's IPv4 and the subnet mask
- The default gateway router
- The DNS server
### Renewing an IP lease
To renew an IP use the command /renew switch like this 
![[Pasted image 20250627004223.png]]
When you renew an IP lease the ipconfig command displays the new lease information
==WARNING==
	This command won't work if you configured the computer to see a static IP address
	
### Releasing an IP lease
To release an IP lease by using an ipconfig command with the /release parameter like this 
![[Pasted image 20250627004855.png]]
As you can see, the DNS suffix and default gateway for the computer are
blank, and the IP address and subnet mask are set to 0.0.0.0.
After you release the DHCP lease, you can use an ipconfig /renew
command to obtain a new DHCP lease for the computer.
==WARNING==
	This command won't work if you configured the computer to see a static IP address
### Flushing the local DNS cache
If you’ve been tinkering with your network’s DNS configuration, though, you may need to flush the cache on your DNS clients so that they’ll be forced to reacquire information from the DNS server. You can do that by using a /flushdns switch:
![[Pasted image 20250627005036.png]]
==TIP==
	Even if you don’t need to do this, it’s fun just to see the computer read flushed. If I worked at Microsoft, you'd be able to revert Windows Vista computers back to XP by using a /flushVista switch.
## nbtstat Command
nbtstat is a Windows-Only Command that can help solve problems with NetBIOS name resolution
For example -a switch displays the cached name table for a specified computer like this
![[Pasted image 20250627005303.png]]
NBTSTAT COMMAND SWITCHES
![[Pasted image 20250627005320.png]]

## netstat Command
It displays a variety of statistics about a computer's active TCP/IP connections. 
It's a useful tool to use when you're having trouble with TCP/IP applications, such as FTP, HTTP and so on
#### Displaying Connections
running netstat without any switches it will look like this
![[Pasted image 20250627005448.png]]
This list shows all the active connections on the computer and indicates the local port used by the connection as well as the IP address and port number for the remote computer

-n switch display both local and foreign addresses in number IP Form
![[Pasted image 20250627010112.png]]
#### Displaying interface statistics
-e switch displays various protocol statistics like this :
![[Pasted image 20250627010229.png]]
==REMEMBER==
	The items to pay attention to in this output are the Discards and Errors. These numbers should be zero, or at least close to it. If they're not, the network may be carrying too much traffic or the connection may have a physical problem. If no physical problem exists with the connection, try segmenting the network to see whether the error and discard rates drop.
To display additional statistics by using an -s switch like this 
![[Pasted image 20250627010401.png]]
![[Pasted image 20250627010417.png]]
![[Pasted image 20250627010424.png]]
## nslookup Command
It is a powerfull tool for diagnosing DNS problems
### Looking up an IP address
The Simplest use of nslookup is to look up the ip address for a given DNS name
For example how did i know that 66.135.192.87 was the ip address for www.ebay.com?
![[Pasted image 20250627010651.png]]
This DNS query was sent to the server named ns1.orng.twtelecom.net at 168.215.210.50. It then displayed the IP address that's associated with ebay.com: namely, 66.135.192.87.
==TIP==
	In some cases, you may find that using an nslookup command gives you the wrong IP address for a host name. To know that for sure, of course, you have to know with certainty what the host IP address should be. For example, if you know that your server is 203.172.182.10 but nslookup returns a completely different IP address for your server when you query the server's host name, something is probably wrong with one of the DNS records.
### nslookup subcommands
If you use nslookup without any arguments, the nslookup command enters a subcommand mode.
It displays a prompt character (>) to let you know that you're in nslookup subcommand mode rather than at a normal windows command prompt.
(?) get a list of all the commands
MOST COMMANLY USED NSLOOKUP COMMANDS 
![[Pasted image 20250627011207.png]]
#### Displaying DNS records
One of the main uses of nslookup is to examine your DNS configuration to make sure that it's set up properly. To do that follow these steps
1. At a command prompt, type nslookup without any parameters.
	nslookup displays the name of the default name server and displays
	the > prompt.
	![[Pasted image 20250627011746.png]]
2. Type the subcommand set type=any.
	nslookup silently obeys your command and displays another prompt:
	![[Pasted image 20250627011804.png]]
3. Type your domain name.
	nslookup responds by displaying the name servers for your domain:
	![[Pasted image 20250627011820.png]]
4. Use a server command to switch to one of the domain's name servers.
	For example, to switch to the first name server listed in Step 3, type server NS000.NS0.com. nslookup replies with a message that indicates the new default server:
	![[Pasted image 20250627011904.png]]
5. Type your domain name again.
	This time, nslookup responds by displaying the DNS information for
	your domain:
	![[Pasted image 20250627011923.png]]
6. Type exit to leave the nslookup program.
	You return to a command prompt.
	![[Pasted image 20250627011946.png]]
#### Locating the mail server for an email address
Trouble in delivering mail to someone you can use nslookup to determine the IP address of the user's mail server
Then, you can use the ping command to see whether you can contact the user's mail server. If not, you can use the tracert command to find out where the communication breaks down.
To find a user's mail server, start nslookup and enter the command set
type=MX. Then, enter the domain portion of the user’s email address.
For example, if the user’s address is Doug@LoweWriter.com, enter
LoweWriter.com. nslookup will display the MX (Mail Exchange)
information for the domain, like this:
![[Pasted image 20250627012327.png]]
Here, you can see that the name of the mail server for the
LoweWriter.com domain is sasi.pair.com.
So, while you're not finding a specific email _address_, you are finding the critical infrastructure (the mail server hostname) that is responsible for handling all email sent to that domain. This is essential for email deliverability
#### Taking a ride through DNS-Land
1. At a command prompt, type nslookup without any parameters. nslookup displays the name of the default name server and displays the > prompt.  ![[Pasted image 20250627013857.png]]
2. Type root to switch to one of the Internet's root servers. nslookup switches to one of the Internet's 13 root servers and then displays the > prompt ![[Pasted image 20250627013918.png]]
3. Type www.disneyland.com. nslookup sends a query to the root server to ask whether it knows the IP address of www.disneyland.com. The root server answers with a referral, meaning that it doesn't know about www.disneyland.com, but you should try one of these servers because they know all about the com domain.
![[Pasted image 20250627013933.png]]
![[Pasted image 20250627013939.png]]
4. Type server followed by the name or IP address of one of the com domain name servers. It doesn't really matter which one you pick. nslookup switches to that server. (The server may spit out some other information besides what I show here; I left it out for clarity.)
![[Pasted image 20250627013959.png]]
5. Type www.disneyland.com again. nslookup sends a query to the com server to ask whether it knows where the Magic Kingdom is. The com server's reply indicates that it doesn’t know where www.disneyland.com is, but it does know which server is responsible for disneyland.com.
	![[Pasted image 20250627014013.png]]
==TECHNICAL STUFF==
	It figures that Disney's name server is huey.disney.com. There's probably also a dewey.disney.com and louie.disney.com
6. Type server followed by the name or IP address of the second level domain name server. 
	nslookup switches to that server:
	![[Pasted image 20250627014136.png]]
7. Type www.disneyland.com again.
	Once again, nslookup sends a query to the name server to find out
	whether it knows where the Magic Kingdom is. Of course,
	huey.disney.com does know, so it tells us the answer:
	![[Pasted image 20250627014152.png]]
8. Type Exit, and then shout like Tigger in amazement at how DNS queries work.  And be glad that your DNS resolver and primary name server do all  this querying for you automatically.
## pathping command
It is the command that combines the feature of ping command the tracert command
When you run pathping, it first traces the route to the destination address much the way tracert does.
Using an -n switch causes the display to use numeric IP numbers only instead of DNS host names that will look like this
![[Pasted image 20250627014416.png]]
![[Pasted image 20250627014422.png]]
## Ping Command
Ping is probably the most basic TCP/IP command line tool
Its purpose is to determine whether you can reach another computer from your computer.
It uses Internet Control Message Protocol (ICMP) to send mandatory ECHO_REQUEST datagrams to the specified host computer.
ping command will look like this
![[Pasted image 20250627014619.png]]
![[Pasted image 20250627014627.png]]
By default it sends 4 packets
You can also ping by using a DNS name that will look like this
![[Pasted image 20250627014748.png]]
The ping command uses a DNS query to determine the IP address for the specified host, and then pings to host based on its IP address.
To check the switches for the ping command use 
ping/? (for windows) or man ping (for Linux/Unix)
## Route command
It displays or modified the computer's routing table
### Displaying the routing table
To display routing table in windows use route print command
And for Linux use route 
Routing table will look like this
![[Pasted image 20250627015304.png]]
![[Pasted image 20250627015312.png]]
For each entry in the routing table, five items of information are listed: 
- The destination IP address
	Actually, this is the address of the destination subnet, and must be
	interpreted in the context of the subnet mask.
- The subnet mask that must be applied to the destination address to determine the destination subnet
- The IP address of the gateway to which traffic intended for the destination subnet will be sent
- The IP address of the interface through which the traffic will be sent to the destination subnet
- The metric, which indicates the number of hops required to reach destinations via the gateway
So in this example information that we get are 
Private IP address : 192.168.1.0
Computer's IP address : 192.168.1.100
Default gateway : 192.168.1.1
The rules for routing table are :
- The first rule is for packets sent to 255.255.255.255, with subnet mask 255.255.255.255. This special IP address is for broadcast packets. The rule specifies that these broadcast packets should be delivered to the local network interface (192.168.1.100).
- The next rule is for packets sent to 192.168.1.255, again with subnet mask 255.255.255.255. These are also broadcast packets and are sent to the local network interface.
- The next rule is for packets sent to 192.168.1.100, again with subnet mask 255.255.255.255. This is for packets that the computer is sending to itself via its own IP address. This rule specifies that these packets will be sent to the local loopback interface on 127.0.0.1.
- The next rule is for packets sent to 192.168.1.0, with subnet mask 255.255.255.0. These are packets intended for the local subnet. They're sent to the subnet via the local interface at 192.169.1.100.
- The next rule is for packets sent to the loopback address (127.0.0.1, subnet mask 255.0.0.0). These packets are sent straight through to the loopback interface, 127.0.0.1.
- The last rule is for everything else. All IP addresses will match the destination IP address 0.0.0.0 with subnet mask 0.0.0.0 and will be sent to the default gateway router at 192.168.1.1 via the computer's network interface at 192.168.1.100. 
==TIP==
	One major difference between the Windows version of route and the Unix/Linux version is the order in which they list the routing table. The Windows route command lists the table starting with the most general entry and works toward the most specific. The Unix/Linux version is the other way around: It starts with the most specific and works toward the more general. The Unix/Linux order makes more sense — the Windows route command displays the routing list upside down.
### Modifying the routing table
Route command also lets you modify it by adding, deleting or changing entries
==WARNING==
	Don't try this unless you know what you’re doing. If you mess
	up the routing table, your computer may not be able to
	communicate with anyone.
The syntax for the route command for adding, deleting or changing a route entry is 
![[Pasted image 20250627020126.png]]
Now here
- -p : Makes the entry persistent. If you omit -p the entry will be deleted the next time you reboot (use this only with add commands)
- command : add, delete , or change
- dest : the IP address of the destination subnet
- mask subnet: The subnet mask. If you omit the subnet mask, the default is 255.255.255.255, meaning that the entry will apply only to a single host rather than a subnet. You usually want to include the mask.
- gateway: The IP address of the gateway to which packets will be sent.
- if interface: The IP address of the interface through which packets will be sent. If your computer has only one network interface, you can omit this.
Suppose that your network has a second router that serves as a link to another private subnet, 192.168.2.0 (subnet mask 255.255.255.0). The interface on the local side of this router is at 192.168.1.200. To add a static route entry that sends packets intended for the 192.168.2.0 subnet to this router, use a command like this:
![[Pasted image 20250627020438.png]]
Now suppose there is some changes in the IP addresses the updated route for the command will be
![[Pasted image 20250627020459.png]]
Now to delete the router we will use the following command
![[Pasted image 20250627020518.png]]
## Tracert Command
The tracert command (traceroute in Unix/Linux implementations) is one of the key diagnostic tools for TCP/IP. It displays a list of all the routers that a packet must go through to get from the computer where tracert is run to any other computer on the Internet. Each one of these routers is called a hop.
If you can't connect to another computer, you can use tracert to find out exactly where the problem is occurring. tracert makes three attempts to contact the router
To use tracert, type the tracert command followed by the host name
of the computer to which you want to trace the route. For example,
suppose that you're having trouble sending mail to a recipient at
wiley.com. You've used nslookup to determine that the mail server for
wiley.com is xmail.wiley.com, so now you can use tracert to trace
the routers along the path from your computer to xmail.wiley.com:
![[Pasted image 20250627020709.png]]
For example, the following tracert output shows the fourth hop timing out on all three attempts:
![[Pasted image 20250627020745.png]]
![[Pasted image 20250627020918.png]]