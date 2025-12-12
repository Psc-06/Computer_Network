Exchange online is the email server for office 365
## Looking at Exchange Online Recipient types
Exchange online supports a variety of different types of recipients for different purposes : 
- Mailbox: A standard mailbox provides email and other features for an Office 365 user. This mailbox contains all the features you normally associate with an Outlook account: email, calendar, contacts, notes, and to-do list. Unlike on-premises Exchange, in Office 365 a standard mailbox is automatically created for every new user. So, you don’t ever have to manually create standard mailboxes in Exchange Online.
- Shared mailbox: A shared mailbox is a mailbox that doesn’t have a specific user associated with it. Instead, existing users can be granted access to the shared mailbox. A shared mailbox is a great way to provide a common email address that’s monitored and used by several people. And it’s also a great way to preserve the email for someone who no longer works for your company: Exchange Online makes it easy to convert a standard mailbox to a shared mailbox. 
  The best thing about a shared mailbox is that it’s free, provided it contains less than 50GB of data. If it’s larger than 50GB, you’ll need to purchase a license.
- Microsoft 365 Group: A Microsoft 365 Group represents a team of users who can collaborate using Microsoft Teams, which provides an online space for meetings, chat, file storage, and calendars. This type of group also includes a group email address so anyone can send an email to all members of the group.
- Distribution group: A distribution group is a simpler type of group that provides a group email address but no other features. Mail-enabled security group: A mail-enabled security group (often just called a security group) is like a distribution group that lets you assign access rights to members of the group.
- Dynamic group: A dynamic group is like a distribution group, but the membership isn’t defined by a static list of users but by a set of rules. The rules are evaluated each time email is sent to the group.
- Resource: A resource is a mailbox that isn’t associated with a user but instead is associated with a resource within your organization, such as a conference room or a vehicle. The most important feature of a resource is its calendar; users can reserve the resource by including it in a meeting request or other calendar item. The resource can be configured to automatically accept all invitations (provided the resource is available) to accept reservations or you can designate one or more people who must approve booking requests.
## Examining the Exchange Admin center
To get the Exchange Admin Center, follow these steps : 
1. Log in to office 365 at www.office.com ![[Pasted image 20250711183150.png]]
2. Click the Admin icon at the bottom of the icons on the left side of the page ![[Pasted image 20250711183211.png]]
==TIP==
	If you don't see the Admin icon, you don't have administrative privileges
3. Click the Show All icon at the bottom of the list of icons on the left
4. Click the exchange icon  ![[Pasted image 20250711183303.png]]
Microsoft had two versions of its administration center for managing Exchange Online. 
The Traditional version presents a large menu of specific administrative tasks you can attend to.
For example, to manage mailboxes, click the Mailboxes link under Recipients
The new Exchange Admin Center provides a much better overall view of your Microsoft Exchange Environment. 
It represent a true dashboard, showing details such as the number of inbound and outbound emails, non-delivery reports, and alerts
![[Pasted image 20250711183525.png]]
You can activate the new Exchange Admin Center by clicking the big blue new exchange Admin center button on the bottom left of the traditional admin center
The information displays in the dashboard are called cards, & you can populate your dashboard with a range of available cards by clicking the add card button.
The Available cards are :
- Training & Guide: Displays links to Microsoft documentation and tutorial information to help you learn more about administering Exchange. I suggest you add this card to your dashboard when you’re first starting with Exchange. You can remove it later when you no longer need it.
![[Pasted image 20250711183914.png]]
- Auto-Forwarded Messages: Displays information about messages that have been forwarded outside of your organization.
- Inbound Message Details: Tracks incoming email.
- Migration Batch Report: If you’re undergoing a migration from on-premises Exchange to Exchange Online, this card can help you track your progress.
- Non-Accepted Domain: This card can help you track email from your own domain where the sender’s domain isn’t listed as an acceptable domain for your server.
- Non-Delivery Report: Tracks error codes for the latest five days of undeliverable email.
- Outbound Message Details: Tracks outgoing email. SMTP AUTH Client: Tracks SMTP clients connected to your Exchange server.
- Recent Alerts Report: Tracks recent Exchange alerts.
- Queues Report: Reports information about the status of Exchange message queues.
- Top Domain Mailflow Status: This card is useful if your organization has multiple domains, because it shows the status of email for each domain.
To add one of these cards to your dashboard, hover the mouse over the card until a plus sign is displayed (shown in the margin), then click the plus sign. When the card is added to the dashboard, you can drag it to change its location. To remove a card, click the ellipses (…) at the upper right of the card and choose Remove.
By default, this option is turned off, so email forwarded is automatically deleted from the original mailbox
## Managing Mailboxes
Main task in the Exchange Admin Center will be managing various types of recipients.
Common features you can set from the mailbox details pane : 
![[Pasted image 20250711185139.png]]
![[Pasted image 20250711185142.png]]
### Creating an email alias
An email alias is an alternative email address for a mailbox.
To set up an alias follow these steps : 
1. Click Manage Email Address type under email address
   ![[Pasted image 20250711185241.png]]
2. Click + Add Email address type
   ![[Pasted image 20250711185251.png]]
3. Enter the new email address and click ok
Here are few additional information about the Manage Email address type page ; 
- When you create a new alias, you can make the alias act as the default reply address for outgoing email sent from the mailbox
- The email address must use a domain that is authorized for the Exchange server.
- Although SMTP is the most common type of email address, you can also add other address types such as X.500, X.400, Lotus Notes, and Novel GroupWise.
- You can also use the Manage Email Address Types page to remove an email alias or to change the primary email address used for the mailbox.
### Assigning a mailbox
To delegate access to a mailbox, open the mailbox in the mailboxes page of the Exchange Admin Center, and then follow these steps : 
1. Select Manage Mailbox Delegation![[Pasted image 20250711185542.png]]
   There are three types of delegation you can set : 
	- Read and Manage: Also referred to as Full Access permissions. A user who has Full Access has complete control over the mailbox.
	- Send As: This option provides more limited access; the delegated user cannot fully control the mailbox but can send messages as if they were sent by the mailbox owner.
	- Send on Behalf: This option allows the delegated user to send email from the mailbox, but the From address will clearly indicate that the message was sent on behalf of the mailbox owner by the delegated user.
2. Click Edit next to the type of permission you want to grant![[Pasted image 20250711185715.png]]
3. Click Add Permissions ![[Pasted image 20250711185733.png]]
4. Select the user or users you want to grant permission to ![[Pasted image 20250711185757.png]]
5. Click save
6. Click the X at the upper right of the manage mailbox delegation page to close the page
### Converting a standard mailbox to a shared mailbox
When an employee leaves your organization, it’s common to convert that employee’s mailbox to a shared mailbox so that email can continue to flow in and other users can access it.
The Procedure to convert a mailbox to a shared mailbox is simple : 
1. Select the user in the Mailboxes administration page
   ![[Pasted image 20250711185911.png]]
2. Select Convert to Shared Mailbox
   ![[Pasted image 20250711185946.png]]
3. Click Confirm
4. Click close
### Enabling or disabling mailbox apps
Exchange Mailbox Apps are different ways a user can connect to an Exchange mailbox.
To manage this option, click Manage Email Apps settings in the mailbox details pane
![[Pasted image 20250711190059.png]]
Here are the apps that are controlled from this pane :
- Outlook on the Web: Lets the user access her Exchange mailbox from a web browser rather than from an Outlook client. With this feature enabled, the user can read email from any computer that has an Internet connection.
- Outlook Desktop (MAPI): Enables email using the MAPI protocol, which is used by the Outlook desktop application.
- Exchange Web Services: Exchange Web Services (EWS) is a protocol that allows developers to connect to an Exchange mailbox.
- Mobile (Exchange ActiveSync): Activates the ActiveSync feature, which allows Exchange data to synchronize with mobile devices such as iPhones or Android devices.
- IMAP: Enables email using the IMAP protocol.
- POP: Enables email using the POP protocol.
### Creating a forwarder
A forwarder is a feature that automatically forwards any incoming email to another email address
To configure a forwarder, follow these steps : 
1. In Exchange Administrative Center, open the User Mailbox pane for the user
2. Click Manage Mail flow settings, found under mail flow settings  ![[Pasted image 20250711190438.png]]
3. Click Edit in the Email Forwarding Section  ![[Pasted image 20250711190453.png]]
4. Flip the switch to turn on email forwarding
5. Enter the email address to which you want email forwarded
6. If desired, flip the switch to retain forwarded email in the mailbox
7. Click Save
8. Click close  ![[Pasted image 20250711190536.png]]
The Manage Mail Flow Settings pane has two other mail flow settings you can adjust : 
- Message Size Restriction: This setting lets you specify the maximum size of sent and received email messages. The default is 35,840 bytes (35KB).
- Message Delivery Restriction: You can use this option to set who can and can’t send email to the mailbox.
# Creating a Shared Mailbox
To create a shared mailbox from the recipients page follow these steps: 
1. Open the Mail administration page in Exchange Admin Center
2. Click Add a shared Mailbox![[Pasted image 20250711190725.png]]
3. Enter the display name, email address, and domain for the new shared mailbox
4. Click Create  ![[Pasted image 20250711190750.png]]
5. Choose Add users to this mailbox
6. Click Add users![[Pasted image 20250711190810.png]]
7. Select the users you want to add to the mailbox and click save
8. Click close
9. Click the X at the upper-right corner to close the pane
   ![[Pasted image 20250711190842.png]]
