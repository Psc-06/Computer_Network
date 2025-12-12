Group policy refers to a feature of Windows Operating System that lets you control how certain aspects of windows and other Microsoft software work throughout your network.
Group policy is an important tool for any windows network administrator
# Understanding Group Policy
Group policy consists of a collection of group policy objects (GPOs) that define individual policies.
These policies objects are selectively applied to both users and computers
A policy that applies to a computer will be applied for every user on that computer and a policy that applies to a user will be applied for that user on every computer
(
There is a computer and policies and rules have been put on it. If any user accesses it, he will have to handle those policies and rules.
And if the administrator has imposed policies or rules on the user, then whenever that user wants to access the device, he will have to face those rules and policies
)
To use group policy, you have to know how to do two things
1. Create Individual group policy objects
2. Apply or link those objects to user and computer objects
## Enabling Group Policy Management on Windows Server 2019
To enable group policy on windows server 2019 follow these steps : 
1. In the server manager, click add roles and features
2. Follow the wizard until you get the select features screen
   ![[Pasted image 20250710112227.png]]
3. If the group policy management check box is not already checked, select it 
4. Click Next
5. When the configuration page appears, click Install
6. Click close
# Creating group Policy Objects
The easiest way to create group policy objects is to use the group policy management console,
Which you can run from the server manager by
choosing tools => Group policy Management
So we will be creating a GPO that defines group policy enabling windows update for all computers in a domain so that users can't disable windows update : 
1. In the Server Manager, choose tools  => group policy management![[Pasted image 20250710112515.png]]
2. In the Navigation pane, drill down through the domains node to the node for your domain, then select the group policy objects node for your domain
3. Right-click the group policy objects node and then choose new from the contextual menu that appears
   ![[Pasted image 20250710112609.png]]
4. Type a name for the group policy object and then click ok
5. Double-click the new group policy
   ![[Pasted image 20250710112630.png]]
6. Click the settings tab
   ![[Pasted image 20250710112641.png]]
==TIP==
	If you get a message indication that the content has been blocked by security settings, click add to enable access. You'll see the policy settings
7. Right-Click Computer configuration and then choose edit from the contextual menu ![[Pasted image 20250710112732.png]]
8. In the navigation pane, navigate to Computer Configuration => Policies => Administrative Templates => Windows Components => Windows Update![[Pasted image 20250710112806.png]]
9. Double-click configure automatic updates
10. Select Enabled to enable the policy
11. Configure the windows update settings however you want    ![[Pasted image 20250710112841.png]]
12. Click Ok
13. Close the group policy management editor window
14. Right-Click Computer configuration and choose refresh from the contextual menu![[Pasted image 20250710112921.png]]
15. In the navigation pane of the group policy management window, drag the new windows update policy object to the top-level domain ![[Pasted image 20250710113013.png]]
16. Click Ok
    ![[Pasted image 20250710113024.png]]
17. Close the group policy management window
==TIP==
	You may notice that there is both column and a link enabled column on the scope tab. In this example the windows update GPO is linked to the lowewriter.com domain, but not enforced. Don't let this confuse you, The GPO is indeed applied to all active directory objects in the domain. 
- Link Enabled : When a GPO is linked to an Active Directory container, the settings of the GPO are applied to all objects in the container.
- Enforced: This setting provides an extra layer of assurance that the GPO settings will be applied by preventing other GPOs that may also be applied to the object from overriding the settings of this GPO. Enforced is rarely used.
## Filtering Group Policy Objects
Suppose that you want to use group policy to assign two different default home pages for Internet Explorer. For the Marketing department, you want the default home page to be www.dummies.com, but for the Accounting department, you’d like the default home page to be www.beancounters.com. You can easily accomplish this task by creating two groups named Marketing and Accounting in Active Directory Users and Computers, and assigning the marketing and accounting users to the appropriate groups. Next, you can create two group policy objects: one for the Marketing department’s home page and the other to assign the Accounting department’s home page. Then you can link both of these policy objects to the domain and use filters to specify which group each policy applies to.
To filter above polices to link correctly to the group  follow these steps : 
1. Choose start => Administrative Tools => Group Policy Management
2. In the navigation pane, navigate to the group policy object you want to apply the filter to
   ![[Pasted image 20250710113544.png]]
3. In the Security filtering section, click authenticated users and then click remove
4. Click Add
   ![[Pasted image 20250710113606.png]]
5. Type accounting in the text box and then click ok
6. Repeat Steps 2 through 5 for the home page dummies policy applying it to the marketing group
   ![[Pasted image 20250710113637.png]]
