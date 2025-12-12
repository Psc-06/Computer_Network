# What Directories Do
Directories is the service that allows you to perform some services for example making a call. 
So we will understand with example what does directories do 
To make a call in early 90s the user need to search for the mobile no. And for searching in the mobile no he need to search in his directories. 
And this makes the problem because imagine a user wants to call to a dozen of person in his day. He need to search for every directory to get his phone number. 
So this is the problem that a user face or we can say that this is the disadvantages of directories.
In short we can say that directories is the phone book.
## Remembering the Good Ol’ days of NT Domains
Active directory was introduced with windows 2000 server
Before then, the directory management system in a windows network has managed by windows NT domains, which stored directory information in a database called the Security Account Manager (SAM) database
#### PDCs and BDCs
The most important thing to know about NT domains is that they are servercentric that is every Windows NT domain is under the control of a windows NT server computer that hosts the primary copy of the SAM database. This server is called the Primary Domain Controller (PDC)
Windows NT domains can also be serviced by one or more backup domain controllers (BDCs).
Each BDC stores a read-only copy of the SAM database, and any changes made to the SAM database on the PDC must be propagated down to the BDC copies of the database.
If the PDC should fail for some reason, one of the BDCs can be promoted so that it becomes the PDC for the domain
#### Trusts
The domain that does the trusting is called the trusting domain
&
The domain that contains the information being trusted is called the trusted domain
Trust relationship work in one direction.
Trust relationship aren't transitive
( TRANSITIVE
$A = B$ 
$B = C$
$A = C$
)
#### NetBIOS names
Important characteristic of Windows NT domains is that they use NetBIOS names
NT names such as computer names and domain names are limited to 15 characters
==TECHINCAL STUFF==
	Actually, NetBIOS names are 16 characters long. But NT uses the last character of the 16-character NetBIOS name for its own purposes, so that character isn’t available for use. As a result, NT names can be only 15 characters long.
# Active Directory to the Rescue
Active Directory is a comprehensive directory management system that tracks just about everything worth tracking in a windows network, including users, computers, files, folders, application and much more
One of the most important differences between Active Directory and NT domains is that Active directory isn't servercentric
Active directory uses the same naming scheme that's used on the internet, domain name system (DNS).
An active directory domain might have a name like sales.mycompany.com
# Understanding How Active Directory is structured
Active directory is essentially a database management system
The active directory database is where the individual objects tracked by the directory are stored
It uses a hierarchical database
#### Objects
The basic unit of data in active directory is called an object
![[Pasted image 20250709220122.png]]
To get to this management tool 
Choose
Start => Administrative Tools =>Active directory users and computers
Then
Click builtin node to show the built-in objects
Objects have descriptive characteristics called properties or attributes
#### Domains
A domain is the basic unit for grouping related objects in active directory.
Nimbus Brooms, and you've registered NimbusBroom.com as your domain name, you should create a top-level domain named NimbusBroom.com before you create any other domains. Then you can create subdomains such as Accounting.NimbusBroom.com, Manufacturing.NimbusBroom.com, and Sales.NimbusBroom.com.
==TIP==
	 If you have Microsoft Visio, you can use it to draw diagrams for your Active Directory domain structure. Visio includes several templates that provide cool icons for various types of Active Directory objects.
	 DOMAINS FOR A COMPANY WITH THREE DEPARTMENTS
	![[Pasted image 20250709220412.png]]
A feature called replication works hard at keeping all the domain controller in sync
#### Organizational units
Active directory lets you create one or more organizational units (OUs)
One reason to create OUs within a domain is to assign administrative rights to each OU of different users. Then these users can perform routine administrative tasks such as creating new user accounts or resetting passwords.
#### Trees
A tree is a set of active directory names that share a namespace
The domains NimbusBroom.com, Accounting.NimbusBroom.com, Manufacturing.NimbusBroom.com, and Sales.NimbusBroom.com make up a tree that's derived from a common root domain, NimbusBroom.com.
The domains that make up a tree are related to one another through transitive trusts.
==TIP==
	A single domain all by itself is still considered to be a tree
#### Forests
A forest is collection of one or more domain trees that do not share a common parent domain
A FOREST WITH TWO TREES
![[Pasted image 20250709220814.png]]
The key to active directory forests is a database called the global catalog.
The global catalog is sort of a suuperdirectory that contains information about all the objects in a forests, regardless of the domain.
If a user account can't be found in the current domain, the global catalog is searched for the account. The global catalog provides a reference to the domain in which the account is defined
# Creating a New Domain
To create a domain, you start by designation a windows server 2019 system to be the new domain's controller
To do this use server manager to install active directory domain services role![[Pasted image 20250709221055.png]]
The Wizard gives you three options : 
- Add a domain controller to an existing domain
- Add a new domain to an existing forest
- Add a new forest
# Creating an Organization Unit
Organization units can simplify the task of managing large domains by dividing users, groups, and other objects into manageable collections
If you want to create additional organization units to help manage a domain, follow these steps.
1. In server manager choose tools => Active directory users and computers
	![[Pasted image 20250709221314.png]]
2. Right click the domain you want to add the OU to and choose 
   New => Organizational unit
	![[Pasted image 20250709221344.png]]
3. Type a name for the new organization unit
4. Click ok
==TIP==
	Each domain you create in active directory has a handful of default OUs that are set up automatically by active directory
	- Builtin
	- Computers
	- Domain Controllers
	- Foreign Security Principals
	- Managed Service Accounts 
	- Users
Create OUs to contain the three most important common types of active directory objects you'll create 
- Computers 
- Groups 
- Users
Few more points about OUs
- You can delegate administrative authority for an OU to another user by right-clicking the OU and choosing Select Delegate Control from the contextual menu. Then you can select the user or group that will have administrative authority over the OU. You can also choose which administrative tasks will be assigned to the selected user or group.
- Remember that OUs aren’t the same as groups. Groups are security principals, which means that you can assign them rights. Thereafter, when you assign a user to a group, the user is given the rights of the group. By contrast, an OU is merely an administrative tool that lets you control how user and group accounts are managed.
