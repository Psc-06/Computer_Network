## Networking Operating Systems
The server operating system is what enables your server computers to function as server rather than as ordinary windows clients. It includes functions such as providing basic security services, sharing disk storage and printers and so on.
Some core server operating system features are : 
#### - Network Services
In addition to basic network connectivity, one of your servers will typically be responsible for providing some essential software services that are required to keep a network operating in an efficient manner. One of these is called Dynamic Host Configuration Protocol (DHCP); it’s the service that recognizes computers and other devices that want to join the network, providing each with a unique address so that all the devices on the network can identify one another.
A second basic service that is provided by one of the servers on your network is called Domain name system (DNS). This service is what enables people to use network names instead of actual address. For example www.google.com
#### - File-Sharing Services
One of the most important functions of a server operating system is to share resources with other network users.
The server operating system allows the system administrator to determine which portions of the server's file system to share
#### - Multitasking
Multitasking is the capability of an operating system to execute more than one program(a task or a process) at a time
#### - Directory Services
Networks have directories too providing information about the resources that are available on the network : users, computers, printers, shared folders, and files. Directories are essential parts of any server operating system
The most popular modern directory service is called active directory. It is kind of a database that organize information about a network and all its computers and users
Managing Active Directory users and computers
![[Pasted image 20250618231407.png]]
#### - Security Services
Most server operating system give you some standard tools for maintaining network security 
- Establish password policies
- Set passwords to expire after a certain number of days 
- Encrypt network data
- Manage digital certificates
## Importance of server
#### - Scalability
It is the ability to increase the size and capacity of the server computer without unreasonable hassle.
#### - Reliability
When a client computer fails only the person who uses that computer is affected when a server fails however everyone on the network is affected.
#### - Availability
Server computers are designed so their components can be easily diagnosed and replaced which minimizes the  downtime that results when a component fails
In some servers, components are hot swappable(certain components can be replaced without shutting down the server) . 
Some server are fault-tolerant so that they can continue to operate even if a major component fails
#### - Service and support
Don’t settle for a maintenance contract that requires you to take the computer in to a repair shop or, worse, mail it to a repair facility. You can’t afford to be without your server that long. Get a maintenance contract that provides for on-site service and repair of your server, 24 hours a day, 7 days a week.
## Components of a server computer
The following are components of a server computer
#### - Motherboard
It is the computer's main electronic circuit board to which all the other components of your computer are connected 
#### - Processor
The CPU is the brain of the computer 
Intel's Xenon processor are designed specifically for server computers rather than client computers and offer from 4 to 22 independent processor cores, depending on the model
==TECHNICAL STUFF==
	Clock speed refers to how fast the basic clock that drives the processor's operation ticks. In theory, the faster the clock speed the faster the processor. However clock speed alone is reliable only for comparing processors within the same family what matters more in a server is the number of processor cores. The more cores the server has the more tasks the server can perform simultaneously. Since servers are in the business of supporting many clients, being able to do many task simultaneously in a huge benefit for server performance 
Processor cores utilize a technology called hyperthreading which effectively lets each processor core juggle two threads at one (threads means a sequence of instruction that performs a single task). Each core can handle two simultaneous threads, a processor with four cores can handle eight concurrent threads
#### - Memory
The total memory capacity of the server depends on the motherboard
#### - Hard Drives
Many servers rely on faster and more reliable SCSI (small computer system interface) or Serial attached SCSI (SAS) disk drives.
For the best performance SSDs are the best
#### - Network interfaces
Server should have at least two network interfaces. 
Additional network interface not only improve the performance of your sever but also make it more reliable
#### - Video
Fancy graphic cards aren't that important for a server computer
#### - Power Supply
As a server usually has more devices than a typical desktop computer, it requires a larger power supply (typically 600 wats)

## Virtualization
A VM is a simulation of an actual computer system. This concept is called Virtualization
When virtualization is used a single physical server computer actually runs more than one virtual server

