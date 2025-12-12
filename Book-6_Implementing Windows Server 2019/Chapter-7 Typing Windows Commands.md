==TIP==
	Windows Server 2019 also includes an alternative command environment known as PowerShell. PowerShell is an advanced command processor that has many sophisticated features that are designed especially for creating powerful scripts
# Using Command window
To open cmd in windows follow these steps
1. Press the window key on your keyboard and then type cmd
2. Press the enter key
   ![[Pasted image 20250710184738.png]]
==TIP==
	To exit the command prompt, type Exit, and press Enter. This action properly terminates cmd.exe and closes the command prompt window. If you try to close the command prompt window by clicking its Close button, Windows is forced to shut down cmd.exe. The process works, but you have to click your way through an intervening dialog box and wait a few seconds while Windows terminates cmd.exe. Entering the Exit command is a much faster method.
==TIP==
	Sometimes it's helpful to open a command prompt in elevated mode, which means that you have full administrative privileges while in the prompt window. To do that, click Start and type cmd; then right-click the Command Prompt icon and choose Run As Administrator.
### Editing Commands
There are several built-in editing features that can simplify the task of correcting a mistaken command or entering a sequence of similar commands : 
- Press the right-arrow key to recall the text of the last command that you entered, one letter at a time. When you get to the spot where the new command should differ from the previous command, start typing.
- Press F3 to recall all the previous commands from the current cursor position to the end of the line.
- If you want to repeat a command that you’ve used recently, press the up-arrow key. This action recalls up to 50 of the most recently executed commands. You can press Enter to execute a command as is, or you can edit the command before you execute it.
### Using the Control menu
The commands found on this menu for all windows, this includes three additional commands : 
- Edit: The Edit command leads to a submenu with several choices. Several of these commands work together so that you can copy information from the command window to the clipboard, and vice versa. If you choose Edit⇒ Mark, you’re placed in a special editing mode that lets you highlight text in the command window with the mouse. (Normally, the mouse doesn’t do anything in the command window.) Then you can choose Edit⇒ Copy or just press Enter to copy the text that you selected to the clipboard.
  You can also use the Edit menu to paste text from the clipboard, to scroll the window, and to search the window for text.
- Default: This command lets you set default properties for the command window.
- Properties: This command displays a Properties dialog box that you can use to change the appearance of the window. You can change the font size, choose background colors, and make other adjustments to make the command window look good on your computer.
## Special Command Tricks
These techniques can let you accomplish in a single command what would otherwise taken dozens of separate commands
#### Wildcards
To delete a file using command line enter
del * *file name* *  extension
An asterisk stands for any number of characters, including zero and an exclamation point stands for just one character
#### Chaining Commands
You can enter two or more commands on the same line by separating commands with an ampersand (&)
![[Pasted image 20250710190655.png]]
This command copies all the .doc files to the A: drive. Then the del command deletes the .doc files
Now here in this command it's a catch what if A drive gets fills up and don't have the space to copy doc files. So in this situation 2nd command will get executed and will be deleted.
So for a safer alternative is that
Telling windows to execute the second command only if the first command finishes successfully : 
![[Pasted image 20250710190904.png]]
Now here the del command will be executed only if the copy command succeeds
we can also use two pipe characters to execute the second command only if the first command fails 
![[Pasted image 20250710190950.png]]
Displays the message oops! if the copy command fails 
We can use parentheses to group commands 
![[Pasted image 20250710191052.png]]
Here the files are copied and then deleted if the copy was successful.
If either command fails, the message is displayed
#### Redirection and Piping
Redirection lets you specify an alternative destination for output that will be displayed by  a command or an alternative source for input that should be fed into a command
You can save the results of an ipconfig/all command to a file name myconfig.txt like this
	`ipconfig/all > myconfig.txt`
Here the greater-than sign (>) is used to redirect the command's console output
	`nslookup < lookup.txt`
To run this command you need to create a lookup.txt file
Piping takes the console output from one command and feeds it into the next command as input
Piping is often used with special commands called filters
Which are designed to read input from the console, modify the data in some way and then write it to the console
To display the content info into alphabetical order use type commands with a filer sort like this
![[Pasted image 20250710192533.png]]
The vertical bar is often called the pipe character because it's the symbol used to indicate piping
#### Environment variables
Environment variables all begin and end with percent signs.
You can use an environment variable anywhere in a command
![[Pasted image 20250710192729.png]]
OUTPUT IS 
![[Pasted image 20250710192736.png]]
If the environment variable represents a path, you may need to enclose it in quotation marks, like this 
![[Pasted image 20250710193042.png]]
This command displays the contents of the user's home directory
The quotation marks are required here because the environment variable expands to a pathname that may include spaces and the command shell requires that long filenames that include spaces be enclosed in quotation marks
ENVIRONMENT VARIABLES
![[Pasted image 20250710193151.png]]
![[Pasted image 20250710194838.png]]
#### Batch files
A batch files is simply a text file that contains one or more command
Batch files are given the extension .bat and can be run from a command prompt
Some examples of simple batch files : 
- I once used a one-line file to copy the entire contents of an important shared network drive to a user’s computer every night at 10 p.m. The user wanted a quick-and-dirty backup solution that would complement the regular tape backups that ran every night.
- I’ve also used a pair of short batch files to stop and then restart an Exchange server before and after nightly backups.
- If I frequently need to work with several related folders at the same time, I create a short batch file that opens Explorer windows for each of the folders. (You can open an Explorer window from a batch file simply by typing the path to the folder that you want to open as a command.) Then I place the batch file on my desktop so that I can get to it quickly.
# The EventCreate Command
It lets you create an event that's added to one of the Windows event logs.
This command can be useful if you want to make a note of something unusual that's happened
It's often used in batch files 
basic Syntax : 
![[Pasted image 20250710195238.png]]
Here's a description of the options : 
- /T: Specifies the type. The options are Information, Warning, and Error.
- /D: Provides a descriptive message that's saved in the log. Use quotes if the message contains more than one word.
- /ID: A number from 1 to 1,000.
- /L: The name of the log to write the event to. The default is Application.
- /SO: A string that represents the source of the event. The default is EventCreate. If you specify this option, you must also specify the /L option.
- /S: The name of the system on which the event should be recorded.
- /U: The user account to use when logging the event. You can specify this option only if you also specify /S.
- /P: The password. You can specify this option only if you also specify /U.
Example that writes an informational message to the application log 
![[Pasted image 20250710195426.png]]
OUTPUT OF THIS COMMAND
![[Pasted image 20250710195432.png]]
# Net Commands
Few details about the net commands : 
- You can get a quick list of the available Net commands by typing net /? at a command prompt.
- You can get brief help for any Net command by typing net help command. To display help for the Net Use command, for example, type net help use. (Yes, we all could use some help.)
- Many of the Net commands prompt you for confirmation before completing an operation.
### The Net accounts command
This command update user account policies for password requirements 
Command syntax is 
![[Pasted image 20250710195742.png]]
Description of the above command
- forcelogoff: Specifies how long to wait before forcing a user off the system when the user's logon time expires. The default value, no, prevents users from being forced to log off. If you specify a number, the user will be warned a few minutes before being forcibly logged off.
- minpwlen: Specifies the minimum length for the user's password. Length can be 0 through 127. The default is 6.
- maxpwage: Specifies the number of days a user's password is considered to be valid. Unlimited means that the password will never expire. Days can be from 1 through 49,710, which is about 135 years. The default is 90.
- minpwage: Specifies the minimum number of days after a user changes a password before the user can change it again. The default value is 0. You usually should set this value to 1 day to prevent users from bypassing the Uniquepw policy.
- uniquepw: Indicates how many different passwords the user must use before he or she is allowed to reuse the same password. The default setting is 5. The range is 0 through 24. domain: Specifies that the operation should be performed on the primary domain controller rather than on the local computer.
If you enter net accounts without parameters, the command simply displays the current policy settings
Example that sets the min and max password ages : 
![[Pasted image 20250710195920.png]]
### The Net computer command
This command creates or deletes a computer account
![[Pasted image 20250710204222.png]]
Description of the above command
- Computername : Specifies the computer to add or delete
- add : Creates a computer account for the specified computer
- del : Deletes the specified computer account
![[Pasted image 20250710204338.png]]
### The Net config command
This command lets you view or configure various network services
![[Pasted image 20250710204458.png]]
To configure server settings, use the syntax
![[Pasted image 20250710204510.png]]
Description of the above command
- Server : Lets you display and configure the server service while it's running
- Workstation : Let you display and configure the workstation service while it's running
- autodisconnect: Specifies how long a user's session can be inactive before it's disconnected. Specify –1 to never disconnect. The range is –1 to 65,535 minutes, which is about 45 days. The default is 15 minutes.
- srvcomment: Specifies a description of the server. The comment can be up to 48 characters long and should be enclosed in quotation marks.
- hidden: Specifies whether the server appears in screens that display available servers. Hiding a server doesn't make the server unavailable; it just means that the user will have to know the name of the server to access it. The default is No.
EXAMPLE 
![[Pasted image 20250710204656.png]]
### The Net Continue command
This command continues a service you've suspended with the net pause command
Syntax is 
![[Pasted image 20250710204727.png]]
Here are some typical services that you can pause and continue
- Netlogon : The Net Logon Service
- Schedule : the Task scheduler service
- Server : The Server Service
- Workstation : The Workstation service
EXAMPLE
![[Pasted image 20250710204952.png]]
If the service name has embedded spaces, enclose the service name in quotation marks. This command continues the NT LM Security Support Provider service:
![[Pasted image 20250710205108.png]]
### The Net File command
This command lists all open shared files and the number of file locks placed on each file.
You can also use this command to close files and remove locks
Syntax 
![[Pasted image 20250710205158.png]]
Description of the above command
- Id : The file's identification number
- Close : Closes an open file and releases any lock that were placed on the file
To close an open files, first run net file without any parameters to list the open files
EXAMPLE
![[Pasted image 20250710205420.png]]
Next, run file again specifying the file number displayed for the file that you want to close.
To close the RECIPE.MFF file, for example use this command
![[Pasted image 20250710205500.png]]
### The Net group command
This commands lets you add, display or change global groups.
To display information about a group or to change a group's comment use this syntax
![[Pasted image 20250710205555.png]]
To create a new group use this syntax
![[Pasted image 20250710205603.png]]
To delete a group use this syntax
![[Pasted image 20250710205614.png]]
To add or remove users from a group, use this syntax
![[Pasted image 20250710205632.png]]
 Description of the above command
 - groupname: Specifies the name of the group to add, change, or delete. If you specify this parameter and no others, a list of users in the group appears.
- comment: Specifies a comment for the group. The comment can be up to 48 characters in length and should be enclosed in quotation marks.
- domain: Specifies that the operation should be performed on the primary domain controller rather than on the local computer.
- add: Creates a new group or adds users to an existing group. Before you add a user to a group, you must create a user account for the user.
- delete: Removes a group or removes users from the group. username: Specifies one or more usernames to be added to or removed from the group. If you list more than one name, separate the names with spaces.
==TIP==
	Windows isn't picky, you can specify net groups rather than net group if you want
EXAMPLE list all the groups on a server
![[Pasted image 20250710210054.png]]
To add a group named Admin
![[Pasted image 20250710210104.png]]
To adds three user to the admin group
![[Pasted image 20250710210123.png]]
To list the users in the admin group
![[Pasted image 20250710210132.png]]
### The Net help command
This command displays help for the net command or for a specific subcommand.
SYNTAX
![[Pasted image 20250710210206.png]]
The command parameters can be any of the following commands
![[Pasted image 20250710210222.png]]
==TIP==
	You can type net help services to display a list of services that you can start via the Net Start command
### The Net Helpmsg command
This command displays an explanation of network error codes
Syntax
![[Pasted image 20250710210320.png]]
Here the message# parameter should be the four-digit number displayed when the error occurred
If you get an error with message 2180,
Use this command
![[Pasted image 20250710210357.png]]
### The Net Localgroup command
This command lets you add, display or change local groups
To display information about a local group or to change a local group's comment, use this syntax
![[Pasted image 20250710210816.png]]To create a new group use this syntax
![[Pasted image 20250710210827.png]]
To delete a group, use this syntax
![[Pasted image 20250710210836.png]]
To add users to or remove users from a group, use this syntax
![[Pasted image 20250710210850.png]]
Description of the above commands
- groupname: Specifies the name of the group to add, change, or delete. If you specify this parameter and no others, a list of users in the group appears.
- comment: Specifies a comment for the group. The comment can be up to 48 characters in length and should be enclosed in quotation marks.
- domain: Specifies that the operation should be performed on the primary domain controller rather than on the local computer.
- add: Creates a new group or adds users to an existing group. Before you add a user to a group, you must create a user account for the user.
- delete: Removes a group or removes users from the group. username: Specifies one or more usernames to be added to or removed from the group. If you list more than one name, separate the names with spaces
To list all groups 
![[Pasted image 20250710210956.png]]
To add a local group named admin
![[Pasted image 20250710211126.png]]
To add three users to the admin local group
![[Pasted image 20250710211138.png]]
To list the users in the admin group
![[Pasted image 20250710211156.png]]
### The net Pause command
This command temporarily pauses a service
To reactivate the service later, use the net continue command
Syntax to pause a service is a
![[Pasted image 20250710211337.png]]
Here are some typical services that you can pause
- netlogon : The Net Logon service
- schedule : The Task Scheduler service
- server : The Server service
- Workstation : The workstation service
To pause the workstation service
![[Pasted image 20250710211442.png]]
If the service name has embedded spaces, enclose the service name in quotation marks. This command pauses the NT LM Security Support Provider service, for example:
![[Pasted image 20250710211456.png]]
### The Net Session command
This command lets you view current server connections and kick users off, if you feel inclined 
Syntax
![[Pasted image 20250710211543.png]]
Description of the above command
- Computername : Indicates which computer's session you want to view or disconnect. If you omit this parameter, all sessions are listed
- Delete : Disconnects the computer's session. Any open files are immediately closed. If you use this parameter without specifying a computer name, all computers currently connected to  server are disconnected
==WARNING==
	This command is an obviously dangerous one. If you disconnect users while they're updating files or before they have a chance to save their work, they'll be hopping mad.
To find out who is connected to a computer, use this command
![[Pasted image 20250710211736.png]]
### The Net Share command
This command lets you manage shared resources
To display information about all shares or a specific share, use this syntax
![[Pasted image 20250710211832.png]]
To create a new share, use this syntax
![[Pasted image 20250710211843.png]]
To change the properties of an existing share, use this syntax
![[Pasted image 20250710211857.png]]
To delete an existing share, use this syntax
![[Pasted image 20250710211905.png]]
Description of the above commands
- ShareName: Specifies the share name. Use this parameter by itself to display information about the share.
- path: Specifies the path to the folder to be shared. The path should include a drive letter. If the path includes spaces, enclose it in quotation marks.
- users: Specifies how many users can access the share concurrently.
- unlimited: Specifies that an unlimited number of users can access the share concurrently.
- remark: Creates a descriptive comment for the share. The comment should be enclosed in quotation marks.
- cache: Specifies the caching option for the share.
- delete: Stops sharing the folder.
If you use net share without any parameters 
![[Pasted image 20250710212023.png]]
Example that creates a share named docs
![[Pasted image 20250710212040.png]]
### The Net Start command
This command lets you start a networking service or display a lot of all the services that are currently running
![[Pasted image 20250710212119.png]]
To Stop the DNS server use the command
![[Pasted image 20250710212155.png]]
To restart the service use this command
![[Pasted image 20250710212209.png]]
### The Net Statistics command
This command lists the statistics log for the local workstation or server service
Syntax
![[Pasted image 20250710212250.png]]
If you use net statistics workstation, the following information appears : 
- The computer name
- The date and time when the statistics were last updated
- The number of bytes and server message blocks (SMB) received and transmitted
- The number of read and write operations that succeeded or failed
- The number of network errors
- The number of sessions that failed, disconnected, or were reconnected
- The number of connections to shared resources that succeeded or failed
if you use net Statistics server, the following information is listed
- The computer name
- The date and time when the statistics were last updated
- The number of sessions that have been started, disconnected automatically, and disconnected because of errors
- The number of kilobytes sent and received, and the average response time
- The number of password and permission errors and violations
- The number of times the shared files, printers, and communication devices were used
- The number of times the size of the memory buffer was exceeded
### The Net Stop command
This command lets you stop a networking service 
Syntax
![[Pasted image 20250710212555.png]]
### The Net time command
This command synchronizes the computer's clock with the clock on the another computer.,
To access a clock on another computer in the same domain or workgroup, use this form
![[Pasted image 20250710213609.png]]
To synchronize time with a domain, use this syntax
![[Pasted image 20250710213622.png]]
To use an RTS time server, use this syntax
![[Pasted image 20250710213633.png]]
To specify the computer to use for network time protocol, use this syntax
![[Pasted image 20250710213700.png]]
To set the computer's clock to match the Server01 clock, use this syntax
![[Pasted image 20250710213720.png]]
### The Net use command
This command connects to or disconnects from a shared resource on another computer and maps the resource to a drive letter.
Syntax
![[Pasted image 20250710213805.png]]
To set up a home directory, use this syntax
![[Pasted image 20250710213824.png]]
To Control whether connections should be persistent, use this syntax
![[Pasted image 20250710213846.png]]
Description of the above commands
- drive: Specifies the drive letter. (Note that for a printer, you should specify a printer device such as LPT1: here instead of a drive letter.) If you specify an asterisk, Windows will determine what drive letter to use.
- `\\computername\sharename`: Specifies the server and share name to connect to.
- password: Provides the password needed to access the shared resource. If you use an asterisk, you're prompted for the password.
- user: Specifies the username to use for the connection.
- savecred: Saves the credentials for reuse later if the user is prompted for a password.
- smartcard: Specifies that the connection should use a smart card for authorization.
- delete: Deletes the specified connection. If you specify an asterisk ( * ) , all network connections are canceled. persistent: Specifies whether connections should be persistent. home: Connects to the home directory.
To display all current connection type net use with no parameters
To create a persistent connection to a drive named Acct on a server named Server01, using drive K::
![[Pasted image 20250710214122.png]]
To drop the connection
![[Pasted image 20250710214130.png]]
### The Net User command
This command creates or changes user accounts
To display user's information, use this syntax
![[Pasted image 20250710214154.png]]
To update user information, use this syntax
![[Pasted image 20250710214241.png]]
To add a new user, use this form
![[Pasted image 20250710214250.png]]
To delete a user,  use this syntax
![[Pasted image 20250710214300.png]]
THE OPTIONS PARAMETERS
![[Pasted image 20250710214322.png]]![[Pasted image 20250710214334.png]]
To display information for a particular user, use this syntax
![[Pasted image 20250710214451.png]]
To add a user account for Theodore Cleaver with the username beaver use this syntax
![[Pasted image 20250710214512.png]]
### The Net View command
This command displays information about your network
If you use it without parameters, it displays a list of computers in your domain.
You can use parameters to display resources that are being shared by a particular computer 
Syntax
![[Pasted image 20250710214703.png]]
Description of the above commands
- Computername  : Specifies the computer whose shared resources you want to view
- domainname : Specifies the domain you want to view, if it's other than the current domain
Out from a net view command
![[Pasted image 20250710214751.png]]
## The RunAs Command
The runas command lets you run a program from a cmd by using the the credentials of another user account
Syntax
![[Pasted image 20250710214839.png]]
To run the Microsoft Management Console with the dom1 domain’s administrator account, for example, you can use this command:
![[Pasted image 20250710214851.png]]
Assuming that the username is valid, you’ll be prompted for the user’s password. Then the program will be run using the specified user’s account.
Some parameters that can be used with the Runas command : 
- /user: Specifies the domain and username. You can use either of two forms to specify the domain and username: domain\username or username@domain.
- /profile: Specifies that the user's profile should be loaded. (This option is on by default, so you don’t have to specify it explicitly.)
- /noprofile: Doesn’t load the user’s profile. Although this parameter can cause the application to load faster, it can also prevent some applications from functioning properly.
- /env: Uses the current environment instead of the user's.
- /netonly: Indicates that the user account isn’t valid in the current domain. (If you use /netonly, the username must be specified in the form domain\username; the username@domain form won't work.)
- /savecred: Saves the password so that it has to be entered only the first time the RunAs command is used.
==WARNING==
	Using the /savecred parameter is an extremely bad idea, as it creates a gaping security hole. In short, after you've used /savecred, any user at the computer can use the RunAs command to run any program with administrator privileges.
# - /smartcard: Specifies that the user’s credentials will be supplied by a smart card device.
  (
  Run this program as another user, and use the credentials provided by a smart card to authenticate that user.
  )
