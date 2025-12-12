## Installing a Wireless Access Point
If you don't have an electrical outlet at the location where you want to place the access point, you can use a Power Over Ethernet (PoE) switch, which injects power on the ethernet cable.
An alternative to using a PoE switch is to use a device called a PoE injector. A PoE injector has two Ethernet jacks an input and an output plus a power cable. The input jack accepts a standard Ethernet cable coming from a switch. You can then connect one end of an Ethernet cable to the injector’s output jack and the other end to the access point. The PoE injector adds power to the output jack to provide power for the access point.
## Configuring a Wireless Access Point
Wireless Access point is configured through web interface 
And to go to that interface type the IP address of the Wireless access point that is written in the documentation
#### Basic Configuration options
![[Pasted image 20250703105732.png]]
The setup page of this router lets you figure information such as host name and IP address of the router and whether the router's DHCP server should be enabled.
Options that are found on additional tabs let you configure wireless settings such as the network name (also called the SSID), the type of security to enforce, and a variety of other settings
#### DHCP Configuration
![[Pasted image 20250703110005.png]]
To enable DHCP you select the Enable option and then specify the other configuration option to use the DHCP server
## Connecting to a Wireless Network
CHOOSING A WIRELESS NETOWRK IN WINDOWS 10
![[Pasted image 20250703110127.png]]
To tell windows to forget a network, follow these steps
1. Click Start, and then tap Settings.
	The Settings window appears.
2. Click Network & Internet.
	This brings up the Network & Internet page.
3. Click Wi-Fi.
	This brings up the Wi-Fi settings page.
4. Click Manage Wi-Fi Settings.
	This brings up the Manage Wi-Fi Settings page, which includes a section titled Manage Known Networks.
5. In the Manage Known Networks section, click the network you want to forget.
	The network is selected, 
6. Tap Forget.
	The network will be forgotten. To log into this network again, you’ll have to enter the security key.
![[Pasted image 20250703110312.png]]
## Paying Attention to Wireless Network Security
### Understanding Wireless Security Threats
As a network administrator, you need to balance the need of legitimate users to access network resources against the risk of illegitimate users breaking into your network. That's the basic dilemma of network security
#### Intruders
With a wired network, an intruder usually must gain access to your facility to physically connect to your network.
Possibilities of getting hacked : 
- If you share a building with other tenants, the other tenants’ offices may be within range.
- If you’re in a multi floor building, the floor immediately above or below you may be in range.
- The lobby outside your office may be within range of your network.
- The parking lot outside or the parking garage in the basement may be in range.
- If a would-be intruder can’t get within normal broadcast range, he or she may try one of several tricks to increase the range:
- A would-be intruder can switch to a bigger antenna to extend the range of his or her wireless computer. Some experiments have shown that big antennas can receive signals from wireless networks miles away. In fact, I once read about someone who listened in on wireless networks based in San Francisco from the Berkeley hills, across San Francisco Bay.
- If a would-be intruder is serious about breaking into your network, he or she may smuggle a wireless repeater device into your facility or near it to extend the range of your wireless network to a location that he or she can get to.
==REMEMBER==
	A physical connection to your network isn’t the only way an intruder can gain access, of course. You must still take steps to prevent an intruder from sneaking into your network through your Internet gateway. In most cases, this means that you need to set up a firewall to block unwanted and unauthorized traffic.
### Freeloaders
Freeloaders are intruders who want to piggyback on your wireless network to get free access to the internet
Even though freeloaders may be relatively harmless, they can be a potential source of trouble. In particular : 
- Freeloaders use bandwidth that you’re paying for. As a result, their presence can slow down Internet access for your legitimate users.
- After freeloaders gain Internet access through your network, they can potentially cause trouble for you or your organization. They may use your network to download illegal pornography, or they may try to send spam via your mail server. Most ISPs will cut you off cold if they catch you sending spam, and they won’t believe you when you tell them that the spam came from a kid parked in a Pinto out in your parking lot.
- If you’re in the business of selling access to your wireless network, obviously, freeloaders are a problem.
- Freeloaders may start out innocently looking for free Internet access. Once they get in, though, curiosity may get the better of them, leading them to snoop around your network.
- If freeloaders can get in, so can malicious intruders.
#### Eavesdroppers
It is just like to listen to your network traffic.
They don't actually try to gain access via your wireless network at least, not at first, they just listen
Unfortunately wireless networks give them plenty to listen to : 
- Most wireless access points regularly broadcast their Service Set Identifiers (SSIDs) to anyone who’s listening.
- When a legitimate wireless network user joins the network, an exchange of packets occurs as the network authenticates the user. An eavesdropper can capture these packets and, if security isn’t set up right, determine the user’s login name and password.
- An eavesdropper can steal files that are opened from a network server. If a wireless user opens a confidential sales report that’s saved on the network, the sales-report document is broken into packets that are sent over the wireless network to the user. A skilled eavesdropper can copy those packets and reconstruct the file.
- When a wireless user connects to the Internet, an eavesdropper can see any packets that the user sends to or receives from the Internet. If the user purchases something online, the transaction may include a credit card number and other personal information. (Ideally, these packets will be encrypted so that the eavesdropper won’t be able to decipher the data.)
#### Spoilers
A spoiler is a hacker who gets kicks from jamming networks so that they become unusable.
A spoiler usually accomplishes this act by flooding the network with meaningless traffic so that legitimate traffic gets lost in the flow. 
Spoilers may also try to  place viruses or worm programs on your network via an unsecured wireless connection
#### Rogue Access points
One of the biggest problems that network administrators have to deal with is the problem of rogue access points.
A rogue access point is an access point that suddenly appears on your network out of nowhere
a rogue access point can operate undetected on your network for months or even years. You may not discover it until you report to work one day and find that your network has been trashed by an intruder who found his or her way into your network via an unprotected wireless access point that you didn’t even know existed.
Some steps to reduce the risk of rogue access points appearing on your system : 
- Establish a policy prohibiting users from installing wireless access points on their own. Then make sure that you inform all network users of the policy, and let them know why installing an access point on their own can be such a major problem.
- If possible, establish a program that quickly and inexpensively grants wireless access to users who want it. Rogue access points show up in the first place for two reasons:
	- Users need the access.
	- The access is hard to get through existing channels.
- If you make it easier for users to get legitimate wireless access, you’re less likely to find wireless access points hidden behind file cabinets or in flower pots.
- Once in a while take a walk through the premises, looking for rogue access points. Take a look at every network outlet in the building see what’s connected to it.
- Turn off all your wireless access points and then walk around the premises with a wireless-equipped mobile device such as a smartphone and look for wireless networks that pop up. Just because you detect a wireless network, of course, doesn’t mean you’ve found a rogue access point; you may have stumbled onto a wireless network in a nearby office or home. But knowing what wireless networks are available from within your office will help you determine whether or not any rogue access points exist.
### Securing your wireless network
Steps taken to secure your wireless network are : 
##### Changing the Password
The first thing you should do when you install a wireless access point is change its administrative password.
Most access points have a built-in, web based setup page that you can access from any web browser to configure the access point's settings. 
The setup page is protected by a username and password, but the username and password are initially set to default values that are easy to guess
##### Securing the SSID
The next step is to secure the SSID that identifies the network
A client must know the access point's SSID to join the network
==WARNING==
	Securing the SSID isn’t a complete security solution, so you shouldn’t rely on it as your only security mechanism. SSID security can slow down casual intruders who are just looking for easy and free Internet access, but it isn’t possible to prevent serious hackers from discovering your SSID.
Things to secure your SSID are : 
- Change the SSID from the default
- Disable SSID broadcast
- Disable guest mode
==WARNING==
	Unfortunately, when a client computer connects to a wireless network, it sends the SSID to the access point in an unencrypted packet. So a sophisticated intruder who’s using a packet sniffer to eavesdrop on your wireless network can determine your SSID as soon as any legitimate computer joins the network.
##### Enabling WEP
WEP stands for wired equivalent privacy and designed to make wireless transmission as secure as transmission over a network cable.
WEP encrypts your data by using either a 40-bit key or 128-bit key
40bit encryption is faster than 128 bit encryption
COMMON DEFAULT SSID VALUES
![[Pasted image 20250703115442.png]]
**NOTE** WEP is less secure than other security methods such as WPA and WPA2. You should use WEP only if you need to connect to devices that do not support WPA or WPA2
To use WEP, both the clients and the server must know the encryption keys being used. A client that doesn't know the access point's encryption keys won't be able to join the network
You can specify encryption keys for WEP in two ways.
The first way is to create the ten-digit key manually by making up a random number.
The second method is to use a passphrase, which can be any word or combination of numerals and letters that you want
WEP automatically converts the passphrase to the numeric keys used to encrypt data.
If the client knows the passphrase used to generate the keys on the access point the client will be able to access the network
==WARNING==
	As it turns out, security experts have identified several flaws in WEP that compromise its effectiveness. As a result, with the right tools, a sophisticated intruder can get past WEP. So although it’s a good idea to enable WEP, you shouldn’t count on it for complete security.
WEP take to steps to increase its effectiveness
- Make WEP mandatory
- Change the encryption keys
![[Pasted image 20250703115949.png]]
#### Using WPA & WPA2
WPA stands for Wi-Fi protected access.
The big difference between WPA and WEP is that when you use WPA, the encryption key is automatically changed to regular intervals.
Few additional things to know about WPA are :
- A small office and home version of WPA, called WPA-PSK, bases its encryption keys on a passkey value that you supply. True WPA devices, however, rely on a special authentication server to generate the keys.
- All versions of Windows since Windows XP Service Pack 2 have built-in support for WPA.
- The official IEEE standard for WPA is 802.11i. However, WPA devices were widely available before the 802.11i standard was finalized; as a result, not all WPA devices implement every aspect of 802.11i.
- The original version of WPA has been superseded by a newer version, named WPA2.
#### Using MAC address filtering
MAC address filtering allows you to specify a list of MAC addresses for the devices that are allowed to access the network or are prohibited from accessing the network.
==WARNING==
	Unfortunately, it isn’t difficult to configure a computer to lie about its MAC address. Thus, after a potential intruder determines that MAC filtering is being used, he or she can just sniff packets to determine an authorized MAC address and then configure his or her computer to use that address. (This practice is called MAC spoofing.) So you shouldn’t rely on MAC address filtering as your only means of security.
![[Pasted image 20250703120403.png]]
MAC ADDRESS TABLE FOR A D-LINK WIRELESS ROUTER
![[Pasted image 20250703120424.png]]
##### Placing your access point outside the firewall
The most effective security technique for wireless networking is placing all your wireless access point outside your firewall.
That way all the network traffic from wireless users will have to travel through the firewall to access the network
To get around those limitations, you can enable a virtual private network (VPN) connection for your wireless users. 
The VPN will allow full network access to authorized wireless users
#### Troubleshooting  a wireless network
Some troubleshooting tips that can help to restore normalcy to a failing wireless network
##### Checking for obvious problems
Before you roll up your sleeves and take drastic correction action, you should check for a few obvious things, if you're having wireless network trouble.
The following list highlights some basic things you should check for
- Is everything turned on? Make sure you have lights on your wireless access point/router, as well as on your cable or DSL modem.
- Many access point/routers use a power supply transformer that plugs into the wall. Make sure that the transformer is plugged into the wall outlet and that the small cable that comes out of the transformer is plugged into the power connector on the access point/router.
- Are the cables connected? Check the network cable that connects your access point/router to the cable or DSL modem.
- Try restarting everything. Turn off the computer, the access point/router, and your cable or DSL modem. Leave everything off for at least two minutes. Then turn everything back on. Sometimes, simply cycling the power off and back on clears up a connection problem.
##### Pinpointing the Problem
if you can't connect to the internet, one of the first steps is finding out whether the problem is with your access point/ router or with your broadband connection .
Here is one way you can check to find out whether your wireless connection is working
1. Open CMD
2. Type ipconfig
![[Pasted image 20250703121042.png]]
If the display resembles this but with different numbers, you're connected to the wireless network, and the problem most likely lies with your broadband modem
But if the IP address, Subnet mask and default gateway indicate 0.0.0.0 instead of valid IP addresses, you have a problem with your wireless network
##### Changing channels
One of the most common sources of wireless network trouble is interference from other wireless devices
The simplest solution to this type of interference is changing channels
802.11b access points let you select 1 of 11 different channels to broadcast on. If you’re having trouble connecting to your access point, try changing the channel. To do that, you must log on to the router with the administrator password. Then hunt around the router’s administrator pages until you find the controls that let you change the channel. You may have to try changing the channel several times before you solve the problem. Unfortunately, 802.11b channels overlap slightly, which means that broadcasts on one channel may interfere with broadcasts on adjacent channels. Thus, if you’re having trouble connecting on channel 1, don’t bother switching to channel 2. Instead, try switching to channel 5 or 6. If that doesn’t work, switch to channel 10 or 11.
##### Fiddling the antennas
Fiddling means manipulation
You can fix intermittent connection problems by fiddling with the antennas on the access point and your computer's wireless adapter.
![[Pasted image 20250703121442.png]]
A more drastic fix is to add a signal booster to your access point.
A signal booster is a power amplifier that increases the transmission power of most wireless devices by a factor of five
##### Adding another access point
If you have a computer that's out of range of your access point, one solution is to add a second access point closer to the problematic computer
An alternative to a second access point is simply adding a range extender
Using a range extender will slow down your Wi-fi Connection
![[Pasted image 20250703121714.png]]
