# Introducing Office 365
The first version, Microsoft office for windows was released in 1990.
The version contained just three applications : Word, Excel and PowerPoint
Microsoft access was added in 1995
&
Outlook was added in 2000
In 2011, Office 365 arrived on the scene
Most popular features available in office 365 are : 
- Azure-based Active Directory synchronized with your on-premises Active Directory
- All the standard applications that traditionally came with Office — Access, Excel, PowerPoint, Publisher, OneNote, Outlook, and Word
- Exchange Online, a cloud-hosted version of Exchange Server that provides email services
- Microsoft Teams for online meetings, collaboration, chat, and calling
- SharePoint for building a company Intranet
- Yammer to provide a company social network
- OneDrive for cloud-based file storage (limited to 1TB with some plans, unlimited with others)
- Various work-management apps, including Forms, Planner, Power Apps, Power Automate, Power Virtual Agents, and To Do
![[Pasted image 20250711111054.png]]
## Considering Office 365 Plans
Consumer Plans are designed for home use or very small businesses
Enterprise plans provide more-advanced features and are designed for larger business
SMALL BUSINESS PLANS FOR MICROSOFT 365
![[Pasted image 20250711111208.png]]
ENTERPRISE PLANS FOR MICROSOFT 365
![[Pasted image 20250711111241.png]]
REMEMBER
	The good news is that you don’t have to fret much over the decision of which plan to select when you’re just getting started. It’s easy to upgrade the plan later. Microsoft is always willing to take more of your money! You can easily start with Microsoft 365 Business Basic, and then upgrade later to Business Premium or Office 365 E3 or E5.
# Understanding Tenants
In the world of Office 365, The environment that represents a single organization is called a tenant.
A tenant is dedicated instance of Active Directory running in Azure
The tenant manages all the users, apps, and data associated with the organization
You cannot change the tenant name after you've selected it
==WARNING==
	Be very deliberate about the tenant name you choose when you set up a tenant. One of the absolute worst things you can do is set up an experimental or test tenant using your company’s primary domain name as the onmicrosoft.com name. If you do, you'll never be able to use your company’s domain name for the tenant later on.
## Creating an Office 365 Tenant
let’s get on with the procedure for creating a new tenant for Office 365. In this example, I’ll select the Enterprise-level Office 365 E3 plan and use lowewriter.onmicrosoft.com as the tenant name.
Follow these steps
1. Go to www.microsoft.com/en-us/microsoft-365 and click For Enterprise.  ![[Pasted image 20250711111848.png]]
2. Under Office 365 E3, Click buy now![[Pasted image 20250711111907.png]]
3. Enter your email address and click next
4. Click Set Up account   ![[Pasted image 20250711111926.png]]
5. Enter your personal information
6. Click Next   ![[Pasted image 20250711111942.png]]
7. Click Send Verification code
8. When you receive the verification code, enter it and click verify![[Pasted image 20250711112003.png]]
9. Enter the onmicrosft.com tenant name you want to use
10. Click Check Availability
11. If the name is available, think again about the name you choose
12. Click Next    ![[Pasted image 20250711112054.png]]
13. Enter the name and password twice
14. Click Sign Up![[Pasted image 20250711112125.png]]
15. Click Add Payment method, enter your credit card details and then click save
16. Click Place order
17. Click Go to setup to get started    ![[Pasted image 20250711112204.png]]
## Creating a New User
To create a new user account in Office 365, follow these steps
1. Go to Admin center by browsing to https://admin.microsoft.com, logging in, and clicking the admin icon 
   ![[Pasted image 20250711112257.png]]
2. In the menu pane at the left select the users and then select active users![[Pasted image 20250711112313.png]]
3. Click Add user, and then choose single user![[Pasted image 20250711112327.png]]
4. Enter the user's first and last name, display name and username
5. Either let Microsoft generate a random password or click let me create the password and enter a password yourself
6. Click Next![[Pasted image 20250711112401.png]]
7. Select the product license to assign to the new user
8. Click Next
9. If you're prompted to buy another license, click Yes
10. Click Apps near the bottom of the wizard page to reveal all applications that are available in the E3 License    ![[Pasted image 20250711112448.png]]
11. Click Next![[Pasted image 20250711112504.png]]
12. Click Roles to assign admin roles to the user, if desired![[Pasted image 20250711112518.png]]
13. Click Profile info to fill out the user's profile information![[Pasted image 20250711112533.png]]
    You can set the following values : 
    - Job title
    - Department
    - Office
    - Office phone and fax number
    - Mobile Phone
    - Street Address, city and state
14. Click Next![[Pasted image 20250711112633.png]]
15. Click Finish Adding
16. Click Close![[Pasted image 20250711112646.png]]
## Resetting a User's Password
To reset the password follow these steps : 
1. At the Active Users page, select the user account
2. Click the Reset Password button, shown in the margin
3. Click reset Password
==TIP==
	You’ll also find a check box that allows you to send the new password via email. You can send the email to yourself or to the user, but sending it to the user won’t be much help because the user presumably can’t sign in, having forgotten his or her password. So, send it to yourself or the user’s manager, and then let the user know what the new password is.
4. You're done
## Disabling a User
Office 365 provides two ways to disable a user.
- The most drastic is to simply delete the user account, which you can do at the active users page by clicking the delete a user button
- The more temperate option is to block the user from accessing office 365. 
  This allows you to restore access later on. When you block access, the user will be barred from all office 365 applications and be kicked out of any active office 365 application within an hour
Follow these steps to disable a user
1. In Active users, click the user name
   ![[Pasted image 20250711113309.png]]
2. Click the block Sign-in button
   ![[Pasted image 20250711113314.png]]
3. Click Block this user from signing in, and then click save changes