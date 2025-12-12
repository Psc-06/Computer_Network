# Understanding Permissions
Permissions allow users to access shared resources on a network.
Working of permission and access control : 
- Every object that is every file and folder on an NTFS volume has a set of permissions called the access control list (ACL) associated with it
- The ACL identifies the users and groups who can access the object and specifies what level of access each user or group has. A folder's ACL may specify that one group of users can read files in the folder, whereas another group can read and write files in the folder, and a third group is denied access to the folder
- Container objects file and volumes allow their ACLs to be inherited by the object that they contain. As a result if you specify permissions for a folder, those permissions extend to the files and child folders that appear within it
==TIP==
	Actually the six file and folder permissions compromise various combination of special permissions that grant more detailed access to files or folders
- It's best to assign permissions to groups rather than to individual users. Then if a particular user needs access to a particular resource, add that user to a group that has permission to use the resource.
FILE AND FOLDER PERMISSION
![[Pasted image 20250710102412.png]]
SPECIAL PERMISSIONS
![[Pasted image 20250710102423.png]]
# Understanding Shares
A share is simply a folder that is made available to other users via the network 
Each share has the following elements
- Share name : The name by which the share is known over the network. To make the share name compatible with older computers, you should stick to eight-character share names whenever possible
- Path : The path to the folder on the local computer that's being shared, such as D:\Accounting
- Description : An optional one-line description of the share
- Permissions : A list of users or groups who have been granted access to the share
MOST COMMON SPECIAL SHARES 
![[Pasted image 20250710102722.png]]
## Considering Best Practices for Setting Up Shares
Before you actually share any data on a file server, you should consider the following common practices :
- Never share data from a file server’s system volume (that is, the C: drive). Doing so is a bad idea because if the operating system becomes corrupted, you may need to restore the system volume from a backup. If the system volume contains data that's shared on the network, you’ll have to revert that data to the version stored on the backup being restored. By placing shared data on a separate volume, you can restore the system volume without affecting data.
- It’s a common practice to use the same name for both the folder being shared and the name of the share itself. So, a shared folder named Accounting is usually shared using the share name Accounting.
- It's also a common practice to create a folder named Shares at the root level of the volume that contains the shared data. Then create individual shared folders within the Shares folder.
For example, if the D: drive will contain shared folders named Accounting, Administration, and Marketing, you would create a folder structure like this:
![[Pasted image 20250710102933.png]]
## Managing Your File server
To manage shares on a windows server 2019 system
Open the server manager and select the file and storage services in the task pane on the left side of the window
Then 
Click shares to reveal the management console 
![[Pasted image 20250710103025.png]]
#### Using the New Share wizard
To create a new wizard using the new share wizard follow these steps : 
1. In Server Manager, click file and storage services, click shares, and then choose new share from the tasks drop-down menu
   ![[Pasted image 20250710103157.png]]
2. Select SMB share quick in the list of profiles and then click next
   ![[Pasted image 20250710103214.png]]
3. Select the server you want the share to reside on 
4. Select the location of the share by choosing one of these two options
	   - Select by Volume: This option selects the volume on which the shared folder will reside while letting the New Share Wizard create a folder for you. If you select this option, the wizard will create the shared folder on the designated volume. Use this option if the folder doesn't yet exist and you don't mind Windows placing it in the default location, which is inside a folder called Shares on the volume you specify.
	   - Type a Custom Path: Use this option if the folder exists or if you want to create one in a location other than the Shares folder.
5. Click Next
   ![[Pasted image 20250710103359.png]]
6. Type the name that you want to use for the share in the share name box
7. Enter a description for the share
8. Click Next
   ![[Pasted image 20250710103428.png]]
9. Select the share settings you'd like to use : 
	- Enable Access-Based Enumeration: Hides files that the user does not have permission to access
	- Allow Caching of Share: Makes the files available to offline users
	- Encrypt Data Access: Encrypts files accessed via the share
10. Click Next
    ![[Pasted image 20250710103524.png]]
11. If you want to customize the permissions, click customize permission
12. Click Next
13. Verify that all the settings are correct and then click create
    ![[Pasted image 20250710103611.png]]
![[Pasted image 20250710103623.png]]
#### Sharing a folder without the wizard
To share a folder without the wizard follow these steps
1. Open file explorer and navigate tot he folder that you want to share
2. Right-click the folder, and choose properties from the contextual menu
3. Select the sharing tab
   ![[Pasted image 20250710103742.png]]
4. Click the advanced sharing button
5. Select the share this folder check box to designate the folder as shared
   ![[Pasted image 20250710103805.png]]
6. Type the name that you want to use for the share in the share name box, and type a description of the share in the comments box
7. If you want to specify permissions now, click permissions
8. Click ok
9. Click Close
#### Getting permissions
To add permissions via file explorer follow these steps : 
1. Open file explorer and browse to the folder whose permission you want to manage
2. Right-click the folder you want to manage and choose properties from the contextual menu
3. Select the sharing tab, then click advanced sharing
4. Click Permissions
   ![[Pasted image 20250710104007.png]]
5. Click Add
   ![[Pasted image 20250710104016.png]]
6. Type the name of the user or group whom you want to grand permission and then click ok
==TIP==
	If you’re not sure of the name, click Advanced. This action brings up a dialog box that lets you search for existing users. You can click the Find Now button to display a list of all users and groups in the domain. Alternatively, you can enter the first part of the name that you’re looking for before you click Find Now to search more specifically.
7. Select the appropriate allow and deny check boxes to specify which permissions to allow for the user or group
8. Repeat step 5 through 7 for any other permissions that you want to add
9. When you're done, click ok
Few point to remember while adding permissions
- If you want to grant full access to everyone for this folder, don’t bother adding another permission. Instead, select the Everyone group and then select the Allow check box for each permission type.
- You can remove a permission by selecting the permission and then clicking Remove.
==REMEMBER==
	The permissions assigned in this procedure apply only to the share itself. The underlying folder also has a set of NTFS permissions. The effective permissions granted to a particular user are a combination of the share permissions and the NTFS permissions, with the more restrictive permissions always overriding less restrictive permissions. For example, if the share permissions grant a user Full Control permission but the folder’s NTFS permissions grant the user only Read permission, the user has only Read permission for the folder. 
	To set the NTFS permissions for a folder, open the folder’s Properties dialog box and select the Security tab.
