# Command Shell Basics
A shell is a program that accepts commands from a command prompt and executes them.
==TIP==
	Linux commands are case sensitive, so be careful about capitalization when you type Linux Commands
### Getting to a shell
You can also remotely access a shell using a TTY program such as PuTTY
==WARNING==
	For normal Linux users, the command shell prompt character is a dollar sign ($). If you see a hash mark (#) as the prompt character, it means you're logged on as root. Whenever you see a hash prompt, you should be extra careful about what you do because you can easily get yourself into trouble by deleting important files or otherwise corrupting the system.
### Editing Commands
Linux shells have a several built-in editing features that can simplify the task of correcting a mistaken command or entering a sequence of similar commands
- Repeat : If you want to repeat a command that you've used recently, press the up-arrow key. You can also press the up-arrow key multiple times to scroll back through your recent commands, and if you overshoot the command you want to repeat, you can use the down-arrow key to scroll forward
- Cursor Movement : You can use the Home and End keys to move to the beginning and ending of a line. Alternatively, you can press Ctrl+A to move to the start of a line and Ctrl+E to move to the end of a line. You can also press Alt+F to move forward one word at a time and Alt+B to move backward one word at a time.
- Clear the screen : Press Ctrl + L to clear the screen
### Wildcards
Wildcards are one of the most powerful features of command shells.
With wildcards, you can process all the files that match a particular naming pattern with a single command
 You can use two basic wildcard characters. An asterisk ( * ) stands for any number of characters, including zero, and an exclamation mark (!)
stands for just one character. 
Thus, !Text.doc matches files with names like aText.doc, xText.doc, and 4Text.doc, but not abcText.doc or just Text.doc. However, * Text.doc matches any of those filenames.
You can also use brackets to indicate a range of characters to choose from.
For example, report[123] matches the files report1, report2, or report3. You can also specify report[1-5] to match report1, report2, report3, report4, or report5. The wildcard r[aeiou]port matches files named raport, report, riport, roport, or ruport.
### Redirection and piping
Redirection lets you specify an alternative destination for output that will be displayed by a command or specify an alternative source for input that should be fed into a command.
For example, you can save the results of an ifconfig command to /home/doug/myconfig like this:![[Pasted image 20250714184114.png]]
Here the greater-than sign(>) is used to redirect the command's console output
You can use two greater-than signs (>>) to redirect output to an existing
file, writing the redirected output to the end of the file. For example:
![[Pasted image 20250714184144.png]]
Piping is a similar technique. It takes the console output from one
command and feeds it into the next command as input.
One of the most common uses of piping is to send the output of a command that displays a lot of information to the more program, which displays the output one page at a time.
For example
![[Pasted image 20250714184237.png]]
### Environment Variables
An environment variable is a predefines value you can use in  your commands to provide commonly used information, such as the name of the current user or the operating system version
You can use an environment variable anywhere in a command by typing $ (dollar sign) followed by the environment variable name.
For example
![[Pasted image 20250714184351.png]]
Output will be this 
![[Pasted image 20250714184358.png]]
ENVIRONMENT VARIABLES
![[Pasted image 20250714184414.png]]
### Shell Scripts
A shell script is simply a text file that contains one or more commands which you can execute in sequence by running the script
==TIP==
	You can create shell scripts by using any text editor. One of the easiest editors is nano, which you can invoke from a shell prompt. But if you want to be a real Linux guru, take a few moments to learn how to use Vi, a powerful text-mode editor. To create or edit a file in Vi, type the command vi followed by a filename.
After you create a shell script you have to grant yourself execute permission to run the script
For example, to grant yourself permission to run a script named myscript use this command
![[Pasted image 20250714184617.png]]
To run a shell script, you can use the sh command and provide the name of the script file. For example : 
![[Pasted image 20250714184638.png]]
### Running a command with root-level privileges
Many Linux commands perform actions that can only be done by the
root user. 
To avoid the need to switch back and forth between your normal user account and the root user account, you can use the sudo command to perform any command using root-level permissions.
To do so, just prefix the command you want to execute with the word sudo.
For example:
![[Pasted image 20250714184722.png]]
## Directory- and File-Handling commands
Because much of Linux administration involves working with configuration files, you frequently need to use the basic directory- and file-handling commands
#### The pwd command
This command display the current directory, which is called the present working directory 
Syntax
![[Pasted image 20250714184827.png]]
Output
![[Pasted image 20250714184832.png]]
#### The cd command
The cd command changes the current working directory
Syntax
![[Pasted image 20250714184854.png]]
You may want to follow the cd command with a pwd command to make
sure that you changed to the right directory. 
For example:
![[Pasted image 20250714184916.png]]
To change to a subdirectory of the current directory, omit the leading slash from the directory name. For example : 
![[Pasted image 20250714184934.png]]
You can also use the double-dot (..) to represent the parent of the
current directory. Thus, to move up one level, use the command cd ..
![[Pasted image 20250714184952.png]]
#### The mkdir command
To create a new directory, use the mkdir command
Syntax
![[Pasted image 20250714185008.png]]
#### The rmdir command
The rmdir command removes a directory. 
Syntax
![[Pasted image 20250714185033.png]]
The directory must be empty to be removes, so you have to first delete any files in the directory
#### The ls command
The ls command lists the contents of the current directory
Sntax
![[Pasted image 20250714185109.png]]
Most important [options] for the ls command ; 
- -a: Lists all the files in the directory, including files that start with a period
- -c: Sorts entries by the time the files were last modified
- -d: Lists only directory names
- -l: Displays in long format
- -r: Displays files in reverse order
- -R: Lists the contents of all subdirectories, and subdirectories of subdirectories, and subdirectories of subdirectories of subdirectories; in other words, lists subdirectories recursively
- -s: Displays file sizes
- -S: Sorts files by size
- -t: Sorts files by timestamp.
- -u: Sorts files by the time the files were last accessed.
- -X: Sorts files by their extensions.
You can limit the display to certain files by typing a filename, which can include wildcards
For example :
![[Pasted image 20250714185339.png]]
You can also specify the directory that you want to display , like this
![[Pasted image 20250714185353.png]]
To display detailed information about the files in the directory, use the -l switch
For example : 
![[Pasted image 20250714185419.png]]
#### The cp command
The cp command copies files
Syntax
![[Pasted image 20250714185437.png]]
Most important [options] for the cp command : 
- -a: The same as -dpR.
- -b: Makes backup copies of existing files before they're overwritten. Sounds like a good plan to me.
- -d: Copies links rather than the files the links point to.
- -f: Removes files that will be overwritten.
- -i: Interactively prompts for each file to be overwritten.
- -l: Creates links to files rather than actually copying file contents.
- -p: Preserves ownership and permissions.
- -R: Copies the contents of subdirectories recursively.
- -s: Creates symbolic links to files rather than actually copying file contents.
- -u: Replaces destination files only if the source file is newer.
To make a copy of a file within the same directory, use cp like this
![[Pasted image 20250714185815.png]]
If you want to copy a file to another directory without changing the filename, use the cp like this
![[Pasted image 20250714185843.png]]
You can use wildcards to copy multiple files
![[Pasted image 20250714185856.png]]
To include files in subdirectories of the source file, use the -R switch like this
![[Pasted image 20250714185921.png]]
#### The rm command
The rm command deletes files
Syntax
![[Pasted image 20250714185942.png]]
The [options] for rm commands are  : 
- -f: Removes files that will be overwritten
- -i: Interactively prompts for each file to be overwritten
- -R: Copies the contents of subdirectories recursively
To delete a single file,  use it like this 
![[Pasted image 20250714190020.png]]
To delete multiple files, use a wildcard like this
![[Pasted image 20250714190038.png]]
To delete an entire directory, use the -r switch
![[Pasted image 20250714190047.png]]
#### The mv command
The mv command moves files or renames them
Syntax
![[Pasted image 20250714190142.png]]
The [options] for mv command are :
- -b: Makes backup copies of existing files before they're overwritten. Still sounds like a good plan to me.
- -f: Removes files that will be overwritten.
- -i: Interactively prompts for each file to be overwritten.
- -u: Replaces destination files only if the source file is newer.
To move a file to another directory, provide a filename for the first
argument and a directory for the second, like this
![[Pasted image 20250714190253.png]]
To rename a file, provide filenames for both arguments
![[Pasted image 20250714190305.png]]
#### The touch command
The touch command is one of the most interesting Linux file management console.
Syntax
![[Pasted image 20250714190325.png]]
The [options] for touch command are : 
- -a: Changes the access time only
- -c: Doesn't create files that don't exist
- -m: Changes the modification time only
The basic form of the touch command look like this
![[Pasted image 20250714190407.png]]
If you use touch on an existing file, the touch command changes the modification date of the file
If you use it on a command that doesn't exist, the touch command creates a new empty file
#### The cat command
The cat command displays the contents of a file
Syntax
![[Pasted image 20250714190642.png]]
The [options] for the cat command are : 
- A: Displays new line characters as $, tab characters as ^I, and control characters with a caret (^)
- -b: Numbers all nonblank lines as they're displayed
- -e: Displays new line characters as $ and control characters with a caret (^)
- -E: Displays new line characters as $
- -n: Numbers lines as they are displayed
- -s: Squeezes multiple spaces down to a single space
- -t: Displays tab characters as ^I and control characters with a caret (^)
- -T: Displays tab characters as ^I
- -v: Shows nonprinting control characters with a caret (^)
(![[Pasted image 20250714191005.png]])
Press Ctrl+D. This signals the end of the input to the cat command
## Commands for Working With Packages and Services
As a Linux administrator, you frequently need to start and stop services and check the status of installed packages or install new packages
#### The service command
You use the service command to check the status of services and to start, stop or restart services
Syntax
![[Pasted image 20250714191810.png]]
Typical uses of the service command
- To check the status of the httpd service (Apache), use this command
  ![[Pasted image 20250714191844.png]]
- To stop the httpd service
  ![[Pasted image 20250714191851.png]]
- To start the httpd service
  ![[Pasted image 20250714191856.png]]
- To restart the httpd service
  ![[Pasted image 20250714191902.png]]
To display the status of all services , use this command
![[Pasted image 20250714191927.png]]
COMMON LINUX SERVICES
![[Pasted image 20250714191943.png]]
![[Pasted image 20250714191948.png]]
#### The yum and dnf commands
yum, which stands for Yellowdog Updater Modified, is a tool for
installing and updating packages on a Linux system.
Note that installing a package is an action that requires root-level
permissions to perform, so you'll usually use dnf or yum along with the
sudo command, like this:
![[Pasted image 20250714192320.png]]
## Commands for Administering Users
Now we will learn how to create and manage user accounts from a command shell
==TIP==
	You should log on as root to perform these tasks
#### The useradd command
The useradd command creates a user account. 
Syntax
![[Pasted image 20250714192416.png]]
You can also use this command to change the default options for new users
Syntax
![[Pasted image 20250714192442.png]]
If you use -D with no options, a list of current default settings will be shown
The [options] for useradd command are : 
- -c comment: Typically the user's full name
- -d home-dir: The home directory of the new user
- -e date: The expiration date for the user
- -f time: The number of days between logons before the user is considered expired
- -g group: The initial logon group for the user
- -G groups: Additional groups the user should belong to
- -m: Creates the new user's home directory if it doesn't exist already
- -s shell-path: Specifies the user's logon shell
This option is valid only with -D (Which sets a default option) : 
- -b base -dir: Provides the default base directory if a home directory is not specified
The useradd command creates a user with default option settings
To command that specifies the user's full name in the comment option:
![[Pasted image 20250714192756.png]]
This command creates a temporary account named ghost that expires on Halloween 2016
![[Pasted image 20250714192821.png]]
If you want to see what the default values are for account options, use the -D option without any other parameter
![[Pasted image 20250714192848 1.png]]
#### The usermod command
The usermod command modifies an existing user
Syntax
![[Pasted image 20250714203744.png]]
The [options] for this command are : 
- -c comment: Typically the user's full name
- -d home-dir: The home directory of the new user
- -e date: The expiration date for a logon
- -f time: The number of days between logons before the user is considered expired
- -g group: The initial logon group for the user
- -G groups: Additional groups the user should belong to
- -m: Creates the new user's home directory if it doesn’t exist already
- -s shell-path: Specifies the user's logon shell
- -l: Locks an account
- -u: Unlocks an account
Here's an example that changes a user's full name : 
![[Pasted image 20250714204349.png]]
#### The userdel command
The userdel command deletes a user.
Syntax
![[Pasted image 20250714204409.png]]
If you specify -r, the user's home directory is deleted along with the account
#### The chage command
The chage command modifies date policies for a user's password
Syntax
![[Pasted image 20250714204553.png]]
The [options] for this command are : 
- -m days : Specifies the minimum number of days allowed between password changes.
- -M days: Specifies the maximum number of days allowed between password changes.
- -d date: The date of the last password change.
- -E date: The date on which the account will expire.
- -W days: The number of days prior to the password expiring that the user will be warned the password is about to expire.
- -I days: The number of days of inactivity after the password has expired that the account is locked out. Specify 0 to disable this feature.
Example that sets an account to expire on Halloween 2024
![[Pasted image 20250714204720.png]]
==TIP==
	If you specify a username but no other options, you're prompted to enter each option. This is a lot easier than trying to remember all the switches
#### The passwd command
The passwd command changes the password for a user account
Syntax 
![[Pasted image 20250714204823.png]]
If you don't supply a user, the password for the current user is changed
#### The newusers command
The newusers command provides an easy way to create a group of new
user accounts.
It reads a text file that contains one line for each new user, listing the user's name and password.
Syntax
![[Pasted image 20250714204917.png]]
If you omit the filename, newusers accepts input from the console
Suppose that you have a file named /root/island.users that contains
these lines:
![[Pasted image 20250714204956.png]]
You can then create these seven standard user account by issuing this command
![[Pasted image 20250714205015.png]]
==WARNING==
	Because the newusers file contains unencrypted passwords, you shouldn't leave it lying around. Require these new users to change their passwords immediately and delete the file you used to create the users.
#### The groupadd command
The groupadd command creates a new group
Syntax
![[Pasted image 20250714205044.png]]
Although you have several possible options to use, the only one you're
likely to need is -r, which creates a system group that has special
privileges.
To administer the group, you use the gpasswd command
#### The groupdel command
The groupdel command deletes a group
Syntax
![[Pasted image 20250714205134.png]]
#### The gpasswd command
You use the gpasswd command to administer a group
To change the group password : 
![[Pasted image 20250714205204.png]]
To add a user
![[Pasted image 20250714205209.png]]
To remove a user
![[Pasted image 20250714205216.png]]
To create group administrators and/or members : 
![[Pasted image 20250714205228.png]]
The [options] for the above command are  : 
- -r: Removes the password from the group.
- -R: Disables access to the group via the newgrp command.
- -a: Adds the specified user to the group.
- -d: Deletes the specified user from the group.
- -A: Specifies one or more group administrators. Use commas with no intervening spaces to separate the administrators from each other. Each administrator must be an existing user.
- -M: Specifies one or more group members. Use commas with no intervening spaces to separate the members from each other. Each member must be an existing user.
Here's an example of adding seven group members and one administrator to a group called castways  :
![[Pasted image 20250714205412.png]]
If the rest of the group finally decides to throw Gilligan off the island,
they can remove him from the group with this command:
![[Pasted image 20250714205448.png]]
# Commands for Managing Ownership and Permissions
This section presents the details of the chown and chmod commands,
which are the essential tools for assigning file system rights in the Linux
environment.
### The chown command
The chown command changes the owner of a file 
Syntax
![[Pasted image 20250714205540.png]]
### The chgrp command
To change the group ownership use chgrp command 
Syntax
![[Pasted image 20250714205732.png]]
### The chmod command
The chmod command lets you change the permission for a Linux file
Linux grants three different types of permissions 
- read 
- write 
- execute
For three different scopes
- owner
- group
- everyone
That's a total of 9 permissions
The nine letters are the nine permission, in this order :
- Read, write, execute for the owner
- Read, write, execute for the group
- Read, write, execute for everyone
The letters r, w, or x appear if the permission has been granted. If the
permission is denied, a hyphen appears.
For example, suppose the ls -l command lists these permissions
![[Pasted image 20250714210005.png]]
So description of this is :
- The first hyphen indicates that this is a file, not a directory.
- The next three positions are rw-. Therefore, the owner has read and write permission on this file, but not execute permission.
- The next three positions are r--. That means the group owner has read permissions but not write or execute permission.
- The last three positions are also r--. That means that everyone else has read permission but not write or execute permission.
The full syntax of the chmod command is pretty complex
However, you can do most of what you need to do with this form
![[Pasted image 20250714210109.png]]
For example, to grant read and write permission for the user to a file named rescue.plans, use this command:
![[Pasted image 20250714210134.png]]
You can also combine specification like this
![[Pasted image 20250714210149.png]]
To revoke all rights for the user, group, or others, don't type anything
after the equal sign. For example, this command revokes all rights for
others:
![[Pasted image 20250714210203.png]]
## Networking commands
#### The hostname command
The hostname command simply displays the computer's host name. 
Syntax
![[Pasted image 20250714210755.png]]
if you use this command without any parameters. the computer's host name is displayed
If you specify a name, the computer's host name is change to the name you specify
#### The ifconfig command
ifconfig displays and sets configuration options for network interfaces
So you'll use ifconfig mostly to display network configuration settings
Syntax
![[Pasted image 20250714210912.png]]
Here are the options that you can use on the ifconfig command : 
- interface: The symbolic name for your network adapter. It's typically eth0 for the first Ethernet adapter or eth1 for the second adapter.
- address: The IP address you want to assign to the interface, such as 192.168.1.100.
- netmask: The subnet mask to use, such as 255.255.255.0.
- broadcast: The broadcast, which should be the highest address on the subnet. For example: 192.168.1.255.
If you enter ifconfig without any parameters, the ifconfig command displays the current status of your network adapters like this
![[Pasted image 20250714211019.png]]
To change the IP address of an adapte, use ifconfig like this
![[Pasted image 20250714211033.png]]
#### The netstat command
The netstat command lets you monitor just about every aspect of a Linux server's network functions
The two most common reasons to use netstat are 
- To display the routing table
- Display open TCP/IP connections
![[Pasted image 20250714211137.png]]
The output will be :
![[Pasted image 20250714211148.png]]
To display TCP/IP connections, use this syntax
![[Pasted image 20250714211201.png]]
The output will be : 
![[Pasted image 20250714211212.png]]
#### The ping command
The ping command is the basic troubleshooting tool for TCP/IP.
You use it to determine whether basic TCP/IP connectivity has been established between two computers
Syntax
![[Pasted image 20250714211306.png]]
The [options] for this command is :
- -c: The number of packets to send. If you omit this, ping continues to send packets until you interrupt it.
==WARNING==
	-d: Floods the network with packets, as many as 100 per second. Use with care!
- -i: Specifies how many seconds to wait between sending packets. The default is one second. If you're having intermittent connection problems, you may try letting ping run for a while with this option set to a higher value, such as 60, to send a packet every minute. 
- -R: Displays the route the packets take to get to the destination computer.
==TIP==
	ping will continue to ping the destination computer until you interrupt it by pressing Ctrl+Z.
#### The route command
The route command displays or modifies the computer's routing table
To add an entry to the routing table 
Use this syntax
![[Pasted image 20250714211532.png]]
To delete an entry use this syntax
![[Pasted image 20250714211541.png]]
The [options] for this command are :
- netmask mask: Specifies the subnet mask for this entry
- gw address: Specifies the gateway address for this entry
- dev if: Specifies an interface (such as eth0 or eth1) for this entry
To add a static route entry that sends packets intended for the 192.168.2.0 subnet to this router, use a command like this:
![[Pasted image 20250714211638.png]]
#### The traceroute command
The traceroute command displays a list of all the routers that a packet must go through to get from the local computer to a destination on the Internet
Each of these routers is a hop
If you're unable to connect to another computer, you can use traceroute to find out exactly where the problem is occurring
Syntax
![[Pasted image 20250714211745.png]]
Although several options are available for the traceroute command, the
one you’re most likely to use is -i, which lets you specify an interface.
This is useful if your computer has more than one network adapter.
{
What is a defining characteristic of a symbolic (or soft) link created with `ln -s`?
It will break if the original file is moved or deleted.
A symbolic link is just a pointer to a path. If the file at that path is removed, the link becomes a 'dangling' or broken link.
}