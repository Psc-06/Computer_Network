==TIP==
	Mastering a virtualization environment calls for a book of its own. I recommend two titles, both from John Wiley & Sons, Inc.: Virtualization For Dummies, by Bernard Golden, and VMware Infrastructure 3 For Dummies, by William Lowe (no relation, honest).
## Understanding Virtualization
The basic idea behind virtualization is to use software to simulate the existence of hardware.
This Powerful idea enables you to run more than one independent computer system on a single physical computer system.
Each of simulated computers is called a virtual machine (VM)
For all intents and purposes, each VM appears to be a complete, self-contained computer system with its own processor (or, more likely, processors), memory, disk drives, CD-ROM/DVD drives, keyboard, mouse, monitor, network interfaces, USB ports, and so on.
Few terms in virtualization world are :
- Host : The actual physical computer on which one or virtual machines run
- Bare metal : Another term for the host computer that runs one or more virtual machines
- Guest : Another term for a virtual machine running on host
- Guest operating system : An operating system that runs within a virtual machine
==WARNING==
	As far as licensing in concerned, Microsoft treats each virtual machine as a separate computer. Thus, if you run six guests on single host, and each guest runs windows server, you need licenses to run six server.
- Hypervisor : The virtualization operating system that creates and run virtual machines for example (VM ware)
- Hardware Abstraction Layer (HAL) : A layer of software that acts as a go-between to separate actual hardware from the software that interacts with it. An operating system provides a hardware abstraction layer, because it uses device drivers to communicate with actual hardware devices so that software running in the operating system doesn’t have to know the details of the specific device it’s interacting with. A hypervisor also provides a hardware abstraction layer that enables the guest operating systems in virtual machines to interact with virtualized hardware.
## Understanding Hypervisors
At the core of virtualization is a hypervisor, a layer of software that manages the creation and execution of virtual machines
A hypervisors provides several core functions : 
- It provides a HAL, which virtualizes all the hardware resources of the host computer on which it runs. This includes processor cores, RAM, and I/O devices such as disk drives, keyboards, mice, monitors, USB devices, and so on.
- It creates pools of these abstracted hardware resources that can be allocated to virtual machines.
- It creates virtual machines, which are complete implementations of an idealized computer system that has the hardware resources of the host available to it. The hardware for each virtual machine is drawn from the pools of available hardware resources managed by the hypervisor. 
- It manages the execution of its virtual machines, allocating host hardware resources as needed to each virtual machine and starting and stopping virtual machines when requested by users.
- It ensures that each virtual machine is completely isolated from all other virtual machines, so that if a problem develops in one virtual machine, none of the other virtual machines is affected.
- It manages communication among the virtual machines over virtual networks, enabling the virtual machines to connect with each other and with a physical network that reaches beyond the host.
Two basic types of hypervisors are :
- Type-1 : A type-1 hypervisors runs directly on the host computer with no intervening operating system. This is the most efficient type of hypervisor because it has direct access to the hardware resources of the host system.
  The two best-known examples are VMware's ESXi and Microsoft's Hyper-V .
- Type-2 : A type-2 hypervisor runs as an application within an operating system that runs directly on the host computer. Type-2 hypervisors are less efficient than type-1 hypervisors because when you use a type-2 hypervisor, you add an additional layer of hardware abstraction, the first provided by the operating system that runs natively on the host, and the second by the hypervisor that runs as an application on the host operating system
	For example Oracle VM virtual box
==TIP==
	For production use, you should always use type-1 hypervisors because they’re much more efficient than type-2 hypervisors. Type- 1 hypervisors are considerably more expensive than type-2 hypervisors, however. As a result, many people use inexpensive or free type-2 hypervisors to experiment with virtualization before making a commitment to purchase an expensive type-1 hypervisor
## Understanding Virtual Disks
Creating Virtual computers leads to virtual disk storage.
Disk virtualization lets you combine a variety of physical disk storage devices and presenting them as one large disk and then parcel out to your virtual machine as needed
Virtualization disk also has some layers in it
**Lowest lever is the actual physical disk drives**
Physical disk drives are usually bundled together in arrays of individual drives. This bundling is a type of virtualization in that it creates the image of a single large disk drive that isn't really there. For example, four 2TB disk drives might be combined in an array to create a single 8TB disk drive
==NOTE==
	Disk array are usually used to provide data protection through redundancy. This is commonly called RAID, which stands for Redundant Array of Inexpensive Disk 
One common form of RAID called RAID-10 lets you create mirrored pairs of disk drives so that data is always written to both of the drives in a mirror pair. 
The usable capacity of the complete array is equal to one-half of the total capacity of the drives in the array. 
For example , a RAID-10 array consisting of four 2TB drives contain two pairs of mirrored 2TB disk drives, for a total usable capacity of 4 TB
Another common form of RAID is RAID-5 in which disk drives are combine and one of the drives in the group is used for redundancy.
The total capacity of a RAID-5 Array is equal to the sum of the capacities of the individual drives, minus one of the drives 
For example, an array of four 2TB drives in a RAID-5 configuration has total usable capacity of 6TB (here one of the drives is 2 TB)

The host computers can be connected to disk storage in several distinct ways : 
- Local disk storage : In local disk storage, disk drives are mounted directly into the host computer and are connected to the host computer via its internal disk drive controllers
  The main drawbacks of local disk storage are that it's limited to physical capacity of the host computers and is available only to the host computer that it's installed in
- Storage Area network (SAN) : In a SAN, disk drives are contained in a separate device that is connected to the host via a high-speed controller. The difference between a SAN and local storage is that the SAN is a separate device. Its high-speed connection to the host is often just as fast as the internal connection of local disk storage, but the SAN includes a separate storage controller that is responsible for managing the disk drives.
  A typical SAN can hold a dozen or more disk drives and can allow high-speed connections to more than one host. A SAN can often be expanded by adding one or more expansion chassis, which can contain a dozen or more disk drives each. Thus, a single SAN can manage hundreds of terabytes of disk data.
- Network Accessible Storage (NAS) : This type of storage is similar to SAN, but instead of connecting to the hosts via a high-speed controller, a NAS connects to the host computer via standard ethernet connections and TCP/IP. NAS is the least expensive of all forms of disk storage, but it's also the slowest
The hypervisor consolidates it storage and creates virtual pools of disk storage typically called data stores.
For example a hypervisor that has access to three 2 TB RAID-5 disk arrays might consolidate them to create a single 6TB data store
virtual disk drives that can be allocated to a particular virtual machine. Then, when an operating system is installed in a virtual machine, the operating system can mount the virtual machine’s volumes to create drives that the operating system can access.
There are four layers of virtualization and that are :
- Physical disk drives are aggregated using RAID-10 to create a unified disk image that has built-in redundancy. RAID-10 is, in effect, the first layer of virtualization. This layer is managed entirely by the SAN.
- The storage available on the SAN is abstracted by the hypervisor to create data stores. This is, effectively, a second level of virtualization.
- Portions of a data store are used to create volumes that are then presented to virtual machines. Volumes represent a third layer of virtualization.
- The guest operating system sees the volumes as if they’re physical devices, which can be mounted and then formatted to create usable disk storage accessible to the user. This is the fourth layer of virtualization.
## Understanding Network Virtualization
The virtual network connects the virtual machines to each other and to the physical network
To create a virtual network, you must create a virtual switch, which connects the virtual machines to each other and to a physical network via the host computer's network interfaces
Virtual switch also has ports
## Benefits of Virtualization
Basic efficiency benefit, virtualization has several compelling benefits and that benefits are : 
- Hardware cost
- Energy cost
- Reduces Downtime
- Recoverability
- Disaster recovery
## Choosing Virtualization Hosts
Tips to get started with the virtualization hosts are :
- If possible, purchase at least two hosts, and make sure that each host is independently capable of running all your virtual server
- Add up the amount of memory you intend to allocate for each server to determine the amount of RAM for each host
- Do a similar calculation for processor cores
- Get the best network connection you can afford
- Provide redundancy in the host's subcomponents
## Understanding Windows Server 2019 Licensing
Windows server 2019 comes in three edition. These editions are as follows
- Standard Edition : Ideal for customers who aren't virtualized or who are virtualized but have a relatively small number of server instances. Each physical server must have a minimum of eight core licenses
- Datacenter Edition ; This edition is used for larger organization with more than a few dozen server instances. It lets you run an unlimited number of server instances
- Essentials Edition : Designed for small businesses setting up their first server. It's limited to just 25 users. 
==TIP==
	And the break-even point doesn't depend on the number of cores per physical server , It's still between 12 and 13 server instances per physical server. The bottom line is that if you anticipate running more than a dozen server instances per physical server, you show consider Datacenter Edition
