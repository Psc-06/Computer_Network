# Defining Spam
The most basic definition of spam is any email that arrives in your inbox that you didn't ask for it.
Spam is unsolicited email
Spam is called junk email
There is a crucial difference between physical junk mail and junk email.
With physical junk mail, the sender must pay the cost of postage.
As a result, even though junk mail can be annoying, most junk mail is carefully targeted. 
Junk mailers don’t want to waste their money on postage to send mail to people who aren’t interested in what they have to sell.
==WARNING==
	One thing is sure: Spam is not just annoying; it’s dangerous. Besides filling up your users’ inboxes with unwanted email, spam emails often carry attachments that harbor viruses or other malware, or entice your users into clicking links that take them to websites that can infect your network. If your network is ever taken down by a virus, there’s a very good chance that the virus entered your network by way of spam.
## Sampling the Many Flavors of Spam
Several distinct categories of spam are : 
- Advertisements
- Phishing Emails
- Scams : The most common type of email scam is called an advance-fee scam, in which you're promised a large reward or prize in the future for advancing a relatively small amount of money now in the form of a wire transfer or money order
- Ads for pornographic websites
- Get-rich-quick schemes
- Backscatter : Backscatter is a particularly annoying phenomenon in which your inbox becomes flooded with dozens or perhaps hundreds of nondelivery reports (NDRs), indicating that an email that you allegedly sent didn’t arrive.
==TIP==
	Though technically not spam, many users consider advertisements and newsletters from companies they have dealt with in the past to be a form of spam. An important element of the definition of spam is the word unsolicited. When you register at a company’s website, you’re effectively inviting that company to send you email.
## Using Antispam Software
The most effective way to eliminate spam from your user's inboxes is to use antispam software
Antispam software examines all incoming email with the intent of distinguishing between spam and legitimate email
==TIP==
	Microsoft Exchange mailboxes include a Junk folder that is often the ultimate destination of email identified as spam. You should always check your Junk folder whenever you can’t find an email you’re expecting.
The programs that usually deliver a daily email (often called a digest) that lists the emails that were identified as spam
False Positives => in which a legitimate piece of email is mistakenly identified as spam
False negatives => In which a spam email is not detected as spam and makes it into the user's inbox
==TIP==
The possibility of false negatives is one of the main reasons that it’s rarely a good idea to configure an antispam program to simply delete spam. Most programs can be configured to delete only the most obvious spam emails — the ones that can be identified as spam with 100 percent certainty. Email that is probably spam but with less than 100 percent certainty should be marked as spam but not deleted.
## Understanding Spam Filters
Antispam programs use a variety of different techniques to determine the probability of a given piece of email being spam. These techniques are employed by filters, which examine each piece of email; each filter uses a specific technique.

Here are some of the most commonly used filter types:
- Keyword Checking : The biggest problem with keyword checking is that it often leads to false positives
  For example, if you list Cialis as a keyword that you want blocked, you’ll also block the words specialist or socialist.
   For these reasons, keyword filters are typically used only for the most obvious and offensive words and phrases, if they’re used at all.
- Bayesian analysis : One of the most trusted forms of spam filtering is Bayesian analysis, which works by assuming that certain words occur more often in spam email than in other email.
- Sender Policy Framework (SPF) : Surprisingly, SMTP (The Internet Email Protocol) has very poor built-in security
  SPF lets you designate via DNS which specific email servers are allowed to send email from your domain. An antispam SPF filter works by looking up the sending email server against the SPF records in the DNS of the domain specified by the email’s From address.
- Block list : Another trusted form of spam filtering is a block list, which uses a list of known spammers to block email from sources that aren’t trustworthy. There are two types of block lists: private and public. A private block list is a list that you set up yourself to designate sources you don’t want to accept email from. A public block list is a list that is maintained by a company or organization and is available for others to use.
==WARNING==
	Unfortunately, spammers don’t usually set up their own servers to send out their spam. Instead, they hijack other servers to do their dirty work. Legitimate email servers can be hijacked by spammers and, thus, become spam sources, often without the knowledge of their owners. This raises the unfortunate possibility that your own email server might be taken over by a spammer, and you might find your email server listed on a public block list. If that happens, you won’t be able to send email to anyone who uses that block list until you have corrected the problem that allowed your server to be hijacked and petitioned the block list owners to have your server removed.
- Friend list : One of the most important elements of any antispam solution is a friend list, which ensure that email from known senders will never be blocked.
==TIP==
	Historically, the block list has been called the blacklist, and the friends list has been called the whitelist. Words matter, and even subtle slights like these that associate negative connotations with blackness and positive connotations with whiteness are ultimately harmful to all of us. The change in terminology was long overdue.
==TIP==
	Most friends list filters will let you friends list entire domains, as well as individual email addresses. You most certainly do not want to friends list domains of large email providers such as gmail.com or comcast.net. But you should friends list the domains of all your business partners and clients to ensure that emails from new employees at these key companies are never marked as spam.
==TIP==
	Use the friends list to preemptively allow important email that you’re expecting from new customers, vendors, or service providers. For example, if you switch payroll providers, find out in advance what email addresses the new provider will be using so that your payroll staff doesn’t miss important emails.
- Graylisting : Graylisting is an effective antispam technique that exploits the fact that if a legitimate email server can’t successfully deliver an email on its first attempt, the server will try again later, typically in 30 minutes.
  The drawback of graylisting is that the first time you receive an email from a new sender. the email will be delayed
## Looking at Three Types of Antispam Software
The many different antispam software programs that are available fall into three broad categories : 
- On-premises
- Appliance
- Cloud-based (Hosted)
#### On-premises antispam
An on-premises antispam program runs on a server on your network and interacts directly with your email server.
Some of the advantages of using an on-premises antispam product are : 
- You have complete control over the configuration and operating of the software
- On-premises antispam software is usually tightly integrated not only with Microsoft Exchange but also with Microsoft Outlook
- On-premises software is relatively inexpensive
Some of the disadvantages of on-premises antispam software are : 
- You're responsible for installing, patching, configuring, updating and otherwise maintaining the software
- Because the relationship between the email server and the antispam software is complicated, on-premises antispam software periodically malfunctions
- On-premises antispam software increases the workload on your servers, requiring additional resources in the form of processor time, RAM, disk storage, and network bandwidth.
#### Antispam appliances
An antispam appliance is essentially an on-premises server in a dedicated box that you install at your location. 
The appliance is usually a self-contained Linux-based computer running antispam software that is pre-installed on the appliance.
This makes the appliance essentially plug and- play; you just set it up, connect it to your network, turn it on, and configure it using a simple web-based interface.
Some of the advantages of using an antispam appliance are :
- Because the appliance include its own hardware and pre-installed operating system you don't have to worry about purchasing hardware separately, installing an operating system, installing software or any of the other tasks associated with setting up a server
- After it's set up, an appliance will pretty much take care of itself
- The appliance may provide other security features, such as antivirus and firewall protection
Some of the disadvantages of antispam appliance are : 
- Eventually, you'll outgrow the appliance
  For example, if the number of users on your network doubles, you may run out of disk space.
- If the appliance fails, you may have trouble getting it back up and running
#### Cloud-based antispam services
A cloud-based antispam service (also called hosted antispam) is an Internet-based service that filters your email before it ever arrives at your mail server. 
When you use hosted antispam, you reconfigure your public DNS so that your mail server (the MX record) points to the cloud-based antispam server rather than to your mail server.
==TIP==
	If you use Microsoft Exchange Online as your email provider, you already have built-in antispam protection available.
Advantages of using cloud-based antispam are : 
- You get to skip the hassle of installing and configuring software, integrating the software with Exchange, maintaining and patching the software, and all the other chores associated with hosting your own server on your own premises
- Because you don't have to buy software or hardware, there is no initial investment. You simply subscribe to the service and pay the monthly service charges
- A cloud-based antispam solution scales easily with your organization. If you double the number of users, you simply pay twice as much per month
- Cloud-based antispam takes a huge load off your network and your mail server
Some disadvantages of cloud-based antispam are ; 
- You give up some control
- if the service goes down, so does your incoming email
## Minimizing Spam
No antispam program is perfect, so you need to understand and expect that a certain amount of spam will get through to your inbox. 
Here are some tips that you (and your users) should keep in mind to minimize the amount of spam that gets through undetected:
- Never trust email that requests your password or credit card
- Never open attachments in spam
- Do not reply to spam
- Use your antispam program's "This is spam" feature
- Unsubscribe from legitimate emails
==WARNING==
	Spammers often include an unsubscribe link on their spam emails. If the email is actually spam, clicking the unsubscribe link is akin to replying to the spam — it simply confirms to the spammers that they’ve found a legitimate email address, and you’ll just get more spam. Worse yet, the link may take you to a malicious website that will attempt to install malware on your computer. So, before you click the unsubscribe link, make sure that the email is indeed from a legitimate sender.
- Protect your email address
- Use an alternate email address
- Don't publish your email address
