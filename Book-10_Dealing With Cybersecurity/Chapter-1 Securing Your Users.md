## Knowing the Difference between Authentication and Authorization
Before I get far into securing user accounts, I want to make sure you understand the distinction between two important concepts of user account security:
- Authentication: Authentication refers to the process of determining that the person using an account is the person who should be using the account. These measures are usually called two-factor authentication or multifactor authentication.
- Authorization: In contrast to authentication, authorization refers to the process of establishing whether a given user is allowed to use a given resource on the network.
## Following Password Best Practices
Your network password is the one thing that keeps an impostor from logging on to the network by using your username and receiving the same access rights that you ordinarily have.
Here are some times for creating good passwords : 
- Don't use obvious password (for example last name admin123 etc)
- Don't pick passwords based on your hobbies
- Store your password in your head, not on paper
- Set expiration times for password 
- Configure user account so that when they change passwords they can't specify a password that they've used recently
- Configure security policies so that passwords must include a mixture of uppercase letters, lowercase letters, numerals and special symbols
- Use a biometric ID device, like a fingerprint reader, as a way to keep passwords
Recent research is suggesting that much of what we've believed about security for the last 30 or so years are making our accounts less secure . Why? Two reasons : 
- The requirement to change passwords frequently and making them too complicated to memorize simply encourages users to write their passwords down, which makes them easy to steal.
- A common way that passwords are compromised is by theft of the encrypted form of the password database, which can then be attacked using simple dictionary methods. Even the most complex passwords can be cracked using a dictionary attack if the password is relatively short; the most important factor in making passwords difficult to crack is not complexity but length.
![[Pasted image 20250716185937.png]]
![[Pasted image 20250716185943.png]]
As a result, the National Institute for Standards and Technology (NIST) recommends new guidelines for creating secure passwords:
- Encourage longer passwords.
- Drop the complexity requirement. Instead, encourage users to create passwords that they can easily remember. A simple sentence or phrase consisting of ordinary words will suffice, as long as the sentence or phrase is long. For example, “My password is a simple sentence” would make a good password.
- Drop the requirement to change passwords periodically; it only encourages users to write down their passwords.
## Securing the Administrator Account
At least one network user must have the authority to use the network without any of the restrictions imposed on other users. This user  the administrator  is responsible for setting up the network’s security system. To do that, the administrator must be exempt from all security restrictions.
Here are some best practices for ensuring the safety of this password : 
- It should be very long — perhaps 20 characters or more — and preferably randomly generated.
- Write it down, place it in a sealed envelope, and put the envelope in a safe-deposit vault at your bank. Only a few select individuals should have access to the password. It should not be stored in the same safedeposit box as other corporate papers that may need to be accessed occasionally.
- No one should know the password. It should be used when the domain is created or in a disaster-recovery situation, and no one in the organization should memorize it, write it down, or store it in a file no matter how carefully encrypted.
## Understanding Multifactor Authentication
Multifactor authentication is an authentication process in which a username and password are not enough to gain access to a system. In addition to the username and password, you must provide at least one other type of evidence that you are who you claim to be.
In general, there are three types of evidence you can present to verify your identity:
- Something you know: For example, your username and password
- Something you have: For example, a phone that can be sent a verification number or a security card you can swipe
- Something you are: For example, your fingerprint or retina pattern
There are several common types of authentication checks that may call themselves multifactor but aren't really. For example : 
- Security questions: These questions may ask for the name of the school you attended for the sixth grade or the city in which your parents met. Security questions aren’t actually all that secure, and they certainly aren’t a form of multifactor authentication. After all, the username, the password, and the name of your favorite teacher are all things you know.
- Email verification codes: Some authentication systems email you a confirmation number that you must enter to gain access. In my view, this is next to worthless. If a hacker has learned your username and password, there’s no reason to think the hacker can’t access your email and steal the verification code as well.
## Securing the Human Firewall
The key to securing your network users is to empower them to realize that they're an important part of your company's cybersecurity plan, and then show them what they can do to become an effective human firewall
#### Establishing Cybersecurity Policies
It is essential that you set at least basic security policies and make sure your entire staff knows them
At the minimum, security policies should address the following
- Password management
- Acceptable use
- Remote access
- Confidentiality
- Privacy
- Email and document retention
- Asset management and tracking
#### Training
Improving cybersecurity awareness involves training, and IT training is usually the most dreaded type of training there is. So, do your best to make the training fun and engaging rather than dull and boring.
#### Phish testing
A final idea you should consider is to conduct phish testing, which means that you regularly send bogus emails to your staff to see how they respond.
==REMEMBER==
	The purpose of phish testing is not to humiliate or embarrass your users, but to help them become better at protecting your organization from a devastating cyberattack. Always follow up a phish test with an email that lets your staff know about the phish test, how you did as an organization, and what clues were in the email they could have noticed.
