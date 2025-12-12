# The Many types of Mobile Devices
PDAs Personal digital assistants were little handheld computers designed to replace the old-fashioned Day-Timer books people used to carry around with them to keep track of their appointment calendars and address books
Some of the most common specifics of mobile devices are : 
- Mobile Phone : A mobile phone (or cellphone) is a mobile device whose primary purpose is to enable phone services
- Smartphone : A smartphone is a mobile phone with advanced features that aren't typically found on mobile phones
- Android : Android is an open-source operating system for smartphones developed by google
- iOS : iOS is the operating system used on Apple's popular iPhone and iPad mobile devices
- BlackBerry : BlackBerry was the king of the smartphone game. BlackBerry had a virtual monopoly on mobile devices that synchronized well with Microsoft Exchange
## Considering Security for Mobile Devices
As a network administrator, one of your main responsibilities regarding mobile devices is to keep them secure.
Unfortunately, that’s a significant challenge. 
Here are some of the reasons why:
- Mobile devices connect to your network via other networks that are out of your control. 
- Mobile devices are easy to lose
- Mobile devices run operating system that aren't as security-conscious as windows
- Users who wouldn't date install renegade software on their desktop computers think nothing of downloading free games or other applications to their handheld devices
- Inevitably, someone will buy his own handheld devices and connect it to your network without your knowledge or permission
Here are some recommendations for beefing up security for your mobile
devices:
- Establish clear, consistent policies for mobile devices, and enforce them.
- Make sure employees understand that they aren’t allowed to bring their own devices into your network unless you have made special provisions to allow it.
- Train your users in the security risks associated with using mobile devices.
- Implement antivirus protection for your mobile devices.
## Managing iOS devices
The success of the iPhone was due in large part to the genius of its operating system, iOS. 
In 2010, Apple released the iPad, a tablet computer that runs the same operating system as the iPhone. 
And in 2012, Apple introduced a smaller version of the iPad: the iPad mini. Together, these devices are commonly known as “iOS devices.”
#### Understanding the iPhone
The iPhone is essentially a combination of four devices
- A cellphone
- An iPod
- A digital camera
- An Internet device with its own web browser (Safari) and applications, such as email, calendar, and contact management
The iPhone has several other innovative features : 
- An accelerometer tracks the motion of the iPhone in three directions. The main use of the accelerometer is to adjust the orientation of the display from landscape to portrait based on how the user is holding the phone. Some other applications — mostly games — use the accelerometer as well.
- A Wi-Fi interface lets the iPhone connect to local Wi-Fi networks for faster Internet access.
- GPS capability provides location awareness for many applications, including Google Maps.
- The virtual private network (VPN) client lets you connect to your internal network.
#### Understanding the iPad
The iPad is essentially an iPhone without the phone but with a larger screen. Apart from these basic differences, an iPad is nearly identical to an iPhone. Any application that can run on an iPhone can also run on an iPad, and many applications are designed to take special advantage of the iPad’s larger screen.
#### Integrating iOS devices with Exchange
An iOS device can integrate with Microsoft Exchange email via the Exchange ActiveSync feature, which is enabled by default on Exchange 2010 and later versions.
To verify the Exchange ActiveSync feature for an individual mailbox,
follow these steps:
1. Choose start => Administrative Tools => Active Directory Users and computers
2. Expand the domain and then locate the user you want to enable mobile access for
3. Click the Exchange Features tab![[Pasted image 20250716120009.png]]
4. Ensure that the Exchange ActiveSync option is enabled
5. Click ok
6. Close Active Directory Users and Computers
That’s all there is to it. After you enable these features, any users running Windows Mobile can synchronize their handheld devices with their Exchange mailboxes.

After ActiveSync is enabled for the mailbox, you can configure an iPhone or iPad to tap into the Exchange account by Follow these steps:
1. On the iPhone or iPad tap settings and then tap Mail, Contacts and calendars
   ![[Pasted image 20250716120135.png]]
2. Tap add account
   ![[Pasted image 20250716120142.png]]
3. Tap Exchange
   ![[Pasted image 20250716120151.png]]
4. Enter your email address, password and a description of the account
5. Tap Next
   ![[Pasted image 20250716120218.png]]
6. Enter either the DNS name or the IP address of your exchange server in the server field
7. Enter your domain name, your windows username and your windows password in the appropriate fields
8. Tap Next
   ![[Pasted image 20250716120258.png]]
9. Select the features you want to synchronize and then tap Done
## Managing Android Devices
The most important difference in many ways, the only important difference is that Android phones are based on an open-source OS derived from Linux, which can be extended and adapted to work on a wide variety of hardware devices from different vendors. 
With the iPhone, you’re locked into Apple hardware. 
With an Android phone, you can buy hardware from a variety of manufacturers.
#### Looking at the Android OS
The Android OS is an opensource OS managed by the Open Handset Alliance (OHA).
Technically speaking, Android is more than just an OS. It’s also a complete software stack, which comprises several key components that work together to create the complete Android platform:
- The OS core, which is based on the popular Linux OS
- A middleware layer, which provides drivers and other support code to enable the OS core to work with the hardware devices that make up a complete phone, such as a touch-sensitive display, the cellphone radio, the speaker and microphone, Bluetooth or Wi-Fi networking components, and so on
- A set of core applications that the user interacts with to make phone calls, read email, send text messages, take pictures, and so on
- A software development kit (SDK) that lets third-party software developers create their own applications to run on an Android phone, as well as a marketplace where the applications can be marketed and sold, much as the App Store lets iPhone developers market and sell applications for the iPhone
Besides the basic features provided by all OSs, few bonus features of the Android software stack:
- An optimized graphical display engine that can produce sophisticated 2-D and 3-D graphics
- GPS capabilities that provide location awareness that can be integrated with applications such as Google Maps
- Compass and accelerometer capabilities that can determine whether the phone is in motion and in which direction it’s pointed
- A built-in SQL database server for data storage
- Support for several network technologies, including Bluetooth and Wi-Fi
- Built-in media support, including common formats for still images, audio, and video files
#### Perusing Android's core Applications
The Android OS comes preconfigured with several standard applications, which provide the functionality that most people demand from a modern smartphone. These applications include
- Dialer
- Browser
- Messaging: Provides text (SMS and multimedia (MMS) messaging
- Email
- Contacts
- Camera
- Calculator
- Alarm Clock
- Maps
- YouTube
- Music
- Market
- Settings
#### Integrating Android With Exchange 
The Android’s core Email application can integrate with Microsoft Exchange email. If you’re using Exchange, you must enable Exchange Mobile Services and then enable ActiveSync for the user’s mailbox.
{
The text implies that the distinction between a 'mobile phone' and a 'PDA' became blurred due to a specific technological advancement. What was it?
The addition of data capabilities to cellular networks.
Right answer
The text states, 'All that changed when cellular providers began adding data capabilities to their networks,' leading to phones getting PDA features and vice versa.
}