Two basic technique for securing your network's internet connection
- Firewall
- Virus Protecting
# Firewalls
A firewall is a security-conscious router that sits between the Internet and your network with a single-minded task preventing them from getting to us. 
The firewall acts as a security guard between the Internet
and your local area network (LAN). 
All network traffic into and out of the LAN must pass through the firewall, which prevents unauthorized access to the network.
You can set up a firewall in two basic ways
- The easiest way is to purchase a firewall appliance, which is basically a self-contained router with built-in firewall features
- You can set up a server computer to function as a firewall computer. The server can run just about any network operating system (NOS), but most dedicated firewall system run Linux
USING A FIREWALL APPLIANCE
![[Pasted image 20250716211022.png]]
==TECHINCAL STUFF==
	The term perimeter is sometimes used to describe the location of a firewall on your network. In short, a firewall is like a perimeter fence that completely surrounds your property and forces all visitors to enter through the front gate.
## The Many types of Firewalls
Firewalls employ four basic techniques to keep unwelcome visitors out of your network
#### Packet filtering
A packet-filtering firewall examines each packet that crosses the firewall and test the packet according to a set of rules that you set up.
Packet filters are the least expensive type of firewall
Packet filters work by inspecting the source and destination IP and port addresses contained in each Transmission Control Protocol/Internet Protocol (TCP/IP) packet.
SOME WELL-KNOWN TCP/IP PORTS
![[Pasted image 20250716211354.png]]
![[Pasted image 20250716211358.png]]
One of the biggest weaknesses of packet filtering is that it pretty much trusts that the packets themselves are telling the truth when they say who they’re from and who they’re going to. 
Hackers exploit this weakness by using a hacking technique called IP spoofing, in which they insert fake IP addresses in packets that they send to your network.
Another weakness of packet filtering is that it examines each packet in isolation without considering what packets have gone through the firewall before and what packets may follow. In other words, packet filtering is stateless.
In spite of these weaknesses, packet-filter firewalls have several advantages that explain why they are commonly used:
- Efficient: They hold up each inbound and outbound packet for only a few milliseconds while they look inside the packet to determine the destination and source ports and addresses. After these addresses and ports are determined, the packet filter quickly applies its rules and either sends the packet along or rejects it. In contrast, other firewall techniques have a more noticeable performance overhead.
- Almost completely transparent to users: The only time a user will be aware that a packet-filter firewall is being used is when the firewall rejects packets. Other firewall techniques require that clients and/or servers be specially configured to work with the firewall.
- Inexpensive: Even consumer-grade routers include built-in packet filtering.
#### Stateful Packet Inspection (SPI)
Stateful packet inspection (SPI) is a step up in intelligence from simple packet filtering. 
A firewall with stateful packet inspection looks at packets in groups rather than individually.
It keeps track of which packets have passed through the firewall and can detect patterns that indicate unauthorized access.
In some cases, the firewall may hold on to packets as they arrive until the firewall gathers enough information to make a decision about whether the packets should be authorized or rejected.
#### Circuit-level Gateway
A circuit-level gateway manages connections between clients and server based on TCP/IP addresses and port number.
After the connection is established, the gateway doesn't interfere with packets flowing between the systems
#### Application Gateway
An application gateway is a firewall system that is more intelligent than a packet-filtering firewall, stateful packet inspection, or circuit-level gateway firewall.
Packet filters treat all TCP/IP packets the same. In contrast, application gateways know the details about the applications that generate the packets that pass through the firewall.
Application gateway work as a proxy server
Proxy server is a server that sits between a client computer and a real server
The proxy server can examine the packet and decide to pass it on to the real server, or it can reject the packet
Or
The proxy server may be able to respond to the packet itself without involving the real server at all
Application gateways are more secure than simple packet-filtering firewalls, which can deal with only one packet at a time
Application gateways slow network performance because they do more detailed checking of packets before allowing them to pass.
## Firewall Best Practices
Best practices for deploying firewalls in your organization are :
- Always protect external connections with a firewall appliance
- Don't skimp (Compromise money )when it comes to firewall
- Use firewall appliances in pars for redundancy
- Keep your firewalls up to date
- Block everything by default
- Document your firewall rules
- Periodically review your firewall logs and configuration
- Enable the built-in Windows Defender Firewall on your endpoint computers
## The Built-In Windows Firewall
The steps to activate the firewall in windows are : 
1. Choose Start => Settings => Windows Security => Firewall & Network Protection   ![[Pasted image 20250716212950.png]]
2. To change the firewall status for Domain, Private or Public networks, click Domain, Private or Public![[Pasted image 20250716213023.png]]
3. Use the slider button to turn Window Defender Firewall On or Off
## Configuring Windows Defender Firewall with group policy
The Group Policy settings for Windows Defender Firewall can be found at the following location in the Group Policy Management Editor:
![[Pasted image 20250716213121.png]]
![[Pasted image 20250716213126.png]]
Steps to create a GPO to activate the firewall on all network are :
1. Use Remote Desktop Connection to connect to an Active Directory server and open the Group Policy Management console
2. In the navigate pane, right-click the Group Policy Objects for your domain and Choose New
3. Enter a name for the new GPO and click OK
4. Scroll down tot he GPO you just created, right-click it and choose edit![[Pasted image 20250716213323.png]]
5. Under Computer Configuration, open Policies, Windows Settings, Security Settings, and Windows Defender firewall with advanced Security
6. Right-click Windows Defender firewall with Advanced Security and choose properties![[Pasted image 20250716213415.png]]
7. Enable the firewall on the domain tab
8. Click ok and then choose the group policy management editor
9. Link the new GPO to enforce the policy on your end-user computers
10. You're done

After you’ve enabled the firewall on end-user computers, you’ll need to add rules to open ports that are required by the applications your users need. 
Here are the steps to open a specific port or group of ports in the firewall:
1. Open the Group Policy Management Editor
2. Under computer configuration, open policies, windows settings, security settings and window defender firewall with advanced security
3. Select inbound rules and then click right-click and choose new policy![[Pasted image 20250716213615.png]]
4. Select the type of rule you want to create
   The choices are : 
	- Program: A rule that allows a specific program to connect.
	- Port: A rule that opens a specific TCP or UDP port.
	- Predefined: Predefined rules for well-known services such as DHCP, DNS, and Remote Desktop.
	- Custom: A completely customizable rule that lets you choose not only protocols and ports but also ranges of IP address, specific programs that the rule applies to, and more.
5. Click Next![[Pasted image 20250716213707.png]]
6. Select whether the rule applies to TCP or UDP and then enter the ports or ports that should be opened
7. Click Next![[Pasted image 20250716213730.png]]
8. Choose how you want the rule to treat traffic on the ports
9. Click Next![[Pasted image 20250716213752.png]]
10. Choose the profile that this rule should apply to 
11. Click Next![[Pasted image 20250716213804.png]]
12. Enter a name and a description
13. Click Finish
# Virus Protection
### What is a virus
Every computer user is susceptible to attacks by computer viruses, and using a network increases your vulnerability because it exposes all network users to the risk of being infected by a virus that lands on any one network user’s computer.
Viruses are computer programs that are created by malicious programmers
Virus Programmers have discovered that email is a very efficient method to spread their viruses
Here are some information about protecting your network from virus attacks : 
- The term virus is often used to refer not only to true virus programs (which are able to replicate themselves) but also to any other type of program that’s designed to harm your computer. These programs include so-called Trojan horse programs that usually look like games but are, in reality, ransomware.
- A worm is similar to a virus, but it doesn’t actually infect other files. Instead, it just copies itself onto other computers on a network. After a worm has copied itself onto your computer, there’s no telling what it may do there. For example, a worm may scan your hard drive for interesting information, such as passwords or credit card numbers, and then email them to the worm’s author.
- Computer virus experts have identified several thousand “strains” of viruses. Many of them have colorful names, such as the I Love You virus, the Stoned virus, and the Michelangelo virus.
- Antivirus programs can recognize known viruses and remove them from your system, and they can spot the telltale signs of unknown viruses. Unfortunately, the idiots who write viruses aren’t idiots (in the intellectual sense), so they’re constantly developing new techniques to evade detection by antivirus programs. New viruses are frequently discovered, and antivirus programs are periodically updated to detect and remove them.
### Antivirus Programs
The best way to protect your network from virus infection is to use an antivirus program. 
These programs have a catalog of several thousand known viruses that they can detect and remove.
In addition, they can spot the types of changes that viruses typically make to your computer’s files, thus decreasing the likelihood that some previously unknown virus will go undetected.
Here are several approaches to deploying antivirus protection on your network
- Install antivirus software one each network user's computer
- Managed antivirus services place antivirus client software on each client computer in your network
- Server-based antivirus software protects your network server form viruses
- Some firewall appliance include antivirus enforcement checks that don't allow your users to access the Internet unless their antivirus software is up to date
Here are few tips for choosing an antivirus program for your environment : 
- Cost should be the last thing you consider when choosing an antivirus platform
- Choose antivirus software that performs well on benchmark test that indicate how through the software is at catching malware
- Choose antivirus software that has centralized management
- Choose antivirus software that can stop an active ransomware attack
- Consider antivirus software that integrates well with your firewall
### Safe Computing
Besides using an antivirus program, you can take a few additional precautions to ensure virus-free computing.
- Regularly back up your data
- If you buy software from a store and discover that the seal has been broken on the disc package take the software back
- Use your antivirus software to scan your disk for virus infection after your computer has been to a repair shop or worked on by a consultant
- Don't open email attachments from people you don't know or attachments you weren't expecting
- Use your antivirus software to scan any floppy disk or CD that doesn't belong to you before you access any of its files