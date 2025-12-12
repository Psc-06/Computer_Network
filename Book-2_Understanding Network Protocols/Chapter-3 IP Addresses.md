## Binary
To understand how IP addressing works, We need to understand how the binary numbering system works because binary is the basis of IP addressing
### Counting by Ones
Binary is a counting system that uses only two numerals : 0 and 1
In decimal system numerals are : 0-9
The positions in a binary number are called bits
And this positions represent power of two rather than power of 10
For example if a decimal value of binary is 10111
It will be calculated as
$1 × 2^0 = 1 × 1 = 1$
$1 × 2^1 = 1 × 2 = 2$
$1 × 2^2 = 1 × 4 = 4$
$0 × 2^3 = 0 × 8 = 0$
$1 × 2^4 = 1 × 16 = 16$
$Total = 1 + 2 + 4 + 0 + 16 = 23$

Characteristics of binary and how the system is similar to and differs from the decimal system are:
- In decimal the number of decimal places allotted for a number determines how large the number can be. If you allot six digits, for ex the larges number possible is 999999 because 0 is itself a number however a six digit number can have any of 1 mil different values.
	Similarly the number of bits allotted for a binary number determines how large that number can be. If you allot eight bits, the largest value that number can store is 11111111, which happens to be 255 in decimal (general formula is 2 ^ (Bits))
==TIP==
	To quickly figure how many different values you can store in a binary number of a given length use the number of bits as an exponent of 2 
	The "powers of two" thing is why computer don't use nice, even, round numbers in measuring such values as memory or disk space. A value of 1K, for example is not an even 1,000 bytes: It's actually 1024 bytes because 1024 is 2^10  Similarly, 1MB is not an even 1,000,000 bytes but instead 1,048,576 bytes which happens to be 2^20

POWERS OF TWO
![[Pasted image 20250620191357.png]]

### LOGICAL OPERATORS
Three of the operators are 
- AND
- OR
- XOR
compare two binary digits (bits).The fourth (NOT) works on single bit
The following list summarizes the basic logical operations
- AND: Compares two binary values. If both values are 1, the result of the AND operation is 1. If one or both of the values are 0, the result is 0.
- OR: Compares two binary values. If at least one value is 1, the result of the OR operation is 1. If both values are 0, the result is 0.
- XOR: Compares two binary values. If one of them is 1, the result is 1 If both values are 0 or if both values are 1, the result is 0.
- NOT: Doesn't compare two values but simply changes the value of a single binary value. If the original value is 1, NOT returns 0. If the original value is 0, NOT returns 1.
LOGICAL OPERATIONS FOR BINARY VALUES
![[Pasted image 20250620191704.png]]
To calculate the decimal values using AND through this 
![[Pasted image 20250620191800.png]]
### Working with binary in windows calculator
The programmer mode in windows calculator looks like this
![[Pasted image 20250620192524.png]]
Things to note about the programmer mode of the calculator are:
- Although you can convert decimal values to binary values with the programmer calculator the calculator can't handle the dotted decimal IP address format. To convert a dotted-decimal address to binary, just convert each octet separately. For example to convert 172.65.48.120 to binary, first convert 172 then 65 then 48 and then 120 to binary
- The programmer calculator has several features that are designed specifically for binary operations, such as AND OR XOR and so on.

## IP Addresses
An IP address is a number that uniquely identifies every host on an IP network. 
IP addresses operate at the network layer of the TCP/IP protocol Stack, so they are independent of lower-level data link layer MAC addresses, such as Ethernet MAC addresses
IP addresses are 32-bit binary numbers
TCP/IP places certain restrictions on how IP addresses are allocated
128-bit IP addresses has been adopted, though it still is not yet in widespread use
### Network & Hosts
IP Stands for Internet Protocol , & its primary purpose is to enable communications between networks, a 32-bit IP addresses actually consists of two parts:
- The network ID (or network address) :Its role is to assign a particular network segment. All devices are on the same network segment will share the same network ID
	-The First 3 octets in IP address is network id
	-The Network ID is like the name of the street or the general area where your computer (or any device) is located on a network.
- The host ID (or host address) : Its role is to uniquely identify a specific device within the network identified by the network ID
	-The Host ID is like the unique house number for your specific computer or device on that particular network.
	The last octet in IP address is HOST ID

==TECHNICAL STUFF==
	As i describe the details of how host IDs are assigned, you may notice that two host addresses seem to be unaccounted for. For example, the class C addressing scheme, which uses eight bits for the host ID allows only 254 hosts not the 256 hosts you'd expect. The host id can't be 0 (the host ID is all zeros) because that address is always reserved to represent the network itself. And the host ID can't be 255 (the host ID is all ones) because that host ID is reserved for use as a broadcast request that's intended for all hosts on the network 
	When the host ID portion of an IP address consists of all binary zeros, this address is reserved to identify the network itself, not a specific device on that network  
	When the host ID portion of an IP address consists of all binary ones this address is reserved for a broadcast address
### Dotted-decimal dance
IP addresses are usually represented in a format known as dotted decimal notation.
Each group of eight bits an octet is represented by its decimal equivalent
For Example
![[Pasted image 20250620204109.png]]
TO convert this value to dotted-decimal notation, first divide it into four octets as follows : 
![[Pasted image 20250620204139.png]]
Then convert each of the octets to its decimal equivalent
![[Pasted image 20250620204156.png]]
Then use periods to separate the four decimal number, like this
![[Pasted image 20250620204219.png]]
This is the format in which you'll usually see IP addresses represented

Four octets of an IP address are often referred to as w, x, y and z
OCTETS AND DOTTED-DECIMAL NOTATION
![[Pasted image 20250620204307.png]]

**BINARY TO DECIMAL CONVERSION TABLE**

| Decimal | Binary (4-bit) | Calculation          |
| ------- | -------------- | -------------------- |
| 0       | 0000           | $0×8+0×4+0×2+0×1=0$  |
| 1       | 0001           | $0×8+0×4+0×2+1×1=1$  |
| 2       | 0010           | $0×8+0×4+1×2+0×1=2$  |
| 3       | 0011           | $0×8+0×4+1×2+1×1=3$  |
| 4       | 0100           | $0×8+1×4+0×2+0×1=4$  |
| 5       | 0101           | $0×8+1×4+0×2+1×1=5$  |
| 6       | 0110           | $0×8+1×4+1×2+0×1=6$  |
| 7       | 0111           | $0×8+1×4+1×2+1×1=7$  |
| 8       | 1000           | $1×8+0×4+0×2+0×1=8$  |
| 9       | 1001           | $1×8+0×4+0×2+1×1=9$  |
| 10      | 1010           | $1×8+0×4+1×2+0×1=10$ |
| 11      | 1011           | $1×8+0×4+1×2+1×1=11$ |
| 12      | 1100           | $1×8+1×4+0×2+0×1=12$ |
| 13      | 1101           | $1×8+1×4+0×2+1×1=13$ |
| 14      | 1110           | $1×8+1×4+1×2+0×1=14$ |
| 15      | 1111           | $1×8+1×4+1×2+1×1=15$ |
## Classifying IP Addresses
IPv4v is limited to 32-bit address space
IPv6 is also called IP next generation or IPng
IPv6 uses 128 bits for internet addresses 
The number of unique internet addresses provided by IPv6
$340,282,366,920,938,463,463,374,607,431,768,211,456$

The IP Protocol defines five different address class : A, B , C D & E.
 Each of the first three classes, A-C uses a different size for the network ID and host ID portion of the address.
 Class D is for a special type of address called a multicast address
 Class e is an experimental address class that isn't used
The first four bits of the IP address are used to determine into which class a particular address fits as follows: 
- Class A: The first bit is zero
- Class B : The first bit is one and second bit is zero
- Class C : the first two bits are both one and third bit is zero
- Class D : The first three bits are all one , and the fourth bit is zero
- Class E : The first four bits are all one
IP address classes
![[Pasted image 20250620210321.png]]

#### Class A addresses
It is designed for very large networks
The first octet of the address is the network Id and the remaining three octets are the host ID
Only eight bits are allocated to the network ID and the first of these bits is to indicate that the address is a class A address
Only 126 class A networks can exist in the entire network
Class A network can accommodate more than 16 mil hosts
only 40 class A addresses are assigned to companies and organization rests are reserved for the use by the internet assigned number authority (IANA) or are assigned to organization that manage IP assignments for geographic regions

127.x.y.z this special range of addresses is reserved for loop-back testing, so these addresses aren't assigned to public networks

==TIP==
	The Special address 127.0.0.1 is called the loop-back address. A device at any IP address that sends a message to 127.0.0.1 is sending a message to itself. This may sound useless, but it actually plays an important role in troubleshooting network problems
#### Class B addresses
In this address the first two octets of the IP address are used as the network ID and the second octets are used as the host ID
16384 class B network can exist
Each class can accommodate more than 65000 hosts
The problem with Class B networks is that even though they are much smaller than Class A networks, they still allocate far too many host IDs. Very few networks have tens of thousands of hosts. Thus, careless assignment of Class B addresses can lead to a large percentage of the available host addresses being wasted on organizations that don't need them.

#### Class C addresses
In this address the first three octets are used for the network ID and the fourth octet is used for the host ID
Each class C network can accommodate only 254 hosts
With 24 network ID bits, class C addresses allow more than 2 mil networks
The problem is that they are too small

==DIFFERENCE BETWEEN CLASS A , B & C ARE : ==
![[Pasted image 20250620214654.png]]

## Subnetting
It is a technique that lets network administrators use the 32 bits available in an IP address more efficiently by creating networks that aren't limited to the scales provided by class A, B and C IP address.
With subnetting, you can create networks with more realistic host limits
it provides a more flexible way to designate which portion of an IP address represents the network ID and which portion represents the host ID
Standard IP address class only three possible network ID size exists:
- 8bits for class A
- 16bits for class B
- 24bits for class C
It allows to allocate the limited IP address space more efficiently. If the internet were limited to class A, B or C addresses every network would be allocated 254, 64K or 16mil IP addresses for host devices. Although many networks with more than 254 devices exist, few exist with 64K let alone 16mil unfortunately any network with more than 254 devices would need a class B allocation and probably waste tens of thousands of IP Addresses
If a single organization has thousands of network devices, operating all those devices with the same network ID would slow the network to a crawl.
The way TCP/IP works dictates that all the computers with the same network ID must be on the same physical network. The physical network comprises a single broadcast domain, which means that a single network medium must carry all the traffic for the network.

We will understood with the **example**: 
Imagine a company that needs, say, 500 houses for its employees.
- A Class C (254 houses) is too small. They can't fit everyone.
- A Class B neighborhood (65,000 houses) is way too big. If we give them a Class B, they'll use 500 spots and leave over 64,500 spots empty. This is a huge waste of valuable land (IP addresses). 
So, the problem was that there was a big gap between the small Class C networks and the very large Class B networks. There was no "just right" size for medium sized organizations. This meant we were either running out of space (if we only had Class C) or wasting a lot of space (if we had to give out Class B networks).
Subnetting was the solution:
Subnetting is like being able to chop up those big Class B neighborhoods into smaller, custom-sized pieces.
### Subnets
it is a network that falls within a class A, B or C network
They are created to extend the network ID
It can have network IDs of any length
Lets take an example 
![[Pasted image 20250620214333.png]]
the network has been assigned the class B address 144.28.0.0
all the devices on this network must share the same broadcast domain
In the second network the first four bits of the host ID are used to divide the network into two small networks. 
these two networks still appear to be a single network identified as 144.28.0.0. For example, the outside world considers the device at 144.28.16.22 to belong to the 144.28.0.0 network. As a result, a packet sent to this device will be delivered to the router at 144.28.0.0. The router then considers the subnet portion of the host ID to decide whether to route the packet to subnet 16 or subnet 32.

### Subnet Masks
We will understand with an example
Imagine your entire office building is  one big, open rooms and everyone is trying to talk to everyone else all the time. It would be super noisy and chaotic right?. It would be hard to have a private conversation or even find the person you're looking for
A Subnet is like putting up walls and creating smaller separate rooms within that big office building
It is simply a smaller network created with a larger network to make it more organized efficient and secure
For subnetting to work, the router must be told which portion of the host ID should be used for the subnet network ID. This little sleight of hand is accomplished by using another 32-bit number, known as a subnet mask. Those IP address bits that represent the network ID are represented by a 1 in the mask, and those bits that represent the host ID appear as a 0 in the mask. As a result, a subnet mask always has a consecutive string of ones on the left, followed by a string of zeros.
For Example
![[Pasted image 20250620214816.png]]
The first 20 bits are ones, and the remaining 12 bits are zeros .Thus the complete network ID is 20 bits in length and the actual host ID portion of the subnetted address is 12 bits in length
To determine the network ID of an IP address the router must have the IP address and the subnet mask
The router then performs a bitwise operation called a logical AND on the IP address in order to extract network ID.
For Example
![[Pasted image 20250620215057.png]]
The network Id for this subnet is 144.28.16.0
Here the subnet mask is 255.255.250.0
Don’t confuse a subnet mask with an IP address. A subnet mask doesn’t represent any device or network on the Internet. It’s just a way of indicating which portion of an IP address should be used to determine the network ID. Note that a subnet mask cannot be an arbitrary collection of octets. Instead, a subnet mask always has a certain number of binary 1s on its left side, and the remaining bits of the mask are always 0. This limits the dotted-decimal representation of a subnet mask to certain values.

==TIP==
	You can spot a subnet mask right away because the first octet is always 255, and 255 is not a valid first octet for any class of IP address
### Network Prefix Notation
A subnet mask always begins with a consecutive sequence of ones to indicate which bits to use for the network ID, you can use a shorthand notation a network prefix to indicate how many bits of an IP address represent the network ID 
It is indicated with a slash immediately after an IP address
IT is represented as 144.28.16.17/20 
This notation is also called classless interdomain routing notation (CIRN) because it provides a way of indicating which portion of an address is the network ID and which is the host ID without relying on standard address classes

### Default subnets
There are three subnet masks that corresponds to the standard class A, B and C address assignments
THE DEFAULT SUBNET MASKS
![[Pasted image 20250620215927.png]]
==TIP==
	Keep in mind that a subnet mask is not actually required to use one of these defaults because the IP address class can be determined by examining the first three bits of the IP address. If the first bit is 0, the address is Class A, and the subnet mask 255.0.0 is applied. If the first two bits are 10, the address is Class B, and 255.255.0.0 is used. If the first three bits are 110, the Class C default mask 255.255.255.0 is used.

**ADDITIONAL RESTRICTIONS THAT ARE PLACES ON SUBNETS AND SUBNET MASKS** : 
- The min number of network ID bits is eight : As a result the first octet of a subnet mask is always 255
- The max number of network ID bits is 30 :You have to leave at least two bits for the host ID portion of the address to allow for at least two hosts. If you use all 32 bits for the network ID, that leaves no bits for the host ID. Obviously, that won't work. Leaving just one bit for the host ID won’t work, either, because a host ID of all ones is reserved for a broadcast address, and all zeros refers to the network itself. Thus, if you use 31 bits for the network ID and leave only 1 for the host ID, host ID 1 would be used for the broadcast address, and host ID 0 would be the network itself, leaving no room for actual hosts. That's why the maximum network ID size is 30 bits.
- Because the network ID portion of a subnet mask is always composed of consecutive bits set to 1, only eight values are possible for each octet of a subnet mask : $0,128,192,224,248,252,254,255$
- A subnet address can't be all zeroes or all ones : This says that Network ID should at least have 2 subnet bits. With 2 bits we can get 00 11 which is forbidden the other values can be formed is 01 10 which is usable 
	-The reason why all zeros can't be because all zeroes means that it is reserved for the main network itself.
	And all ones are usually reserved for broadcast message
	-==SUBNET ADDRESS == NETWORK ID==
	==THIS THING IS FOR ONLY OLDER NETWORKS BUT IN MODERN NETWORKS ALL ONES ARE CONSIDERED AS USABLE AND ALL ZEROES ARE ALSO CONSIDERED AS USABLE  ==
### IP BLOCK PARTIES
Here Block means a group of collection
A subnet can be though of as a range or block of IP addresses that have a common network ID 
We will understand with a example 
The CIDR 192.168.1.0/28
![[Pasted image 20250621111026.png]]
This image represents a block of 14 IP address
it is a CIDR notation. Its useful to be able to determine the range of actual IP Addresses that the CIDR represents
If the network ID ends happen to be 0 you must determine how many host IDs are allowed based on the size of the network ID 
The number after the slash indicates how many of those bits starting from the left are 1s (network portion) the remaining bits are 0s(host portion)
When we convert the 28 into binary the 
Subnet mask would be 255.255.255.240
We will take another example
Let the IP address be 192.168.1.100
But the subnet mask would be the same for complex situation
now we have the IP address and subnet mask we will find the network ID
To find that
![[Pasted image 20250621112324.png]]
now we need to find the allowable hosts
So as we know that There are 8 octets so the total possible address  will be $2^8$ and as we know we always need two addresses if we take one address then it will be for the network itself so we will subtract the value of $2^8 - 2$ which will be 254

Now as we know that there are allowable hosts are 254
And the network ID bits for this subnet is 240 
So 254 - 240 is the allowable host which is 14
So the following block of IP addresses are
![[Pasted image 20250621112856.png]]
Last IP address is 192.168.1.110 this comes when we added 14 to the Network ID
#### Private and Public Addresses
To create a Private TCP/IP network, IP addresses should range from : 
![[Pasted image 20250621114140.png]]
## Pondering Ports
IP addresses is associated with a port that enables a connection to a particular server
The best-known port is port 80 which corresponds to HTTP of the world wide web
The combination of transport protocol(Example TCP) an IP address and a port called is called an internet Socket
Ports are layer 4
Layer 4 is the transport layer
Ports are represented by 32-bit numbers, so they range from 0 to 65545
There are three ranges of port numbers:
- 0 to 1023 : These are called well-known ports and they're used for the widely used services available on ports
- 1024 to 49151 : These are called registered ports and they've assigned by the Internet's governing authorities to various service provides. For example Apple's iTunes uses port 3689 and Adobe Media Server uses port 8134
- 49152 to 65535 : These are called dynamic ports, private ports or ephemeral ports. These ports cannot be registered and are used only for a specific communication
WELL KNOWN PORTS ARE : 
![[Pasted image 20250621120032.png]]

## Network Address Translation
All firewalls use a technique called network address translation (NAT).
it is used to hide the actual IP address of a computer on the local network from the outside world.
When packets cross the firewall, the NAT device translates the Private IP address to the public IP address and vice versa
NAT enables all the computer behind the firewall to communicate with the internet. 
Consider what typically happens when a user sends a request to a local
HTTP server — that is, an HTTP server that is on the same network as the user. Let’s assume that the IP address of the local HTTP server is 192.168.0.100, and the IP address of the user’s computer is 192.168.0.50. What happens is this:
1. The user’s computer sends an HTTP request in the form of an IP packet with the following address information:
- For the source, the transport protocol is TCP, the IP address is 192.168.0.50. The port number for the source is chosen by client and is typically a high port number. For this example, I’ll use port 45444 for the source port.
- For the destination, the transport protocol is TCP, the IP address is 192.168.0.100, and the port is 80.
1. The HTTP server receives the request, processes it, and sends back
an HTTP response in the form of an IP packet with the following
address information:
- For the source, the transport protocol is TCP, the IP address is 192.168.0.100, and the port is 80.
- For the destination, the transport protocol is TCP, the IP address is 192.168.0.50, and the port is 45444 (the port that was chosen by the client).
This won't work because the port of the website is public and the user is private and to send a response to 192.168.0.50 an address doesn't exist on the public internet
Let's understand public and private IP address with an example
- Outside IP address (public) : 75.68.10.201
- Inside IP address (Private) : 192.168.0.1
Let’s also assume that the HTTP server is at 99.84.206.125 (which happens to be Wiley’s web server), and a user whose private IP address is 192.168.0.50 uses a web browser to request information from the HTTP server. The HTTP request will have the following address
information:
	Source IP: 192.168.0.50
	Source port: 45444
	Destination IP: 99.84.206.125
	Destination port: 80
Here’s how it works:
1. Someone Inside Wants to Send a Letter:
    - Let's say your laptop (its internal address is $192.168.0.50$, and it's sending from a specific "return address" on the laptop, let's call it "slot 45444") wants to visit a website ($99.84.206.125$) on its usual "website viewing slot" (port 80).
    - The router sees this outgoing letter.
2. The Router Prepares the Letter for the Outside World:
    - The router realizes, "Okay, this letter is from inside, but the outside world only knows our house's main address ($75.68.10.201$)."
    - It also needs a way to remember which person inside sent this letter when the reply comes back. So, it invents a temporary "reference number" or "mailbox" for this specific outgoing letter (e.g., "mailbox 42003").
    - It writes down all the details in its "address book" (NAT table): "Laptop at $192.168.0.50$ (slot 45444) sent a letter to $99.84.206.125$ (slot 80), and I used my temporary mailbox $42003$ for it." This is its memory of the connection.
    - It then stamps the letter with the house's official address and the temporary mailbox: The "return address" on the letter now says $75.68.10.201$ (your house's public address) and "mailbox 42003." The destination remains the same ($99.84.206.125$, slot 80).
3. Sending the Letter:
    - The router sends this modified letter out to the internet. The website ($99.84.206.125$) thinks the letter came directly from $75.68.10.201$ (your house) and "mailbox 42003."
4. The Reply Letter Arrives Back:
    - A little while later, the website sends a reply letter. Its return address is $99.84.206.125$ (slot 80), and it's addressed to your house's public address $75.68.10.201$ and "mailbox 42003."
    - The router receives this reply.
5. The Router Delivers the Reply to the Right Person Inside:
    - The router looks at the incoming letter and checks its "address book" (NAT table). It sees, "Ah, a letter addressed to my $42003$ mailbox! I remember that. That was for the laptop at $192.168.0.50$ (slot 45444)."
    - It then changes the destination address on the letter back: It updates the destination to $192.168.0.50$ and the original "slot 45444" on your laptop. The source address ($`99.84.206.125`$, slot 80) stays the same.
6. Letter Delivered:
    - Finally, the router sends this correctly addressed letter to your laptop on your internal network. Your laptop receives the reply, completely unaware that the router did all this address changing in between!