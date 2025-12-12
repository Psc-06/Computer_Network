Postfix, which is a standard part of most Linux distributions, is one of the most popular mail server programs on the internet
Before Postfix, Sendmail was the most popular mail server for Linux
Postfix is faster, more secure and easier to manage
==WARNING==
	Spam artists — unscrupulous marketers who clutter the Internet with millions of unsolicited emails — are constantly on the prowl for unprotected Postfix servers, which they can use to launch their spam campaigns. If you don't protect your server, sooner or later, a spammer will coax your computer into spending almost all its time sending out the spammer’s email. To protect your server from becoming an indentured spam servant, you can configure it to refuse any mail that merely wants to use your computer to relay messages to other computers.
# Understanding Email
SMTP was first codified in 1983
In 1983, Eric Allman developed the first version of the Postfix program as part of the Berkeley Software Distribution (BSD) of UNix
Key features of email when setting up a Linux server running Postfix : 
- Mailbox: A mailbox is a repository for holding incoming email messages until they’re disposed of by a user. In Fedora Linux, each user has a mailbox file in /var/mail.
- Mail User Agent (MUA): A program that end users can use to send and receive mail. The most widely used MUA is Microsoft Outlook. Linux comes with several MUAs. The most basic is Mail, a textbased MUA that lets you read and compose email messages from a console prompt. Fedora also includes a sophisticated graphical MUA called Evolution, which is similar in many ways to Microsoft Outlook. Both are described later in this chapter.
- Mail Transfer Agent (MTA): A program that transfers email messages between computers. Postfix, which most of this chapter is devoted to, is an MTA. When a user uses an MUA to send an email message, the MUA delivers the message to an MTA, which then transfers the message to the intended recipient.
- Mail Delivery Agent (MDA): A program that accepts incoming mail from an MTA and places it in the intended recipient's mailbox. A basic MDA simply copies each message to the mailbox, but more advanced MDAs can be used to filter the incoming mail to eliminate spam or check for viruses. The default MDA for Fedora Linux is Procmail. Fedora also includes SpamAssassin, which you can use to filter spam from your incoming mail.
## Installing Postfix
To install Postfix, open a console or terminal window and enter the
following commands:
![[Pasted image 20250714113917.png]]
When Postfix is installed, its files are placed in several directories:
- /etc/postfix: Configuration files are placed here, with the exception of one configuration file (aliases) which is placed in /etc. 
- /var/spool/postfix: User email queues are stored here.
- /usr/sbin: Postfix commands are found here.
- /usr/libexec/postfix: All Postfix daemon programs are stored here.
- /var/lib/postfx: Postfix stores its working data here.
## Modifying main.cf
Postfix has a nearly endless list of configuration options, but setting up a basic configuration requires just a few changes. 
The configuration files are found in /etc/postfix, and the primary configuration file is main.cf.
Here's the procedure for editing main.cf to configure a basic mail
server:
1. Open the file /etc/postfix/main.cf with your favorite editor
2. Enable the myhostname parameter
   ![[Pasted image 20250714114124.png]]
   Uncomment it and replace the host it with the hostname of the email server
   ![[Pasted image 20250714114153.png]]
3. Enable the mydomain parameter
4. Enable the myorigin paramter
5. Verify that the correct inet_interfaces line is uncommented
   ![[Pasted image 20250714114238.png]]
   This line allows the mail server to listen on all network interfaces available to the server
6. Verify that the correct mydestination line is uncommented 
   look for the following line   ![[Pasted image 20250714114320.png]]
7. Enable the mynetworks parameters and set it to your local subnet 
   look for the following line ![[Pasted image 20250714114347.png]]
![[Pasted image 20250714114356.png]]
8. Save the file and exit the editor
9. Restart the postfix Service![[Pasted image 20250714114427.png]]
## Using SpamAssassin
SpamAssassin is a spam-blocking tool that uses a variety of techniques
to weed the spam out of your users' mailboxes. 
SpamAssassin uses a combination of rule filters that scan for suspicious message content and other telltale signs of spam, as well as block lists from known spammers.
#### Installing SpamAssassin
To install and configure SpamAssassin follow these steps : 
1. Install SpamAssassin 
   To do that enter the command![[Pasted image 20250714114551.png]]
2. Ensure that the SpamAssassin daemon is running
   To do that enter the command![[Pasted image 20250714114620.png]]
   If SpamAssassin isn't running, enter the command![[Pasted image 20250714114634.png]]
==TIP==
	Whenever you make a configuration change, you should stop and restart the service with this command![[Pasted image 20250714114705.png]]
3. Create a file named procmailrc in the /etc directory|
   Use vi for the text editor 
   ![[Pasted image 20250714114757.png]]
   These lines cause Procmail to run all incoming mail through the SpamAssassin client program
4. Restart Postfix and SpamAssassin 
   You can do this from 
   Applications => Server Settings => Services
   Or
   Enter the command
   ![[Pasted image 20250714114851.png]]
#### Customizing SpamAssassin
You can configure SpamAssassin by editing the configuration file
/etc/mail/spamassassin/local.cf.
In Fedora, the default local.cf file look like this
![[Pasted image 20250714114943.png]]
These lines cause SpamAssassin to add the word [SPAM] to the start of
the subject line for any message that scores 5 or higher on
SpamAssassin's spam scoring algorithm.
==TIP==
	Although you can configure SpamAssassin to automatically delete messages that score above a specified value, most antispam experts recommend against it. Instead, adding a word such as [SPAM] to the header lets each user decide how he wants to handle spam by using a message filter on his email client that either deletes the marked messages or moves them to a Spam folder.
#### Block listing and friends listing email addresses
SpamAssassin lets you block list or friends list a specific email address or an entire domain.
When you friends list an address, all mail from the address will be allowed through, even if the message would otherwise be blocked as spam.
==TIP==
	Friends listing is a powerful tool for making sure that the people you correspond with on a regular basis don’t get their email accidentally blocked by SpamAssassin. As a result, it’s a good idea to add your friends, relatives, and especially your customers to a friends list.
To friends list an address, add a line such as the following to
/etc/mail/spamassassin/local.rc:
![[Pasted image 20250714115215.png]]
To block list an address, add a line like this 
![[Pasted image 20250714115243.png]]
## Using the Mail Console Client
To install  the mail command, open a terminal window and enter the  command
![[Pasted image 20250714115319.png]]
To read mail, open a command console, log on using the account whose
mail you want to read, and enter the command mail. A list of all
messages in your mailbox will be displayed.
MAIL COMMANDS
![[Pasted image 20250714115341.png]]
To compose a new message from a command prompt, follow these steps
1. Type mail followed by the email address of the recipient
   ![[Pasted image 20250714115420.png]]
2. Type the subject line and press enter
3. Type the message test. Use the enter key to start new lines
4. To send message, enter a line consisting of only a period