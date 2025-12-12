A petabyte (PB) is a thousand of terabytes
## Backup Basics
==TIP==
	The main goal of a backup is existential: Keep a spare copy of your network’s critical data so that no matter what happens to your computer systems, your company can survive. Cybercriminals may ransom your data, your server room may burn down, or Disney may decide to bring Jar Jar Binks back. But as long as you have a good backup architecture and stay on top of it, you’ll be able to recover from these or even worse disasters. 
Conventional wisdom along with common sense says that you should always have at least three backup copies of all essential data: 
- At least one local copy, which is a part of your local network and can be accessed quickly
- At least one off-site copy, which is kept at a remote location.
- At least one off line copy, which is kept completely isolated from the internet and from your network
Another conventional-wisdom paradigm of backups is to keep three generations of backups, typically known as Grandfather, Father, and Son, or GFS. The idea is to have three different sets of backups, differentiated by age. For example, one set that was made last night, another that was made two days ago, and a third that was made three days ago. (I’d like to lobby the backup industry to switch this terminology to GPC, for Grandparent, Parent, and Child.)
You may use a differential scheme for the local, off-site and offline backups. For example, you might divide a scheme something like this
- Local backups ; 10 daily, 4 weekly and 3 monthly
- Off-site backups : 4 weekly
- Offline backup : 4 weekly and 3 monthly
## Three basic types of backups
There are two fundamentally different types of backup you can choose for your organization
- File based backup : The oldest type of backup software backs up the files on your computer one at a time. With this type of software, you can be very selective about exactly which files to back up. For example, you can choose to skip all files with the extension .bak, because these are backup files and you don't really need to back up backup files. Or, you can choose to omit specific folders or even entire disk drives from the backup. The drawback is that if a computer contains a lot of files (say, in the millions — not uncommon for a large file server), the backup program will spend an inordinate amount of time just keeping track of all the files.
- Image-based backup : This type of backup software make copies of entire disk images. The best known of these is Acronis. With an image-based backup, it doesn't matter how many files are on a disk, the backup software makes an exact copy of the entire disk, copying data block by block. This is much faster than a file-based backup not just for backing up but also for restoring data 
![[Pasted image 20250702105709.png]]
## Where to Back Up Your Data
==TIP==
	In backup Lingo, the destination for your backups is called backup target
Four most common media options are :
- Tape : Magnetic tape is the oldest storage medium for backups and is still one of the most widely used. One big advantage of tape backups is that tape cartridges are small and can thus be easily transported to an off-site location.
![[Pasted image 20250702110145.png]]
- Network-attached storage (NAS): A Network Attached Storage device connects directly to your network. NAS devices are often used as backup devices because they’re relatively inexpensive. Note, however, that the most inexpensive NAS devices have 1GB network connections, and it can take a very long time to back up terabytes of data over a 1GB connection. 10 Gbps NAS units are more expensive but will back up your data much faster.
![[Pasted image 20250702110206.png]]
The blue white are the hard disk drives
- Network-attached backup appliances: A network-attached backup appliance is similar in many ways to a NAS, but it’s specifically designed for backup. NAS devices are designed to work as file servers and can be used for backups, but a purpose-built backup appliance will give better performance and capacity for your backups.
- Cloud backup: An increasingly popular option is to use a third party service to back up data to a remote location via the Internet. Cloud backup has the advantage of already being off-site, but keep in mind that it’s online, meaning that a very skilled hacker can in theory wipe out your cloud backups.
## Backing Up to Tape
Tape backups is one of the oldest and most reliable forms of backup there is.
Computers have been using tape for data storage since 1951
The most common format for modern tape storage is the LTO cartridge
### Looking closer at LTO
![[Pasted image 20250702110732.png]]
Originally two physical cartridge formats were planned but only one knowns as Ultrium was ever manufactured
LTO stands for Linear Tape-Open which is important only in that the open means that the format is an open standard, so different vendors can make drives and tape cartridges which are compatible with one another.
LTO TAPE GENERATIONS
![[Pasted image 20250702110928.png]]
### Hardware for tape backup
You will need a tape drive to write backups to tape 
![Half-High LTO Generation 5 SAS Tape Drive Product Guide (withdrawn product)  > Lenovo Press](https://lenovopress.lenovo.com/assets/images/tips0826/0.3FE.jpg)
An LTO tape drive consists of the following internal and external components : 
- A carrier that can hold the tape while it's being written to or read from and can also eject the tape when necessary
- A read/write head that reads data from and writes data to the tape
- A motor that spins the tape reel inside the cartridge so that the tape moves across the read/write head. The motor is also responsible for rewinding the tape when all its data has been read
- A tape take-up reel. The tape cartridge itself has just one reel for the tape. Therefore, The tape drive itself includes a take-up reel for the tape that is spun off the cartridge's reel as the tape is read or written
- Optionally a bar code reader that can read a bar code printed on a label that's attached to the cartridge. This helps the tape drive verify that the correct tape is inserted
- A controller interface to connect the drive to a computer. Usually the interface is serially attached SCSI (SAS) or Fibre Channel (FC)
If you need to backup more than a single tape of data, you'll need an automated tape changer, usually called a  tape library. 

A tape library consists of the following internal components

- One or more tap magazines each of which can hold several tape cartridges
- One or more tape drives. When multiple tape drives are available each  drive can read or write tapes simultaneously. Thus, a library with two drives can write tape backups twice as fast as a stand-alone tape drive or a library with just one drive
- A robotic mechanism to automatically move tapes from the magazines to the drives and vice versa

The greatest advantage of a tape library is that it can change tapes automatically, so no manual intervention is needed when a tape fills up. But the ability to process multiple tapes simultaneously is also a big advantage, especially when many terabytes of data need to be backed up.
### Tape Reliability
I've found that although tape drives are very reliable they do run malfunctioning once in a while. 
The problem is that they don't always tell you when they're not working.
A tape drive can spin along for hours, pretending to backup you data but in reality, your data isn't being written reliably to the tape
==TIP==
	Don’t panic! Here’s a simple way to assure you that your tape drive is working. Just activate the “compare-after-backup” feature of your backup software. As soon as your backup program finishes backing up your data, it rewinds the tape, reads each backed-up file, and compares it with the original version on the hard drive. If all files compare, you know that your backups are trustworthy.
Here are some additional thoughts about the reliability of tapes :
- The compare-after backup feature doubles the time required to do a backup, but that doesn’t matter if your entire backup fits on one tape. You can just run the backup after hours. Whether the backup and repair operation takes one hour or ten doesn’t matter, as long as it’s finished by the time the network users arrive at work the next morning. 
- If your backups require more than one tape, you may not want to run the compare-after-backup feature every day. Be sure to run it periodically, however, to check that your tape drive is working. 
- If your backup program reports errors, throw away the tape, and use a new tape.
- Actually, you should ignore that last comment about waiting for your backup program to report errors. You should discard tapes before your backup program reports errors. Most experts recommend that you should use a tape only about 20 times before discarding it. If you use the same tape every day, replace it monthly. If you have tapes for each day of the week, replace them twice yearly. If you have more tapes than that, figure out a cycle that replaces tapes after about 20 uses.
### Cleaning the heads
An important aspect of backup reliability is proper maintenance of your tape drives. Every time you back up to tape, little bits and specks of the tape rub off onto the read and write heads inside the tape drive. Eventually, the heads become too dirty to read or write data reliably.
To counteract this problem, clean the tape heads regularly. The easiest way to clean them is to use a cleaning cartridge for the tape drive. The drive automatically recognizes when you insert a cleaning cartridge and then performs a routine that wipes the cleaning tape back and forth over the heads to clean them. When the cleaning routine is done, the tape is ejected. The whole process takes only about 30 seconds.
The most annoying aspect of tape drive cleaning is that the cleaning cartridges have a limited life span and unfortunately, if you insert a used-up cleaning cartridge, the drive accepts it and pretends to clean the drive.
For this reason keep track of how many times you use a cleaning cartridge and replace it as recommended by the manufacturer
## Backing Up to NAS
NAS is storage that is not attached directly to a server but is instead connected to the network.
Any other device on the network can access the storage provided by the NAS, as long as proper credentials are used.
==WARNING==
	The only caveat for using NAS as a backup target is to consider the speed of the NAS device’s network connection. Most NAS devices have a 1GB network interface that can be connected basically anyplace on your network. But data measured in terabytes is being transferred, so a 1GB connect can be painfully slow. You can count on about five hours per terabyte.
## Using a Backup Appliance
Backup Appliances are devices that are specifically designed to work as backup targets.
Most backup appliances rely on the technique of deduplication (means that it eliminates the duplicate copies of data) to dramatically reduce the storage space required to store your backup data
Deduplication is a compute-heavy operation
To accomplish this, Exagrid carves the total storage of the appliance into two regions. The first region is called the landing zone. This is where backup software writes its backup data to. The second region is called the retention zone. After data has been written to the landing zone, the Exagrid device begins the process of moving that data to the retention zone, applying its deduplication algorithm as it goes.
## File-Based Backup
The main advantage of this type of backup program is that you have a lot of flexibility over exactly what files, folders, and volumes should be backed up.
The drawback is that processing files individually significantly slows down the backup program.
File-based backup programs do more than just copy data from your hard drive to tape. Backup programs use special compression techniques to squeeze your data so that you can cram more data onto fewer tapes. Compression factors of 2:1 are common, so you can usually squeeze 100GB of data onto a tape that would hold only 50GB of data without compression. (Tape drive manufacturers tend to state the capacity of their drives by using compressed data, assuming a 2:1 compression ratio. Thus, a 200GB tape has an uncompressed capacity of 100GB.)
- Documents : If your network is used primarily for Microsoft Office applications and is filled with word and excel documents, you'll probably get better than 2:1 compression
- Graphics : if you network data consists primarily of graphic image files, you probably won't get much compression. Most graphic image file formats are already compresses so they can't be compressed much more by the backup software's compression methods.
==REMEMBER==
	If your network has more than one server, invest in good backup software. One popular choice is Barracuda Backup, made by BarracudaWare (www.barracudaware.com). Besides being able to handle multiple servers, one of the main advantages of backup software (such as Yosemite Backup) is that it can properly back up Microsoft Exchange server data.
### Types of file-based backups
You can perform five different types of backups
The Differences among the five types of backups involve a little technical detail known as the archive bit.
The archive bit indicates whether a file has been modified since it was backed up. The archive bit is a little flag that’s stored along with the filename, creation date, and other directory information. Any time a program modifies a file, the archive bit is set to the On position. That way, backup programs know that the file has been modified and needs to be backed up.
BACKUP TYPES USE THE ARCHIVE BITS
![[Pasted image 20250702123546.png]]
==TIP==
	Backup programs allow you to select any combination of drives and folders to back up. As a result, you can customize the file selection for a backup operation to suit your needs. For example, you can set up one backup plan that backs up all a server’s shared folders and drives, plus its mail server stores, but then leaves out folders that rarely change, such as the operating system folders or installed program folders. You can then back up those folders on a less-regular basis. The drives and folders that you select for a backup operation are collectively called the backup selection.
#### Normal Backups
A normal backup also called a full backup is the basic types of backup.
In a normal backup all files in the backup selection are backed up regardless of whether the archive bit has been set.
When a normal backup finishes, none of the files in the backup selection has its archive bit set
The easiest backup scheme is to simply schedule a normal backup every night.
==REMEMBER==
	Do normal backups nightly if you have the tape capacity to do them unattended — that is, without having to swap tapes. If you can’t do an unattended normal backup because the amount of data to be backed up is greater than the capacity of your tape drive(s), you have to use other types of backups in combination with normal backups.
==TIP==
	If you can’t get a normal backup on a single tape, and you can’t afford a second tape drive or a tape changer, take a hard look at the data that’s being included in the backup selection. I recently worked on a network that was difficult to back up onto a single tape. When I examined the data that was being backed up, I discovered a large amount of static data that was essentially an online archive of old projects. This data was necessary because network users needed it for research purposes, but the data was read-only. Even though the data never changed, it was being backed up to tape every night, and the backups required two tapes. After I removed this data from the cycle of nightly backups, the backups were able to squeeze onto a single tape again.
#### Copy backup
A copy backup is similar to a normal backup except that the archive bit isn't reset when each file is copies. 
You use a copy backup when you want to do an occasional one-shot backup.
in copy backup archive bits of any modified files remain unchanged
#### Daily Backups
A daily backup backs up just those files that changed the same day that the backup was performed
A daily backup examines the modification date stored with each file's directory entry to determine whether a file should be backed up.
Daily backups don't reset the archive bit
==WARNING==
	I’m not a big fan of this option because of the small possibility that some files may slip through the cracks. Someone may be working late one night and modify a file after the evening’s backups have completed — but before midnight — meaning that those files won’t be included in the following night’s backups. Incremental or differential backups, which rely on the archive bit rather than the modification date, are more reliable.
#### Incremental Backups
An incremental backup backs up only those files that were modified since the last time you did a backup.
Incremental backups are a lot faster than full backups because your network users probably modify only a small portion of the files on the server on any given day
Incremental backups resets the file's archive bits.
Some thoughts about using incremental backups
- The easiest way to use incremental backup is to do a normal backup everyday and an incremental backup on each remaining normal business day
- When you use incremental backups, the complete backup consists of the full backup tapes and all the incremental backup tapes that you've made since you did the full backup
- Incremental backups complicate restoring individual files because the most recent copy of the file may be on the full backup tape or on any of the incremental backup
	==TECHNICAL STUFF==
	Backup programs keep track of the location of the most recent version of each file to simplify the process
- When you use incremental backups, you can choose whether you want to
	- Store each incremental backup on its own tape
	- Append each backup to the end of an existing tape
#### Differential backups
A differential backup is similar to incremental backup except that it doesn't reset the archive bit when files are backed up.
Suppose that you do a normal backup on Monday and differential backups on Tuesday, Wednesday, and Thursday, and your hard drive crashes Friday morning. On Friday afternoon, you install a new hard drive. To restore the data, you first restore the normal backup from Monday. Then you restore the differential backup from Thursday. The Tuesday and Wednesday differential backups aren’t needed
The main difference between incremental and differential backups is that 
- Incremental backups result in smaller and fast backups
- Differential backups are easier to restore
## Image-based backups and virtualization
If the server is running on virtual machine it is recommended to backup the server virtually 
Virtualization platforms such as VMware and Hyper-V have built-in capabilities to manage this replication, but you can also purchase third-party solutions that can turn this replication capability into a full-fledged backup solution
For example the Swiss-based company veeam has powerful backup solution that is specifically designed for virtual environments
One of the best features of the Veeam is that you can run a virtual server directly from a backup image, without the need to first do a time-consuming restore
## Backup Security
Backup policies and procedures are : 
- Set up a user account for the user who does backups. 
  Because this user account has backup permission for the entire server, guard its password carefully. Anyone who knows the username and password of the backup account can log on and bypass any security restrictions that you place on that user’s normal user ID.
- Counter potential security problems by restricting the backup user ID to a certain client and a certain time of the day.
  If you’re really clever (and paranoid), you can probably set up the backup user’s account so that the only program it can run is the backup program.
- Use encryption to protect the contents of your backups.
- Secure the backup tapes in a safe location, such as, um, a safe.