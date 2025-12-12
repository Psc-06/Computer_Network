# Understanding Windows User accounts
User accounts are among the basic tools for managing a windows server
#### Local accounts versus domain accounts
A local account Is a user account that's stored on a particular computer and applies only to that computer
Domain account is a user account that's stored by active directory and can be accessed from any computer that's part of the domain
Domain accounts are centrally managed
#### User account properties
The three most important account properties are :
- Username: A unique name that identifies the account. The user must enter the username when logging on to the network. The username is public information. In other words, other network users can (and often should) find out your username.
- Password: A secret word that must be entered to gain access to the account. You can set up Windows so that it enforces password policies, such as the minimum length of the password, whether the password must contain a mixture of letters and numerals, and how long the password remains current before the user must change it.
- Group membership: The group or groups to which the user account belongs. Group memberships are the key to granting access rights to users so that they can access various network resources, such as file shares or printers, or perform certain network tasks, such as creating new user accounts or backing up the server.
## Creating a New User
To create a new domain user follow these steps
1. Choose Start => Windows administrative Tools => Active directory users and computers
	![[Pasted image 20250709223358.png]]
2. Right click the organization unit that you want to add the user to and then choose New => User
	![[Pasted image 20250709223422.png]]
3. Type the user's first name, middle initial and last name
4. Change the Full name field if you want it to appear different from what the wizard proposes
5. Type the user logon name
6. Click Next
	![[Pasted image 20250709223515.png]]
7. Type the password twice
8. Specify the password options that you want to apply
	The following options are available
	- User Must change password at next logon
	- User cannot change password
	- Password never expires
	- account is disabled
9. Click next
	![[Pasted image 20250709223611.png]]
10. Verify that the information is correct and then click finish to create the account
==TIP==
	An alternate way to create a new user is to simply copy an existing user. When you copy an existing user, you provide a new username and password and Windows copies all the other property settings from the existing user to the new user.
# Setting User Properties
To set additional properties for the user  to do that
Right click the new user and choose properties from the contextual menu
![[Pasted image 20250709223744.png]]
#### Changing the user's contact information
Several tables of the user properties dialog box contain information for the user : 
- Address: Lets you change the user’s street address, post office box, city, state, zip code, and so on
- Telephones: Lets you specify the user’s phone numbers
- Organization: Lets you record the user’s job title and the name of his or her boss
#### Setting account options
![[Pasted image 20250709223911.png]]
The following account options are available in the account options list box : 
- User Must Change Password at Next Logon: This option, which is selected by default, allows you to create a one-time-only password that can get the user started with the network. The first time the user logs on to the network, he or she is asked to change the password.
- User Cannot Change Password: Use this option if you don’t want to allow users to change their passwords. (Obviously, you can’t use this option and the preceding one at the same time.)
- Password Never Expires: Use this option if you want to bypass the password-expiration policy for this user so that the user will never have to change his or her password.
- Store Password Using Reversible Encryption: This option stores passwords by using an encryption scheme that hackers can easily break, so you should avoid it like the plague.
- Account Is Disabled: This option allows you to create an account that you don’t yet need. As long as the account remains disabled, the user won’t be able to log on.
- Smart Card Is Required for Interactive Logon: If the user’s computer has a smart card reader to read security cards automatically, check this option to require the user to use it.
- Account Is Trusted for Delegation: This option indicates that the account is trustworthy and can set up delegations (means to give responsibility). This advanced feature usually is reserved for Administrator accounts.
- Account Is Sensitive and Cannot Be Delegated: This option prevents other users from impersonating this account.
- Use DES Encryption Types for This Account: This option beefs up the encryption for applications that require extra security.
- Do Not Require Kerberos Preauthentication: Select this option if you use a different implementation of the Kerberos protocol
#### Specifying Logon Hours
You can restrict the hours during which the user is allowed to log on to the system by clicking the logon hours button on the account tab of the user properties dialog box
![[Pasted image 20250709224406.png]]
Initially, the Logon Hours dialog box is set to allow the user to log on at any time of day or night. 
To change the hours that you want the user to have access, click a day and time or a range of days and times; choose either Logon Permitted or Logon Denied; and click OK.
#### Restricting access to certain computers
You can restrict a user to certain computers, however by clicking the Log On To button on the account tab of the user properties dialog box
![[Pasted image 20250709224516.png]]
To restrict the user to certain computers, select the radio button labeled The Following Computers. Then, for each computer you want to allow the user to log on from, type the computer’s name in the text box, and click Add.
#### Setting the user's profile information
![[Pasted image 20250709224551.png]]
It lets you configure three bits of information related to the user's profile
- Profile Path : This field specifies the location of the user's roaming profile
- Logon Script :  This field is the name of the user's logon script
  A logon script is a batch file that's run whenever the user logs on. The main purpose of the logon script is to map the network shares that the user requires access to
- Home folder : This section is where you specify the default storage location for the user
==TIP==
	The profile tab lets you specify the location of an existing profile for the user, but it doesn't actually let you set up the profile
## Resetting User password
The procedure to reset the password for a user domain account are : 
1. Log on as an administrator
2. In Server manager , choose Tools => Active Directory Users and Computers
3. Drill down to the organizational unit that contains the user's Active Directory object
4. In the details pane, right-click the user who forgot his or her password, and choose reset password from the contextual menu
5. Type the new password in both password boxes
6. If desired, select the user must change password at next logon option
7. Click Ok
# Disabling and Enabling User Accounts
If you want to temporarily prevent a user from accessing the network, you can disable his or her account. Then you can enable the account later, when you’re ready to restore the user to full access.
Here’s the procedure:
1. log on as an administrator
2. From server manager, choose tools => Active directory users and computers
3. Drill down to the organizational unit that contains the user's active directory object
4. In the Details pane, right click the user that you want to enable or disable, then choose either enable account or disable account from the contextual menu to enable or disable the user
## Deleting a User
To delete a user account follow these steps
1. Log on as an administrator
2. Choose start => Administrative Tools => Active Directory Users and Computers
3. Drill down to the organizational unit that contains the user's active directory object
4. In the details pane, right-click the user that you want to delete and then choose delete from the contextual menu
5. Click Yes
==WARNING==
	Deleting a user account is a permanent, nonreversible action. Do it only if you’re absolutely sure that you’ll never want to restore the user’s account. If there’s any possibility of restoring the account later, you should disable the account rather than delete it.
# Working with groups
A group is a special type of account that represents a set of users who have common network access needs
### Group Types
Two distinct types of groups exist : 
- Security groups: Most groups are security groups, which extend access rights to members of the group. If you want to allow a group of users to access your high-speed color laser printer, for example, you can create a group called ColorPrintUsers. Then you can grant permission to use the printer to the ColorPrintUsers group. Finally, you can add individual users to the ColorPrintUsers group.
- Distribution groups: Distribution groups aren’t used as much as security groups are. They’re designed as a way to send email to a group of users by specifying the group as the recipient.
### Group Scope
It can have three distinct scopes and that are : 
- Domain local: A group with domain local scope can have members from any domain. The group can be granted permissions only from the domain in which the group is defined, however.
- Global: A group with global scope can have members only from the domain in which the group is defined. The group can be granted permissions in any domain in the forest, however.
- Universal scope: Groups with universal scope are available in all domains that belong to the same forest.
One common ways you can use domain local and global groups is as follows : 
1. Use domain local groups to assign access right for network resources
2. Use global groups to associate users with common network access needs
3. Finally, add the global group to the domain local group
### Default groups
DEFAULT GROUPS![[Pasted image 20250709225905.png]]
DEFAULT GROUPS LOCATED IN THE USERS CONTAINER
![[Pasted image 20250709225926.png]]
#### Creating a group
To create a group follow these steps
1. Log on as an adminstrator
2. From server manager, choose Tools => Active directory users and computers
3. Right-Click the domain to which you want to add the group and then choose New => Group from the contextual menu
4. Type the name for the new group
	![[Pasted image 20250709230034.png]]
5. Choose the group scope
   The choices are Domain Local, Global, and Universal. For groups that will be granted access rights to network resources, choose Domain Local. Use Global for groups to which you’ll add users and Domain Local groups. Use Universal groups only if you have a large network with multiple domains.
6. Choose the group type
7. Click Ok
### Adding a member to a group
Groups are collections of objects, called members
The group isn't useful until you add at least one member
Follow these steps to add a member to a group : 
1. Log on as an administrator
2. Choose Start => Administrative Tools => Active Directory Users and computers
3. Open the folder that contains the group to which you want to add members and then double-click the group
4. Click the Members tab
	![[Pasted image 20250709230241.png]]
5. Click Add, type the name of a user or another group that you want to add to this group and click ok
6. Repeat step 5 for each user or group that you want to add
7. Click ok
## Working with User profiles
User profiles automatically maintain desktop settings for windows users
The following items are just some of the settings that are stored as part of the user profile : 
- Desktop settings in the Display Properties dialog box, including wallpaper, screen savers, and color schemes
- Start-menu programs and Windows toolbar options
- Favorites, which provide easy access to the files and folders that the user accesses frequently
- Application Data, such as option settings, custom dictionaries, and so on
- Cookies, used for Internet browsing
- Recent Documents, which keeps shortcuts to the documents most recently accessed by the user
- Templates, which stores user templates
- Network, which keeps shortcuts to the user’s network locations
- Send To, which keeps shortcuts to document-handling utilities
- Local Settings, such as history and temporary files
- Printers, which keeps shortcuts to the user’s printers
- Documents, which stores the user’s local documents
### Types of User profiles
Four types of user profiles exist : 
- Local user profile: A local user profile is stored on the user’s local computer and is applied only when the user logs on to that computer. A local user profile is created automatically when a new user logs on.
- Roaming user profile: A roaming user profile is created on a network share. That way, the user can access the roaming profile when he or she logs on to any computer on the network.
- Mandatory user profile: A mandatory user profile is a roaming user profile that the user is not allowed to change. One benefit of mandatory user profiles is that users can’t mess up their desktop settings. Another benefit is that you can create a single mandatory profile that can be used by multiple users.
- Temporary user profile: If a roaming or mandatory profile isn’t available for some reason, a temporary user profile is automatically created for the user. The temporary profile is deleted when the user logs off, so any changes that the user makes while using a temporary profile are lost at the end of the session.
#### Roaming Profiles
A roaming user profile is simply to a user profile that has been copied to a network share so that it can be accessed from any computer on the network
After you’ve created the shared Users folder, you can copy the profile to the server by following these steps at the user’s local computer:
1. Log on to the computer by using an account other than the one you want to make a user account
2. Open file explorer right click this pc choose properties advanced system settings and then click settings in the user profile section
   ![[Pasted image 20250709230758.png]]
3. Select the profile that you want to copy and then click copy to. A copy to dialog box appears
4. Type the path and name for the roaming profile in the copy profile to box
5. Click Ok

Now you can go back to the server, log on as an administrator, and follow these steps to designate a roaming profile for the user’s domain account:
1. From the server manager, choose Tools => Active Directory users and computers
2. Right-click the user account, and choose properties from the contextual menu
3. Click the Profile tab
4. Type the path and name of the profile in the profile path text box
5. Click ok
## Creating a Logon Script
The most common reason for using a logon script is to map the network shares that the user needs access to 
![[Pasted image 20250709231038.png]]
If you want, you can use the special variable %username% to get the user's username. This variable is useful if you’ve created a folder for each user, and you want to map a drive to each user’s folder,
![[Pasted image 20250709231107.png]]
==TIP==
	Scripts should be saved in the Scripts folder, which is buried deep in the bowels of the SYSVOL folder — typically, c:\Windows\SYSVOL\Sysvol\domainname\Scripts, where domain name is your domain name. Because you need to access this folder frequently, I suggest creating a shortcut to it on your desktop.
