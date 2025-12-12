# Installing Apache
To install apache run the command
![[Pasted image 20250714102341.png]]
This command installs Apache plus a number of companion packages, including the following : 
- httpd-manual: Provides a web-based user manual for Apache. (You can access it at http://yourhost/manual, where yourhost is the name or IP address of the web server.
- mod-perl: Lets you run Perl programs in your web server.
- php: Allows you to deploy PHP applications to your web server. (If you're a programmer and you want to investigate PHP programming, check out the latest edition of my book, Java All-In-One For Dummies, available from Wiley, of course.)
- webalizer: Lets you analyze log data for your website; reports are generated in HTML format so you can view them in a browser.
## Starting and Stopping Apache
To start Apache run this command
![[Pasted image 20250714102529.png]]
Whenever you make a configuration change, you should do a graceful restart of the Apache Server
![[Pasted image 20250714102555.png]]
If you're not sure whether Apache is running, run this command
![[Pasted image 20250714102612.png]]
Output for this command is : 
![[Pasted image 20250714102636.png]]
To shut down Apache gracefully, run this command
![[Pasted image 20250714102701.png]]
You can run a configuration check to make sure your configuration files are correct by running this command
![[Pasted image 20250714102725.png]]
## Opening the Firewall for Apache
Apache communicates over two well-known ports : 
- port 80 for http:
- port 443 for https:
To get Apache to work, you'll need to open those ports.
You can do this also using Cockpit
So follow these steps : 
1. Open Cockpit on a remote computer
2. Click Networking   ![[Pasted image 20250714103031.png]]
3. In The firewall section, click Edit Rules and Zone  ![[Pasted image 20250714103048.png]]
4. Click Add Services![[Pasted image 20250714103058.png]]
5. Type http in the Filter Services text box
6. Check both http and https and then click add services
## Configuring that Apache is Running
You can test to see whether Apache is up and running by opening the
web browser on a computer connected to the same network as the server and enter either the hostname or the IP address of the server.
If Apache is running on the server it will look like this
![[Pasted image 20250714103211.png]]
If the apache is not running there are few things to check
- Make sure that the httpd service is running
- Try turning the firewall off altogether temporarily. To do this run this command
  ![[Pasted image 20250714103318.png]]
  If that solves the problem, revisit the firewall settings to confirm the correct ports are open. And be sure to restart the with the following command
  ![[Pasted image 20250714103412.png]]
- Confirm that Apache is running on the standard http and https port. To do this run this command
  ![[Pasted image 20250714103439.png]]
  The output will look like this![[Pasted image 20250714103452.png]]
## Looking at the httpd.config File
Apache’s primary configuration file is /etc/httpd/conf/httpd.conf.
APACHE SERVER DOCUMENTATION PAGE
![[Pasted image 20250714103558.png]]
Among other things, the httpd.conf file specifies the following configuration directives : 
- The port that the server listens on (80): You can modify httpd.conf to direct Apache to change the port or listen on multiple ports. The configuration line for this option is the following ![[Pasted image 20250714103639.png]]
- The name of the account and the group that Apache runs under (apache): The configuration lines are the following:![[Pasted image 20250714103651.png]]
- The email address of the web administrator: This is one of the most common lines to change. The default is the following:![[Pasted image 20250714103708.png]]
- The location of the root folder for web documents: The default is the following:
  ![[Pasted image 20250714103727.png]]
- File system access: The access rules start by prohibiting all access to the entire file system; then they grant access to specific directories that contain HTML or other content.
- Logging configuration, including where logs are written to (the default is /etc/httpd/logs/error_log), what level of events are logged, and the log format.
- An include statement
  ![[Pasted image 20250714103833.png]]
  This line includes all files that match the pattern * .conf in the /etc/httpd/conf.d directory as part of the configuration. This line allows you to extend Apache's configuration without editing the httpd.conf file. Instead, you can create new * .conf files in /etc/httpd/conf.d to add your own customizations.
## Understanding Access Rules
The httpd.conf file has several ines that are designed to protect your web server by denying web users access to any files outside of the website you create
The web root location configured by the DocumentRoot directive sets /var/www/html as the top-level directory where web resources should be placed.
The following lines in the httpd.conf file set up the access rules so that this and only this directory tree is accessible:
![[Pasted image 20250714104048.png]]
The first Directory section blocks all access to the entire file system,
starting at the root (/). It's important to remember that the access rules in a Directory section apply to all files in the named path and to all files in subdirectories of the path.
The AllowOverride directive
![[Pasted image 20250714104146.png]]
This directive tells Apache that the directory access specified cannot be overriden in separate files called .htaccess files.
AllowOverride none does not prevent the access rules from being overridden by subsequent sections within the httpd.conf file.
The Require directive specifies the access allowed or disallowed for the
section.
![[Pasted image 20250714104253.png]]
After all access has been blocked, the next two Directory sections relax
the access restrictions on two specific directories
![[Pasted image 20250714104315.png]]
The third Directory section adds an additional option to the html
directory within the document root:
![[Pasted image 20250714104337.png]]
This Options directive specifies two options that apply to the html
directory and all of its subdirectories:
- Indexes: Tells Apache that if a URL specifies a directory but not a file within the directory and an index.html file does not exist in the directory, Apache should display a formatted listing of the files in the directory.
- FollowSymLinks: Tells Apache to follow symbolic links (shortcuts in Windows terminology) within the directories.
The FollowSymLinks is enabled by default
The net effect of these access rules is as follows : 
- For all files in the /var/www/html directory and any of its subdirectories, anyone can access the files and if a URL names a directory but not a file and no index.html file is present, a directory listing will be presented.
- For all files in /var/www, full access is granted but the directory listing is never shown, even if there is no filename in the URL.
- Access to all other files in all other directories within the server's file system is prohibited.
==TIP==
	In addition to index.html, you can use the DirectoryIndex directive to change the name of the default index file for a directory. For example, if you'd prefer to use index.htm, use this directive:
	![[Pasted image 20250714104553.png]]

==TIP==
	There's one other trick you should know about controlling access to your web server: You can restrict access to a certain range of IP addresses. This is a brilliant idea if your server is hosting a company intranet that you want accessible to anyone within your network but to no one outside of it. You can list an IP address range on a Require directive like this:
	![[Pasted image 20250714104632.png]]
To block a specific Ip address from access like this
![[Pasted image 20250714104659.png]]
## Configuring Virtual Hosts
A virtual host is simply a website with its own domain name hosted by an Apache Server
By default, Apache is set up to server just one virtual host
Before you set up a virtual host, you should first add the names of the
virtual host site to your DNS. Each virtual host should have an A record
that points to the IP address of the web server. For example:
![[Pasted image 20250714104804.png]]
To make that work, you need to set up a virtual host for each of the sites. You can easily do this by creating a .conf file in the
/etc/httpd/conf.d directory.
![[Pasted image 20250714104848.png]]
I also created a directory /var/www/html/haunt and put a single HTML
file named index.html in it. Here's the index.html file:
![[Pasted image 20250714104905.png]]
Before restarting the web server, it's a good idea to run a check on the
configuration changes you’ve made. To do that, enter the following
command:
![[Pasted image 20250714104922.png]]
