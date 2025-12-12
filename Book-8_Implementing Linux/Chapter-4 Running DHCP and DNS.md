# Running a DHCP Server
==TIP==
	Even for small networks, however, DHCP can be a timesaver. For example, suppose that you have a notebook computer that you take back and forth between your home and office. If you don’t set up a DHCP server at home, you have to change the computer’s static IP address each time you move the computer. With DHCP, the computer can change IP addresses automatically.
### Installing DHCP
You can quickly find out whether DHCP is installed on your system by entering the following command form a shell prompt
![[Pasted image 20250713222944.png]]
If DHCP has already installed, the dnf command will let you know that the package is already installed.
### Configuring DHCP
You configure DHCP settings through a file called dhcpd.conf that lives
in the /etc/dhcp directory.
![[Pasted image 20250713223046.png]]
Open this file in vi to review it
![[Pasted image 20250713223106.png]]
Description of the above file : 
- option domain-name: This line provides the domain name for the network.
- option domain-name-servers: This line provides the name or IP addresses of your DNS servers.
- subnet: This line specifies a subnet that's managed by this DHCP server. Following the subnet ID and netmask is an opening bracket; all the options that appear between this bracket and the closing bracket in the last line of the file belong to this subnet. In some cases, your DHCP server may dole out IP configuration information for two or more subnet groups. In that case, you need additional subnet groups in the configuration file.
- range: This line specifies the range of addresses that the DHCP server will assign for this subnet.
- option routers: This line provides the IP address of the Default Gateway.
- default-lease-time: This line determines the default lease time in seconds. The default in the example file (600 seconds, or 10 minutes) is far too short for anything other than a testing situation. 
  More common settings are:
	- 86400 (1 day)
	- 604800 (7 days)
	- 2592000 (30 days)
- max-lease-time: This line determines the maximum life of a lease.
- host: This line specifies a reservation. The host group specifies the MAC address for the host and the fixed IP address to be assigned.
### Starting DHCP
After you set up the configuration file, you can start DHCP by opening a terminal window or virtual console and entering the following command
![[Pasted image 20250713223416.png]]
You should also restart the service, whenever you make a change to the configuration file. 
To restart DHCP enter this command
![[Pasted image 20250713223444.png]]
To automatically start DHCP whenever you start the computer, run this command
![[Pasted image 20250713223501.png]]
# Running a DNS Server
Linux comes with BIND, the best DNS Server that money can buy.
### Installing BIND
You can quickly find out whether BIND is installed on your system by entering the following command from a shell prompt ![[Pasted image 20250713223614.png]]
After BIND has been installed you can start its server by entering the command
![[Pasted image 20250713223715.png]]
### Editing BIND configuration files
Like most things Linux, BIND is configured by editing configuration
files. These files live in one of two places: /etc or /var/named. The
following sections describe the most important configuration files.
##### named.conf
This file, found in the /etc directory, is the basic BIND configuration file.
This file contains global properties and links to the other configuration files
THE NAMED.CONF FILE
![[Pasted image 20250713223849.png]]
![[Pasted image 20250713223855.png]]
The zone lines name the zone files for each domain for which the server
is responsible. Initially, the file contains just one zone, which is used for
all lookups that aren't covered by local zones you add to the file. This
zone is defined by the following lines:
![[Pasted image 20250713223915.png]]
In the first line (zone), a single period is used as the domain name. 
The second line indicates that the zone type is hint, which means that the
zone will refer to the DNS root servers.
Finally, the third line provides the name of the file that identifies the root servers.
To edit the files to include your own zones
![[Pasted image 20250713224024.png]]
Then, you can create this file in the /etc directory and add a zone
statement for your domain's zone.
Here’s an example of a zone statement to create a new zone named
lowewriter.com:
![[Pasted image 20250713224043.png]]
Note that this zone specifies the type as master, which means that this
server is authoritative for the zone.
##### named.ca
The named.ca file, located in the /var/named directory, lists the names and addresses of the Internet's root servers.
A SAMPLE NAMED.CA FILE
![[Pasted image 20250713224159.png]]
![[Pasted image 20250713224204.png]]
==TIP==
	An organization named InterNIC keeps the named.ca file up to date. You can download the most current version of named.ca from the InterNIC FTP site at ftp.internic.net. Every once in a while, InterNIC publishes a new version of this file, so you should check now and then to make sure that your file is current.
##### Zone files
Each zone for which your DNS server is authoritative should have a
zone file, named domain.zone and located in the /var/named directory.
Here's a typically zone file, named lowewriter.com.zone : 
![[Pasted image 20250713224318.png]]
MOST COMMON TYPES OF RECORDS THAT APPEAR IN ZONE FILES![[Pasted image 20250713224345.png]]
### Restarting BIND
Whenever you make changes to BIND configuration files, you should restart the named service to apply the changes.
To do that, use this command
![[Pasted image 20250713224418.png]]
