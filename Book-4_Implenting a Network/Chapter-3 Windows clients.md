## Configuring Network Connections
Windows automatically detects and configures network adapters
The following steps that show you how to configure your network adapter on a windows 10 system are : 
1. Click the start icon and then tap or click settings
![[Pasted image 20250703190155.png]]
2. Click Network and Internet
![[Pasted image 20250703190210.png]]
3. Click Ethernet
![[Pasted image 20250703190220.png]]
4. Click Change Adapter options
![[Pasted image 20250703190237.png]]
5. Right click the connection that you want to configure and then choose properties from the contextual menu that appears
![[Pasted image 20250703190304.png]]
6. To Configure the network adapter card settings click configure
	![[Pasted image 20250703190453.png]]
	The dialog box has seven tabs that let you configure the adapter: 
	- General : This tab shows basic information about the adapter such as the device type and status
	- Advanced : This tab lets you set a variety of device-specific parameters that affect the operation of the adapter
	- About : Displays information about the device's patent protection
	- Driver : This tab displays information about the device driver that's bound to the NIC and lets you update the driver to a newer version, roll back the driver to a previously working version, or uninstall the driver
	- Details : With this tab, you can inspect various properties of the adapter such as the date and version of the device driver. To view the setting of a particular property, select the property name from the drop-down list
	- Events : This tab lists recent events that has been logged for the device
	- Power Management : This tab lets you configure power management options for the device
7. Review the list of connections items listed in the properties dialog box
	 ![[Pasted image 20250703190848.png]]
	 The most important items you commonly see are : 
	 - Client for Microsoft Networks : This item is required if you want to access  a Microsoft Windows network. It should always be present
	 - File and printer sharing for Microsoft Networks : This items allow your computer to share its files or printers with other computers on the network 
	 ==TIP==
		 This option is usually used with peer-to-peer networks, but you can use it even if your network has dedicated servers. If you don't plan to share files or printers on the client computer, however, you should disable this item
		 Internet Protocol Version 4 (TCP/IPv4) : This item enables the client computer to communicate by using the version 4 standard TCP/IP protocol
		 Internet Protocol Version 6 (TCP/IPv6) : This items enable version 6 of the standard TCP/IP protocol. Typically both IP4 & IP6 are enabled, even though most networks rely primarily on IP4
8. If a protocol that you need isn't listed, click the install button to add the needed protocol
9. To remove a network item that you don't need , select the item and click the uninstall button
10. To configure TCP/IP settings, click Internet Protocol (TCP/IP) click properties to display the TCP/IP properties dialog box, adjust the settings and then click ok
	![[Pasted image 20250703191824.png]]
	- Obtain an IP address automatically : Choose the option if your network has a DHCP server that assign IP address automatically. Choosing this option dramatically simplifies administering TCP/IP on your network
	- Use the following IP address : If your computer must have a specific IP address, choose this option and then type the computer's IP address, subnet mask, and default gateway address
	- Obtain DNS server address automatically : The DHCP server can also provide the address of the domain name system (DNS) server that the computer should use. Choose this option if your network has a DHCP server
	- Use the following DNS server addresses : Choose the option if a DNS server isn't available. Then type the IP address of the primary and Secondary DNS servers
## Joining a Domain
To use a computer in a domain network, you must joint the computer to the domain.
Here are the steps : 
1. Click the start icon and then tap or click settings
2. Click System
	![[Pasted image 20250703192538.png]]
3. Click about
	![[Pasted image 20250703192549.png]]
4. Click Rename this PC (advanced)
	![[Pasted image 20250703192611.png]]
5. Click the change button
	![[Pasted image 20250703192635.png]]
6. If you need to change the computer name, enter it in the computer name field
7. Enter the domain name and click OK
8. Enter the domain administrator credentials then click ok
9. When informed that you need to restart the computer Click restart now
We can join a domain when the windows edition is pro or enterprise 
For windows home edition joining domain is prohibited
