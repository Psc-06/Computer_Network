## Making a Network Plan
Here are some general thoughts to keep in mind while you create your network plan:
- Don't rush the plan. 
- Write down the network plan
- Ask someone else to read your network plan before you buy anything
- Keep the plan up to date
==TIP==
	The best laid schemes of mice and men gang aft agley, and leave us naught but grief and pain for promised joy.” Robert Burns lived a few hundred years before computer networks, but his famous words ring true. A network plan isn’t chiseled in stone. If you discover that something doesn’t work the way you thought it would, that’s okay. Just change your plan.
## Being Purposeful
Some common reasons for needing a network area :
- My co-worker and I exchange files using flash drives just about every day.
- I don't want to buy everyone a color laser printer when i know the one we have now just sits there taking up space most of the day
- I want everyone to be able to access the internet.
- Business is so good that one person typing in order eight hours each day can't keep up
- My brother-in-law just put in a network at his office
- I already have a network, but it's so old that it may as well be made of kite string and tin cans
==REMEMBER==
	After you identify all the reasons why you think you need a network, write them down. Don’t worry about winning the Pulitzer Prize for your stunning prose. Just make sure that you write down what you expect a network to do for you. If you were making a 500-page networking proposal, you’d place the description of why a network is needed in a tabbed section labeled Justification. In your ½-inch network binder, file the description under Purpose.
==TIP==
	As you consider the reasons why you need a network, you may conclude that you don’t need a network after all. That’s okay. You can always use the binder for your stamp collection.
## Taking Stock
One of the initial challenges of planning a network is figuring out how to work with the computers that you already have. In other words, how do you get from here to there? Before you can plan how to get “there,” you have to know where “here” is. In other words, you have to take a thorough inventory of your current computers.
#### What you need to know
You need to know the following information about each of your computer
- The processor type and, if possible, its clock speed
- The size of the hard drive and the arrangement of its partitions
- The amount of memory
- The operating system version
- What kind of printer if any is attached to the computer
- Any other devices connected to the computer
- What software is used on the computer
### Programs that gather information for you
Several software programs are available that can automatically gather the information for you. These programs inspect various aspects of a computer, such as the CPU type and speed, amount of RAM and the size of the computer's hard drives
In windows there is one program that gather information and display and the program name is system information
Start > type "System information" > Enter
![[Pasted image 20250701101441.png]]

## Considering Cable
Nowadays almost all the cabled networks are built using simple copper-based unshielded twisted pair (UTP) 
UTP cable connects the computer in a starlike arrangement, in which each computer is connected to a central point
Details about twisted pair cabling : 
- UTP cable consists of four pairs of thin wire twisted around each other; several such pairs are gathered up inside an outer insulating jacket. Ethernet uses two pairs of wires, or four wires altogether.
- UTP cable comes in various grades known as categories. Don’t use anything less than Category 5e cable for your network; Category 6 is better yet. Although lower-category cables may be less expensive, they won’t be able to support faster networks.
TWISTED PAIR CABLE
![[Pasted image 20250701103125.png]]'
==TIP==
	Be prepared for the future. Although higher-category cables are more expensive than lower-category cables, the real cost of installing Ethernet cabling is the labor required to actually pull the cables through the walls. As a result, I recommend that you invest in Category 6. (Here category 6 include cat6 cables)
- UTP cable connectors look like modular phone connectors but are a bit larger. UTP connectors are officially called RJ-45 connectors.
- UTP cable can be purchased in prefabricated lengths, but for most jobs you’ll want to purchase the cable in bulk and have a professional installer attach the connectors. Or, you can attach the connectors yourself using a simple crimping tool you can purchase for about $50.
- The maximum allowable cable length between the switch and the computer is 100 meters (about 328 feet). That should be more than enough for most circumstances, but don’t forget that the distance includes the vertical distance required for getting from the floor up to the ceiling, and back down again.
- Always leave at least 5 feet or more of extra cable neatly coiled up in the ceiling space above each location where the cable drops through the wall to floor level. That way, you’ll have some flexibility to reroute the cable later on if necessary.
## Surmising Switches
A switch contains a number of ports, each of which is receptacle that can accommodate an RJ-45 Jack connected to a UTP cable.
A SWITCH WITH FIVE COMPUTERS CONNECTED
![[Pasted image 20250701103414.png]]
The switches are generally located in the server room
Details in working with switches
- Because you must run a cable from each computer to the switch, find a central location for the switch to which you can easily route the cables.
- The switch requires electrical power, so make sure that an electrical outlet is handy.
- As a general rule, purchase twice as many switch ports as you currently need. Don’t buy an eight-port switch if you want to network eight computers because when (not if) you add the ninth computer, you’ll have to buy another switch. 
- You can connect or daisy-chain switches to one another, You connect one end of a cable to a port on one switch and the other end to a port on the other switch.
DAISY-CHAINING SWITCHES
![[Pasted image 20250701103623.png]]
==WARNING==
	Although you can daisy-chain as many switches together as you want, in actual practice you should limit the number of daisy chains in your switch configuration. Daisy-chaining can slow down a network a bit because each switch must fully receive each packet before it begins to forward the packet to the next switch. (However, some switches actually start the packet forwarding before the entire packet is received, which reduces the performance hit a bit.)
- If you need more ports than a single switch can provide, you can use stackable switches. Stackable switches have high-speed direct connections that enable two or more switches to be connected in such a way that they behave as if they were a single switch. 
  This type of connection is sometimes called a back-plane connection because the interconnect may be on the back of the switch, but that’s not always the case. If a single switch will suffice for you now, but there is a reasonable chance that you might outgrow it and need a second switch, I suggest you invest in a stackable switch so that you can expand your network later without daisy-chaining.
	![[Pasted image 20250701104044.png]]
- Another way to provide a high-speed interconnect between switches is to purchase switches that have a few high-speed SFP ports. You can then equip those ports with 10 Gb connections to route traffic between the switches. (These high-speed connections can also be used to connect switches to servers.)
- Yet another way to create high-speed interconnects between switches is to use a feature called link aggregation. If your switches provide this feature, you simply run two or more cables between the switches, using two or more ports on each switch. Then, you use the switch’s configuration software to bond the two ports together to create one link with double the port speed.
  Professional-quality network switches have network-management features that allow you to log in to the switch, usually via a web interface, to monitor and configure the switch. Such switches are called managed switches. Consumer-grade switches, also called unmanaged switches, are less expensive primarily because they do not support this feature. If you have more than a few dozen users, you’ll want to invest in managed switches.
## Planning the Network Topology
Topology refers to the way the devices in your network are connected to each other via network switches
To plan for the network Topology you need to determine what kind of switches to use, how many where to run the cable, where to locate the switches and so on
For midsized networks (say, 50 to 200 users), a common way to design the network topology is to use a two-layer switch architecture, and these two layers are :
- Core layer : The core layer contains high-performance switches that connect to the servers, the Internet gateway, and to each other. These connections should be as fast as possible - ideally 1-gbps fiber or copper connections using SFP ports
- Access Layer : The access layer consists of switches that are connected to the core layer and to the end-user computers
A TWO-TIERED SWITCH DESIGN'
![[Pasted image 20250701104528.png]]
There is one switch at the core layer and four switches at the access layer. 
For larger networks, a three-tier design can be used. In that case, a distribution layer is added between the access and the core layers
## Planning the TCP/IP Implementation
Main points your plan should address
- The subnet and VLAN structure of your network: Will everything be on a single subnet, or will you use two or more subnets to separate different types of devices?
  Although it isn’t impossible, dividing an existing network into separate subnets later on is a bit of a pain. So unless your network is very small, I suggest you plan on using subnets from the very start.
- In particular, you should consider using separate subnets for the following:
	- Wireless networks: In fact, if you create two or more wireless networks (for example, a corporate network for company-owned mobile devices, an employee network for personal smartphones, and a guest network for visitors), I suggest a separate subnet for each of the wireless networks.
	- Remote locations that will be connected via a VPN tunnel.
  In addition, if you use IP phones, definitely put the phones on their own subnet. And if your organization has more than a few dozen users, consider dividing them among two or more subnets according to their work groups. For example, you might use one subnet for the sales department and another one for the production department.
  You’ll probably need to set up VLANs to manage your subnets.
  Typically, there’s a one-to-one correspondence between subnets and VLANs; in other words, each subnet lives on its own VLAN.
==TIP==
	Don't go overboard with the subnets, however. Try to find the right balance between running the entire organization on a single subnet versus creating a lot of subnets ,each with just a few users
==TECHNICAL STUFF==
	Why bother with the subnets? The main reason is to avoid issues that will come up when your organization grows. You may have just 20 employees now, but years from now, when you have 100, and everyone starts bringing their smartphones and tablets and connecting to your Wi-Fi, you’ll find that the limit of 253 devices per subnet on a 255.255.255.0 network is simply not enough. When you run out of DHCP space and your users can’t get on the network, you’ll wish you had spread things out over a couple of subnets.
- The DHCP structure: Speaking of DHCP, what server will be responsible for DHCP? What will be the DHCP scope — that is, the range of addresses that are given out by DHCP? How will the size of your scope accommodate all the devices that will require DHCP on the subnet, with plenty of room for growth? (Again, be especially careful if you connect a wireless access point to the same subnet that your cabled network is on. You’ll be surprised how quickly you can run out of IP addresses when every one of your users brings an iPhone and an iPad. Subnets are the best answer to that problem.)
- The static IP addresses of devices whose IP should never change: These devices may include servers, printers, firewalls, and other managed devices. You’ll be surprised how quickly these can add up, as well. You’ll need static IP addresses for each of the network interfaces on your servers, for your switches, printers, copiers, fax machines, firewalls, routers, tape backup devices, and network storage devices. If you use virtualization software, the host processors will also need an IP address for each network interface. Even your UPS battery backups may want an IP address. The list goes on and on.
==TIP==
	It is absolutely imperative that you keep a good record of what static IP addresses you have assigned in your network, and that you configure your DHCP server properly so that it doesn’t step on top of static IP addresses. Every time you add a device with a static IP address, be sure to update your list. And, just as important, whenever you retire a device that uses a static IP address, update your master list to remove the IP address.
## Drawing Diagrams
The diagram can be a detailed floor plan, showing the actual location of each network component : a physical map
One of the best program for drawing diagrams is Microsoft Visio
![[Pasted image 20250701105619.png]]
