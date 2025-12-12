This chapter gives you some suggestions on what to do when it becomes
impossible to keep all this stuff in your head.
# Introducing IT Asset Management
IT asset management (ITAM) is a program that assumes the responsibility for managing the life cycle of all IT assets within an organization
IT assets include hardware assets and software assets
For a hardware asset such as a computer, the life cycle includes : 
- Acquisition: Consideration of alternative proposals for the asset, planned usage of the asset, development of new or application of existing policies related to the asset, and the actual purchase of the asset
- Deployment: Installation and configuration of the asset for use by a specific user
- Support: Any necessary reconfiguration, repair, upgrades, or installation of new software that may be done during the asset’s useful life
- Redeployment: For example, when a desktop computer is redeployed to a different user or application
- Retirement: When an asset is taken out of service due to obsolescence or changing business needs
- Disposition: When the asset is physically disposed of (e-wasted or sold) and is no longer owned by the organization
The ITAM program should be able to accommodate a variety of licensing models so that you can track your software assets
## Why Bother?
Some top reasons to maintain an accurate and detailed record of all your IT assets : 
- To prevent loss due to theft or neglect of equipment
- To reduce cost by not purchasing unnecessary equipment and by repurposing existing equipment for new applications
- To improve performance by retiring and replacing obsolete equipment
- To comply with auditing or regulatory requirements
- To control the cost of maintaining equipment
- To ensure proper recovery of lost or damaged equipment, especially if an insurance claim is necessary
- To prevent the serious security threat that occurs when assets are lost
## Getting Organized
The first step for creating a system to track the assets on your network is
to get organized. 
Start by making a list of the various types of IT assets that exist within your organization. 
This list might include
- Desktop computers
- Portable computers
- Tablets
- Smartphones
- MiFi devices (hotspots)
- Printers
- Scanners
- IP phones
- Servers
- Switches
- Wireless access points
- Routers
![[Pasted image 20250715183324.png]]
## What to Track
When putting together a database for tracking IT assets, you should carefully consider the type of information you want to track
At the minimum, You should track these : 
- Asset Identifier 
- Type of asset : Develop a list of asset types and use a standard name for each type of asset (For example WK for workstation)
- Manufacturer, Product name, model Number, and serial number
- Asset's status : For example Deployed, In inventory, Retired or Disposed
- Date the asset was acquired
- The user currently assigned to the asset
- The date the asset was assigned to the current user
In particular, you may want to track the entire history of the asset. 
To do that Records should be maintained and that records should include:
- Asset identifier
- Event type (for example, “Deployed,” “Serviced,” “Returned to Inventory,” “Retired,” and so on)
- Event date
- Name of the user
- Name of the technician
- Description
## Taking Pictures
Consider including a photograph of each asset in your asset database
Including a picture can be especially useful if the asset is stolen or
damaged and an insurance claim is made.
A good photograph coupled with an accurate description can go a long ways toward establishing the legitimacy of a loss claim
## Picking a Number
To keep track of your computer inventory, you’ll need to assign each
device in your inventory a unique identifier. 
You can call this identifier an asset identifier, asset number, tracking number, or anything else that makes sense to you.
If your initial goal is to keep track of Windows computers, you may be
tempted to use each computer’s Active Directory computer name to
uniquely identify your assets. For two reasons
- Even if you initially start with Windows computers, you’ll eventually realize that you also need to track other types of devices, such as smartphones, tablets, and cellular hotspots. Not all these devices lend themselves to Active Directory naming conventions.
- More important, it’s easy to change the name of a Windows computer. If you rename a device, you’ll have to remember to rename the device in your asset database.
==TECHNICAL STUFF==
	In case you’re interested, database normalization refers to the design of database structures that meet an idealized concept known as normal form. One of the basic normalization rules is that every column should signify one and only one thing; a single column should not be overloaded with two or more meanings. So, the asset ID should not represent both a sequence number and a type. Instead, the type should be indicated in a separate column. (To be fair, I should point out that many common unique identifiers are overloaded with additional information. For example, an automobile vehicle identification number [VIN] includes many attributes about the vehicle, including the country, manufacturer, plant, and model year in addition to a sequence number. And the venerable MAC address, which uniquely identifies network hardware, indicates the manufacturer as well as a unique serial number.)
## Making Labels
One of the basic steps in keeping track of your computer equipment is to
physically apply a label on every piece of equipment maintained in your
asset inventory.
![[Pasted image 20250715184408.png]]
Few tips for making labels are : 
- Don't use handheld or desktop label maker unless you have only a few asset to track. Instead use a computer-attached label printer
- Consider printing the asset ID number in bar code format. Then you can use a bar code reader whenever you need to read the label.
- Use tamper-proof label tape when printing labels. It costs a bit more but is worth it.
- Affix the labels in a consistent location for each device type.
- Always affix the label to the device itself, not to a protective case.
- If possible, incorporate your company’s branding into the design of the label. Get help from the marketing or publicity department to make sure your labels are consistent with company branding.
## Tracking Software
Many software products offer their own license management portals you can use to manage their licenses
Examples are: 
- If you use Microsoft Volume Licensing for your Microsoft software, you can use the Volume Licensing Center (available via www.microsoft.com/licensing).
- You can manage Office 365 from the Office 365 admin center. Just log in at www.office.com, and then choose Admin from the app launcher. (You must have admin permissions, of course.)
- For Adobe Creative Suite products (such as Acrobat, Photoshop, InDesign, and so on), log in to the team management portal at http://accounts.adobe.com. This portal allows you to view all your Adobe subscription licenses and purchase additional seats if needed.
## Using Asset-Tracking Software
When searching for asset management software, here are a few features I
suggest to look for:
- Simple installation and management: Asset management is an ideal application for a cloud-based service rather than an on-premises install.
- Secure access: If you do go with a cloud-based option, it’s imperative that the data be secure.
- Web-based interface: That way, a client install is not required. It will be very helpful to access your asset management software from any computer on your network so that you don’t have to return to your office to look up or update an asset’s record.
- Mobile app support: This allows you to easily scan a bar code label with your smartphone or tablet to call up an asset’s record. Customizable fields: This allows you to set up the tracking records to meet your own unique needs.
- Customizable reports: These let you meet your organization’s reporting standards.
- Import capabilities: This allows you to convert your current asset tracking spreadsheets to the new system. 
- Pricing that scales with volume: That way, you don’t pay for capacity you don’t need.
- Responsive support and good training resources.
## Other Sources of Asset Tracking information
In addition to dedicated asset-tracking service, there are several other
places you can go for information that can be helpful for tracking IT
assets. 
Here are a few:
- Cellphone vendor portals: All major mobile phone providers have online portals for managing your accounts. These portals typically let you view and edit all the phone lines on your account, with details including who the phone is assigned to, how much usage the phone has incurred, the exact make and model of the phone, and when the phone is eligible for upgrade. If a phone is lost or stolen, you can disable or deactivate the device.
  These vendor portals also track MiFi hotspot devices as well.
- Copier vendor portals: If your organization leases its copiers and has a support plan, your provider probably has a service and support portal you can use to manage your devices. This portal can give you up-to-date information about the make, model, and location of each of your copiers. And you can keep track of maintenance and supplies needed for the copiers.
- Switch or router management pages: Modern switches and routers include management pages that can be useful for managing network assets. For example, the management page for a switch can reveal information about the devices that are attached to each of the switch’s ports. Some switches provide basic information such as IP address, but others provide detailed information including the computer name for Windows computers connected to the switch.
