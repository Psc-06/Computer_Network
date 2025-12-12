## DNS Names
DNS is a name service that provides a standardized system for providing names to identify TCP/IP hosts as well as a way to look up the IP address of a host given the host's DNS name
### Domains & Domain Names
To provide a unique DNS name for every host computer on the internet , DNS uses a time-tested technique :
1. Divide
2. Conquer
Root domain is the anchor points for all domain
Root domain are four top-level domains, named edu , com, org and gov
![[Pasted image 20250625001619.png]]
Lowrriter is the personal domain
The parts of the domain name are separated from each other with periods which are called dots.
Beneath the LoweWriter node are four host nodes, named doug, debbie server1, and printer1.
These correspond to three computers and a printer on my home network
Details that you need to remember about DNS names are : 
- DNS names are not case sensitive
- The name of each DNS node can be up to 63 characters long(not including the dot) and can include letters, numbers and hyphens
- A subdomain is a domain that's beneath an existing domain
	-For ex, the com domain is actually a subdomain of the root domain. Likewise, LoweWriter is a subdomain of the com domain
 - DNS is a hierarchical naming system that's similar to the hierarchical folder system used by windows
 -==TIP==
	 However, one crucial difference exists between DNS and the Windows naming convention. When you construct a complete DNS name, you start at the bottom of the tree and work your way up to the root. Thus, Doug is the lowest node in the name doug.LoweWriter.com. In contrast, Windows paths are the opposite: They start at the root and work their way down. For example, in the path \Windows\System32\dns, dns is the lowest node.
- The DNS tree can be up to 127 levels deep
- Although the DNS tree is shallow, it's very broad
### Fully qualified domain names
If a domain name ends with a trailing dot, that trailing dot represents the root domain, and the domain name is said to be a fully qualified domain name (Also known as FQDN)
It is also called as absolute name
DNS names that don't end with a trailing dot are called relative names
They are absolute and unambiguous
For example www.google.com
DNS names that don't end with a trailing dot are called relative names
URL = Uniform Resource Locator
## Top-Level Domains
A top-level domain appears immediately beneath the root domain.
It come in two categories
1. Generic domains
2. Geographic Domains
### Generic Domains
7 Top-level organizational domains existed
THE ORIGINAL SEVEN TOP-LEVEL DOMAINS
![[Pasted image 20250625003349.png]]

### Geographic Domains
THE NEW SEVEN TOP-LEVEL DOMAINS
![[Pasted image 20250625003440.png]]
150 geographic top-level domain exist
GEOGRAPHIC TOP-LEVEL DOMAINS WITH MORE THAN 200 SUBDOMAINS
![[Pasted image 20250625003523.png]]
## The Hosts File
Host file simply listed the name and IP address of every host on the network.
Each computer had its own copy of the Hosts file
Importance of Hosts file
- The Hosts file is not dead. For small networks, a Hosts file may still be the easiest way to provide name resolution for the network’s computers. In addition, a Hosts file can coexist with DNS. The Hosts file is always checked before DNS is used, so you can even use a Hosts file to override DNS if you want.
- The Hosts file is the precursor to DNS. DNS was devised to circumvent the limitations of the Hosts file. You’ll be in a better position to appreciate the benefits of DNS when you understand how the Hosts file works.
LOCATION OF THE HOSTS FILE
![[Pasted image 20250625003815.png]]

SAMPLE HOSTS FILE
![[Pasted image 20250625004109.png]]
The Hosts file ends with comments, which show the host mapping commands used to map for the host name localhost, mapped to the IP address 127.0.0.1. The IP address 127.0.0.1 is the standard loopback address. As a result, this entry allows a computer to refer to itself by using the name localhost.
Note that after the 127.0.0.1 localhost entry, another localhost entry defines the standard IPv6 loopback address (::1). This is required because all versions of Windows since Vista provide built-in support for IPv6.
To add an entry to the hosts file simply edit the file in any text editor
For example 
To associate the host name server1.loweWriter.com with the IP address 192.168.168.201 you add this line to the host file
![[Pasted image 20250625004314.png]]
Now whenever an application requests the IP address of the host name server1.loweWriter.com the IP address 192.168.168.201 is returned
You can also add an alias to a host mapping. This enables user to access a host by using the alias as an alternative name. For example, consider the following line 
![[Pasted image 20250625004418.png]]
Here the device at the address 192.168.168.201 can be accessed as server1.loweWrite.com or just s1

A HOST FILE WITH SEVERAL HOSTS DEFINED
![[Pasted image 20250625004811.png]]

## DNS Servers & Zones
DNS server is a computer that runs DNS server software helps to maintain the DNS database and responds to DNS name resolution requests from other computer
The most popular are 
- BIND
- Windows DNS service
BIND runs on Unix-based computer (including Linux computer)
Windows DNS (naturally) runs on windows computer
For example, suppose that I set up a DNS server to handle name resolutions for my LoweWriter.com domain. Then, when someone requests the IP address of doug.LoweWriter.com, my DNS server can provide the answer. However, my DNS server wouldn't be responsible for the rest of the Internet. Instead, if someone asks my DNS server for the IP address of some other computer, such as coyote.acme.com, my DNS server will have to pass the request on to another DNS server that knows the answer.

#### Zones
Each zone is responsible to a particular DNS server
We will understand with one example
let the one zone be us.loweWrite.com is responsible for the entire us.loweWriter.com subdomain. The other zone, loweWriter.com is responsible for the entire loweWriter.com domain except for the us.loweWrite.com subdomain

The two zones allow one server to be completely responsible for the US portion of the domain and the other server handles the rest of the domain ![[Pasted image 20250625005427.png]]
Two basic types of zones are : 
- A primary zone is the master copy of a zone. The data for a primary zone is stored in the local database of the DNS server that hosts the primary zone. Only one DNS server can host a particular primary zone. Any updates to the zone must be made to the primary zone.
- A secondary zone is a read-only copy of a zone. When a server hosts a secondary zone, the server doesn’t store a local copy of the zone data. Instead, it obtains its copy of the zone from the zone’s primary server by using a process called zone transfer. Secondary servers must periodically check primary servers to see whether their secondary zone data is still current. If not, a zone transfer is initiated to update the secondary zone.
![[Pasted image 20250625005658.png]]
#### Primary & Secondary Server
- Primary server for a zone, which means that the DNS servers hosts a primary zone. the data for the zone is stored in files on the DNS server. Every zone must have one primary server
- Secondary server for a zone, which means that the DNS server obtains the data for a secondary zone from a primary server. Every zone should have at least one secondary server. That way, if the primary server goes down, the domain defined by the zone can be accessed via the secondary server or servers
==WARNING==
	A Secondary server should be on a different subnet than the zone's primary server. If the primary and secondary server are on the same subnet, both servers will be unavailable if the router that controls the subnet goes down
A server is said to be authoritative for the primary and secondary zones that it hosts because it can provide definitive answers for queries against those zones.

#### Root Servers
Core of DNS comprises the root servers, which are authoritative for the entire internet
The main function of the root servers is to provide the address of the DNS servers that are responsible for each of the top-level domains
A total of 13 root servers are located throughout the world
THE 13 ROOT SERVERS ARE :
![[Pasted image 20250625010200.png]]
THE NAMED.ROOT FILE
![[Pasted image 20250625010735.png]]
#### Caching
Name servers keep a cache of a query results. 
The next time the user visits the site the name server is able to resolve this name without having to query all those other name servers
The expiration value for DNS data is called the TTL(time to live)

## DNS Queries
When a DNS client need to resolve a DNS name to an IP address, it uses a library routine a resolver to handle the query
The resolver sends the query message over the network to the DNS server, receiving and interpreting the response and information of the results of the query
A DNS client can make two basic type of query
1. Recursive
2. Iterative
- **Recursive** **Queries** : When a client issues a recursive DNS query, the server must reply with either the IP address of the requested host name or an error message indicating that the host name doesn’t exist. If the server doesn’t have the information, it asks another DNS server for the IP address. When the first server finally gets the IP address, it sends it back to the client. If the server determines that the information doesn’t exist, it returns an error message.
- **Iterative Queries** : When a server receives an iterative query, it returns the IP address of the requested host name if it knows the address. If the server doesn’t know the address, it returns a referral, which is simply the address of a DNS server that should know. The client can then issue an iterative query to the server to which it was referred.
## Zone Files & Resource Records
Each DNS Zone is defined by a zone file (also known as a DNS database or a master file)
For windows DNS server the name of the zone file is domain.zone 
for ex : it will be named as loweWriter.com.zone
And for the BIND DNS server it will be named as db.LoweWriter.com 
Zone file consists of one or more resource records
Creating and updating the resource records that comprise the zone files is one of the primary tasks of a DNS administrator
Resource Records are written as simple text lines with the following fields : 
![[Pasted image 20250625011924.png]]
Now we will understand this line
- Owner: the name of the DNS domain or the host that the record applies to 
==TIP==
	You can also specify a single at symbol(@) as the owner name. in that case the current domain is used.
- TTL : Also known as time to live. The number of seconds that the records should be retained in a server's cache before it's invalidated. If you omit the TTL value for a resource record, a default TTL is used obtained from the start of authority (SOA) record
- Class: Defines the protocol to which the record applies. You should always specify IN, for the Internet protocol. If you omit the class field, the last class field that you specified explicitly is used. As a result, you’ll sometimes see zone files that specify IN only on the first resource record (which must be an SOA record) and then allow it to default to IN on all subsequent records.
- Type: The resource record type. The most commonly used resource types are summarized and are described separately later in this section. Like the Class field, you can also omit the Type field and allow it to default to the last specified value.
- RDATA: Resource record data that is specific to each record type.
==REMEMBER==
	Most resource records fit on one line. If a record requires more than one line, you must enclose the data that spans multiple lines in parentheses 

COMMON RESOURCE RECORD TYPES
![[Pasted image 20250625012354.png]]
==TIP==
	You can include comments to clarify the details of a zone file. A comment begins with a semicolon (;) and continues to the end of the line.

#### SOA Records
Every zone must begin with an SOA record, which names the zone and provides default information for the zone
SOA records has so may RDATA fields
RDATA FIELDS FOR AN SOA RECORD
![[Pasted image 20250625012548.png]]
Two things about the SOA fields are : 
- The email address of the person responsible for the zone is given in DNS format, not in normal email format. Thus, you separate the user from the mail domain with a dot rather than an at symbol (@). For example, doug@LoweWriter.com would be listed as doug.lowewriter.com.
- The serial number should be incremented every time you change the zone file. If you edit the file via the graphic interface provided by Windows DNS, the serial number is incremented automatically. However, if you edit the zone file via a simple text editor, you have to manually increment the serial number.
EXAMPLE OF AN SOA RECORD
![[Pasted image 20250625012822.png]]
### NS Records
Name Server (NS) records identify the name servers that are authoritative for the zone. 
Using two or more NS records is better so that if the first name server is unavailable the zone will still be accessible
TWO NS RECORDS THAT SERVER THE LOWEWRITER.COM DOMAIN
![[Pasted image 20250625013010.png]]

### A records
Address (A) records are the meat of the zone file
They provide IP addresses for each of the hosts that you want to make accessible via DNS.
The RDATA field for the A record is the IP address of the host
THE FOLLOWING LINES DEFINE VARIOUS HOSTS FOR THE LOWEWRITER.COM DOMAIN 
![[Pasted image 20250625013150.png]]\
IMPLEMENTATION OF A RECORDS 
![[Pasted image 20250625013224.png]]
This increase the chance for the error 
It creates more work for you later if you decide to change your network's domain

### CNAME records
A canonical Name (CNAME) record creates an alias for a fully qualified domain name
The DNS System substitutes the real domain name known as the canonical name for the alias
CNAME RECORD
![[Pasted image 20250625013725.png]]
Here the host name of an FTP server at 207.126.127.132 if gtp.lowewriter.com.
The CNAME record allows user to access this host as files.lowewriter.com if they prefer

### PTR Records
A pointer (PTR) record is the opposite of an address record
It provide the fully qualified domain name for a given address
the owner field should specify the reverse lookup domain name
PTR RECORDS
![[Pasted image 20250625013903.png]]
PTR records don't usually appear in normal domain zones. instead they appear in special reverse lookup zones

### MX records
Mail Exchange (MX) records identify the mail server for a domain.
The first is a priority number used to determine which mail servers to use when several are available. The second is the fully qualified domain name of the mail server itself.
MX RECORDS
![[Pasted image 20250625014038.png]]
In this example, the lowewriter.com domain has two mail servers, named mail1.lowewriter.com and mail2.lowewriter.com. The priority numbers for these servers are 0 and 10. Because it has a lower priority number, mail will be delivered to mail1.lowewriter.com first. The mail2.lowewriter.com server will be used only if mail1.lowewriter.com isn't available.
==TIP==
	The server name specified in the RDATA section should be an actual host name, not an alias created by a CNAME record. Although some mail servers can handle MX records that point to CNAMEs, not all can. As a result, you shouldn't specify an alias in an MX record.
==WARNING==
	Be sure to create a reverse lookup record (PTR, described in the next section) for your mail servers. Some mail servers won’t accept mail from a server that doesn’t have valid reverse lookup entries.
## Reverse Lookup Zones
Normal DNS queries ask a name server to provide the IP address that corresponds to a fully qualified domain name. This kind of query is a forward lookup. A reverse lookup is the opposite of a forward lookup: It returns the fully qualified domain name of a host based on its IP address.
Reverse lookups are possible because of a special domain called the in-addr.arpa domain. That provides a separate fully qualified domain name for every possible IP address on the internet
The technique used to create the reverse domain name for a given IP address is pretty clever. It creates subdomains beneath the in-addr.arpa domain by using the octets of the IP address, listing them in reverse order. For example, the reverse domain name for the IP address 207.126.67.129 is 129.67.126.207.in-addr.arpa.

## Working with the Windows DNS Server
Installing and managing a DNS server depends on the network operating system (NOS)

## Configuring a windows DNS client
1. Open the Control Panel. If you haven’t already, switch to Small Icons view.
2. Open Network and Sharing Center.
3. Click the link for your wired or wireless network adapter. The adapter’s Status dialog box appears.
4. Click Properties. The adapter’s Properties dialog box appears.
5. Select Internet Protocol Version 4 and then click Properties. The Internet Protocol Version 4 (TCP/IPv4) Properties dialog box,
 ![[Pasted image 20250625014915.png]]
 6. Configure the DNS options. To pull DNS from the DHCP server, choose Obtain DNS Server Address Automatically. To manually specify the DNS servers, choose Use the Following DNS Server Addresses, and then enter the IP addresses for your preferred and secondary DNS servers.
7. Click OK several times until all the dialog boxes you’ve opened are gone.