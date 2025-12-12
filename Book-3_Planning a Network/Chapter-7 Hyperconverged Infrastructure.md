One of the newest trends in IT architecture is called hyperconverged infrastructure (HCI)
HCI is an attempt to solve some of the most difficult problems in IT infrastructure, including the complexity of managing explosive growth in capacity and performance requirements.
## Considering the Headaches of Traditional IT Architecture
Some basic issues that HCI addresses are : 
- Storage is difficult to manage
- The SAN is itself a network that needs to be managed
- SAN has limited expansions
-  Performance is difficult to manage
- Storage outgrows backup capacity
- Deduplication is often more trouble than it's worth
Undoing the deduplication is called hydration
## Hyperconverged Infrastructure
There are three major components of a typical SAN installation 
- Server
- Storage 
- Storage Network
Into a single component called an HCI Node
TRADITIONAL STORAGE WITH SEPARATE COMPUTER, STORAGE AND A STORAGE NETWORK
![[Pasted image 20250702183526.png]]
The equipment's that can be replaced by HCI are
- The host servers have been replaced by HCI nodes, which are HCI appliances that are typically based on the same hardware platform as a host server but that include additional software and possibly a special hardware card to enable HCI functions
- The separate storage devices are gone. Instead, each of the HCI nodes is populated with disk drives that will provide storage for the HCI environments. in other words, the computer resources of the host servers and the storage resources of the SAN have been consolidated into the HCI nodes. In most cases, the storage placed in the HCI nodes is flash storage (SSDs) to provide maximum performance
- The Fiber channel switch is gone. a separate storage area network (SAN)is not needed, so the fiber channel elements can be eliminated. Note that because there is no fiber channel network, disk performance is faster in HCI. Directly attached storage as used by the HCI is always faster than even the best tuned SAN
- The two HCI nodes are combine to create HCI cluster, which can be managed and used as if the two nodes were a single entity
![[Pasted image 20250702184252.png]]
HCI node is a server computer that is outfitted with ample disk storage, special software and possibly special hardware to consolidate storage and compute resources into a single appliance. HCI nodes can be combined into HCI clusters, which operate as a unified system
## Understanding Deduplication
One of the best feature about HCI is that it depends heavily on built-in deduplication to massively expand the capacity of the disk storage build into the nodes
Few things to note about deduplication in an HCI system:
- In HCI, deduplication isn't a feature that can be turned on or off, it's an inherent part of the system
- Depending on the make and model of the HCI node, a special deduplication accelerator card may be installed in the node to provide the computer resources needed for deduplication
- In HCI, deduplication is applied to the entire storage resource, not just to the individual virtual hard drives that are allocated on the storage.
## Understanding how Deduplication Works
There are two basic types of deduplication technology
- In-line : In-line deduplication performs its deduplication magic as data is written to the disk. In other words, when in-line deduplication is used, duplicate blocks are never written to the disk. The results in the best savings of disk space, but writing data to disk is slowed down by the deduplication process
- Post-process: In contrast, post-process deduplication performs its magic after data is written to the disk. Data is written to the disk without checking for duplication. Then, later a deduplication process scans blocks on the disk, looking for and removing duplicate blocks. This results in faster disk writes, at the cost of disk capacity
Windows server has built-in post-process deduplication that can be used for disk volumes. This feature is often enabled on file servers to increase capacity
To improve the performance of in-line deduplication, HCI solutions often use SSDs instead of hard disk drives (HDDs) and often use dedicated hardware to assist with the deduplication process
==TECHNICAL STUFF==
	Deduplication may seem like magic, but it isn't. It's just an algorithm, like everything else in computing
Overview of how it works : 
1. When a block of data is written to disk, the deduplication system creates a hash of the block by applying a hashing function to the block of data. Data blocks are typically 4K, but some HCI systems use longer 8K blocks. The hash values are typically 20 bytes long (160 bits).
2. The hash values for all blocks that are written to the disk are kept in memory in a hash table, which records not only the hash value but the disk location of the actual data block that corresponds to the hash.
3. If a hash value calculated for a block of data to be written to the disk already exists in the hash table, the deduplication software does a bit-by- bit comparison of the block to be written with the block already stored for the hash value. This is done to make sure the data blocks are actually identical. Hash functions are not perfect; although it’s very unlikely, it is possible that two different blocks of data may produce the same hash value.
4. Assuming the data blocks are, indeed, identical, the new block is not written to the disk. Instead, a link to the corresponding entry in the hash table is written to the disk. Then, when reading data blocks from the disk, if a link is encountered, the hash table is used to find the actual data block to be retrieved.
5. If the comparison in Step 3 indicates that the blocks are different, the new block is written to the disk and the hash table is updated to reflect that the hash value represents more than one actual data block value. (Links subsequently written for the hash indicate which version of the data block should be used.)
==REMEMBER==
	Because the deduplication process requires a lot of computation applying hash values, hash table lookups, comparing blocks that may be identical to ensure they really are, and so on — most HCI products use advanced hardware to mitigate the performance hit. For starters, SSD storage is usually used instead of slower HDD storage. And in many cases, a separate card in the HCI appliance is used to handle the deduplication process. This deduplication card contains its own CPU and RAM so that the task of deduplication doesn’t tax the main CPU and RAM that’s used to run the server’s virtual machines.
	![[Pasted image 20250702185813.png]]
## Considering Backup
HCI is a game-changer for backup
Its built-in deduplication abilities enable an HCI platform to integrate backups into HCI storage.
in HCI, there's really no such things as a full backup,
All backups are incremental (or differential) backups based on changed blocks within the HCI storage.
HCI backup is nearly instantaneous
==TECHINAL STUFF==
	The enormous deduplication ratios seen in HCI can trick you into thinking that you have more available storage than you really do. For example, suppose you have 10TB of data on a 20TB HCI node, with a deduplication ratio of 10:1. You may think that you’re only using 1TB of actual disk and have 19TB available. But if you have ten backup restore points, HCI includes the size of all the restore points, which may indicate that you have as much as 100TB of data on the disk. 100TB of data at a deduplication ratio of 10:1 is actually consuming 10TB of disk, so your storage is actually half-full
==WARNING==
	The one thing HCI backup does not provide is redundancy. Because data and its backup are stored on the same disk, if the disk is damaged, the data and its backup will be lost
In an HCI cluster of two nodes, those nodes are effectively mirrors of one another. So, if one node is lost, the other node can step in without losing any data. For this reason, you should always plan for at least two HCI nodes. With just one node, you can’t provide redundancy.
==WARNING==
	One other point to consider with HCI backups: Data on an HCI system — including your backup data — is always online. a good backup strategy will include three types of backups: local, off-site, and offline. The HCI backup itself meets the local backup requirement. You can place two HCI nodes in different locations to meet the offsite requirement. But HCI on its own cannot meet the offline requirement. So, even with the most advanced HCI environment, I recommend you still incorporate tape backup into your design. Tape is still the only surefire way to provide offline backups.
## Digging into HCI Clusters
You can combine HCI nodes into cluster to increase capacity.
In many HCI installations, the second node doesn't add more capacity but replicates the data stored on the first node. That way, if either of the node fails, no data is lost
HCI CLUSTERS WITH TWO AND THREE NODES
![[Pasted image 20250702191039.png]]
Some HCI providers make a special type of HCI node that focuses on data only, not on computing power. These nodes, sometimes called disaster recovery (DR) nodes, are not designed to run virtual machine workloads. Instead, they’re designed to provide secure off-site replication of your data. Because they don’t have large amounts of memory or multiple high-performance CPUs, they can be considerably less expensive than regular HCI nodes.
## Incorporating HCI Into Your Plan
One of the challenges of adopting HCI is determining what the actual capacity of your HCI storage will be.
For example, consider an HCI cluster with three 20TB nodes. The manufacturer of the nodes will probably tell you that you can expect at least 2:1 deduplication, so they’ll advertise these nodes as having a capacity of 40TB. With three nodes, you have a theoretical capacity of 120TB. But with replication built in, the actual capacity will be more like 80TB, spread out across the three nodes
Here 80TB is the Net amount of logical data you can store on the cluster, after all the system overheads (replication) and data reduction technologies (deduplication) have applied
