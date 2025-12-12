## Planning Disk Capacity
10MB hard disk was invented in 1981
General rules for planning the disk capacity are 
- Plan on about 100GB of disk space for the root drives of all your servers, and allow for twice as many servers as you currently have
- If Possible, choose expandable disk subsystems, and don't load them up to capacity.
- Be wary of the desire to increase capacity at the risk of performance or reliability
- Don't be tempted by huge drive capacities
- Don't put too much faith in manufacturer claims of the benefits of tricks like compression or deduplication
- Don't neglect data retention policies and archiving strategies
## Considering Disk Drive Types
There are two basic types of storage to choose from :
### Hard Disk drives
Hard disk drives (HDD) also known as spinning drives
They are magnetic disk drives
Their disk space ranges from 500GB to 6TB or more
HDDs include mechanical components such as the motor that spins the disk platters and the servos that move the read/write heads over the spinning platters to read and write data
The performance of an HDD depends in large part on how fast the disk platters spin. 
Disk speed is measured in revolution per minute (RPM) 
Common speeds are 7.2K, 10K, & 15K
### Solid State drives
Solid state drives (SSDs) 
Their disk space ranges from 100GB to 1TB
HDD access speed is measured in milliseconds thousands of a second 
While SSD storage is measured in microseconds millionths of a second
SSD storage device are based on flash memory
![[Pasted image 20250702094832.png]]
## Drive Interfaces
The drive interface manages the connection between the disk drive itself and the control unit that the drive is attached to 
In a desktop or laptop computer, the disk controller is built into the motherboard, and it's almost always the first variety, known as SATA.
## SATA
SATA is the most popular interface for consumer devices.
The interface was originally called IDE (Integrated device electronics)
That was replaced by an improved interface called ATA (AT attachment)
Parallel interfaces were increasingly difficult to keep up with increasing disk transfer speeds, so IDE and ATA evolved into a serial interface called SATA (Serial ATA)
There are two classes of SATA disk devices
- Consumer 
- Enterprise
Consumer-class SATA disks are found in desktop and laptop computers and are the least expensive disk drives available.
Enterprise-class SATA drives are preferred for server storage because they're about ten times as reliable as consumer-class drives
### SAS
It is an evolution of an older drive interface called SCSI (Small computer system interface)
SAS is the serial version of SCSI, stands for serial attached SCSI
The SAS interface is faster than the SATA interface. 
Most SAS devices transfer data from the disk to the controller at either 6GBPS or 12 GBPs
## Considering RAID
We have ways to survive disk drive failures. 
The first line of defense is to use RAID which groups disk drives together into arrays that have built-in redundancy and automatic recovery when one of the drives in an array fails
### RAID 10
In a RAID 10 array, the disk in the array are paired into mirror sets, in which both disks in each set contain the same data.
Whenever data is written to one disk in a set, the exact same data is written to the other disk.
Thus, if either of the two disk in the set fails, the other disk in the set has a backup copy of the data
RAID 10 is generally considered the safest form of RAID, but it's vulnerable to a loss of two disk in the array.
If two disk fails at the same time, only luck will determine whether the entire array is lost.
If the failing disks are in separate mirror sets, the array will survive.
But if both disks in a single mirror set are lost, the entire array will be lost
### RAID 5
In a RAID 5 array, multiple disks are combined into a single array.
If any disk in the array fails, the contents of that disk can be recovered to a new disk by calculating the data that was on the failed disk using the data that is on the surviving disk
Working of RAID 5 array
We will understand with an example write down a list of five numbers like this 
![[Pasted image 20250702100556.png]]
Just add all the number and write down the sum.
Now if i erase any of the original five numbers you can easily figure out what it was by subtracting the surviving four numbers from the sum
RAID 5 is more efficient than RAID 10 in terms of disk capacity
But from a performance perspective, RAID 5 is considerably slower than RAID 10 when writing data to the disk.
RAID 5 is less efficient because of the calculation and because of the need for multiple writes
When one of the drives in  a RAID 5 array fails, the array will take much longer to rebuild. 
In this all the data from all the surviving drives must be read then the data for the replacement drive must be written.
The rebuild of a failed RAID 5 array often requires several days
==WARNING==
	In fact, many experts and most disk drive manufacturers recommend against RAID 5 altogether because of how long it takes to rebuild a failed drive. The problem with RAID 5 is that disk drive capacity has increased much faster than disk drive speed. We’ve been stuck at 6 Gbps or 12 Gbps for many years now, but disk capacity has soared. That means that rebuild times for RAID 5 arrays have also soared. Unfortunately, there’s a not unreasonable chance that a second drive in a RAID 5 will fail during a rebuild operation. If that happens, the entire array will be lost.
### RAID 6
RAID 6 is one step more secure than RAID 5. 
In RAID 6 two sets of redundancy information are calculated.
Two of the disk in the array are set aside for redundancy
RAID 6 imposes a greater space penalty than RAID 5
RAID 6 is a bit slower than RAID 5 because two sets of redundancy data must be calculated rather than just on e
RAID 6 is considerably safer than RAID 5
## Considering Attachment Types
Disk storage must be attached to your servers
There are four basic approaches to attaching storage to your server and that are : 
### Direct attached storage
Direct attached storage (DAS) is the simplest and most obvious way to attach storage to a server. 
With DAS, storage is directly connected to a hard disk controller within the server.
It is generally not a good idea to install large amounts of storage directly into a server body because that storage will be accessible only to the server. 
This doesn't mean that you can't use DAS for large amount of storage to be shared by several host server.
Instead you can use an external storage subsystem that has the ability to directly attach to more than one host.
These attachments are usually made with external SAS cables.
TWO HOSTS DIRECTLY ATTACHED TO A STORAGE SUBSYSTEM
![[Pasted image 20250702102118.png]]
### Storage area networks
A storage area networks (SAN) is used when the number of storage devices or the host computers make it impossible to directly connect the storage to the hosts.
Instead,  a separate network of storage devices is created using a networking technology called Fibre Channel
Fibre Channel is similar in many ways to other networking technologies such as Ethernet, but it's designed specifically for connecting huge numbers of storage devices to servers.
This network can support thousands of storage devices
They are also very fast with the top speed of 128gb
STORAGE AREA NETWORK
![[Pasted image 20250702102752.png]]
### Network-attached Storage
One final form of attaching storage in a network is called network-attached storage (NAS).
When NAS is used, storage devices are connected directly to the existing Ethernet network and data is accessed over TCP/IP using a variety of protocols that enable normal disk and file handling operations to be encapsulated in IP packets.
NAS is one of the easiest ways to add large amounts of storage to a network, but NAS doesn't have nearly the performance that SAN or DAS does.
In effect data access via NAS devices is limited to the speed of the underlying network which is typically 1 Gbps
NAS SYSTEM CONNECTED TO A NETWORK 
![[Pasted image 20250702103138.png]]
==TIP==
	When you incorporate NAS into your overall storage plan, be sure to account for the backup and recovery requirements of the NAS. It’s temptingly easy to add inexpensive terabytes of NAS storage to your network to satisfy your users’ increasing appetite for storage. But don’t forget that if the data is important enough to save on the network, it’s important enough to back up on a regular basis. Your users will be sorely disappointed if they lose data they thought was safely ensconced on NAS if you fail to incorporate it into your backup plans.
==WARNING==
	Another issue to be concerned about with NAS is that it can just randomly appear on your network when a user decides to stop at Best Buy on the way to work one day. Inexpensive, consumer quality NAS is readily available and can easily be plugged in to any available network port. Keep on the lookout for rogue NAS devices.
