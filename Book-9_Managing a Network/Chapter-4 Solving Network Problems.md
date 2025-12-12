## When Bad Things Happed to Good computers
Here are some basic troubleshooting steps explaining what you should examine at the first sign of network trouble
In many cases of the cases, one of the steps can get your network back up and running : 
1. Make sure that your computer and everything attached to it is plugged in.
==TECHNICAL STUFF==
	Computer geeks love it when a user calls for help, and they get to tell the user that the computer isn’t plugged in or that its power strip is turned off. They write it down in their geek logs so that they can tell their geek friends about it later. They may even want to take your picture so that they can show it to their geek friends. (Most “accidents” involving computer geeks are a direct result of this kind of behavior. So try to be tactful when you ask a user whether he or she is sure the computer is actually turned on.)
2. Make sure that your computer is properly connected to the network
3. Note any error messages that appear on the screen
4. Try restarting the computer
==TIP==
	An amazing number of computer problems are cleared up by a simple restart of the computer. Of course, in many cases, the problem recurs, so you’ll have to eventually isolate the cause and fix the problem. But many problems are only intermittent, and a simple reboot is all that’s needed.
5. Try the build-in Windows Network Troubleshooter
6. Check the free disk space on your computer and on the server
7. Do a little experimenting to find out whether the problem is indeed a network problem or just a problem with the computer itself
8. Try restarting the network server
## Fixing Dead computers
If a computer seems totally dead, here are some things to check
- Make sure that the computer is plugged in.
- If the computer is plugged into a surge protector or a power strip, make sure that the surge protector or power strip is plugged in and turned on.
- Make sure that the computer's on/off switch is turned on 
==REMEMBER==
	To complicate matters, newer computers have a Sleep feature, in which they appear to be turned off but really they’re just sleeping. All you have to do to wake such a computer is jiggle the mouse a little. (I used to have an uncle like that.) It’s easy to assume that the computer is turned off, press the power button, wonder why nothing happened, and then press the power button and hold it down, hoping it will take. If you hold down the power button long enough, the computer will actually turn itself off. Then, when you turn the computer back on, you get a message saying the computer wasn’t shut down properly. Arghhh! The moral of the story is to jiggle the mouse if the computer seems to have nodded off.
- If you think the computer isn't plugged in but it looks like it is, listen for the fan. If the fan is running, the computer is getting power and the problem is more serious than an unplugged power cord
- If the computer is plugged in and turned on but still not running plug a lamp into the outlet to make sure that the power is getting to the outlet
- Check the surge protector
- Make sure that the monitor is plugged in and turned on
- Make sure that all cables are plugged in securely
- If the computer is running but display is dark, but adjusting the monitor's contrast and brightness
## Ways to check a Network Connection
- Twisted-pair cable: If your network uses twisted-pair cable, you can quickly tell whether the cable connection to the network is good by looking at the back of your computer. Look for a small light located near where the cable plugs in; if this light is glowing steadily, the cable is good. If the light is dark or it’s flashing intermittently, you have a cable problem (or a problem with the network card or the hub or switch that the other end of the cable is plugged in to).
==TIP==
	If the light isn't glowing steadily, try removing the cable from your computer and reinserting it. This action may cure the weak connection
- Patch cable: Hopefully, your network is wired so that each computer is connected to the network with a short (six feet or so) patch cable. One end of the patch cable plugs into the computer, and the other end plugs into a cable connector mounted on the wall. Try quickly disconnecting and reconnecting the patch cable. If that doesn’t do the trick, try to find a spare patch cable that you can use.
- Switches: Switches are prone to having cable problems, too — especially switches that are wired in a less-than-professional manner, featuring a rat’s nest of patch cables. Be careful whenever you enter the lair of the rat’s nest. If you need to replace a patch cable, be very careful when you disconnect the suspected bad cable and reconnect the good cable in its place.
## A bunch of Error Messages just Flew By!
Error messages that display when your computer boots can provide
invaluable clues to determine the source of the problem.
If you see error messages when you start up the computer, keep the
points in mind:
- Don't panic if you see a lot of error messages
- If the messages fly by so fast that you can’t see them, press your computer’s Pause key. Your computer comes to a screeching halt, giving you a chance to catch up on your error-message reading. After you’ve read enough, press the Pause key again to get things moving. (On keyboards that don’t have a Pause key, pressing Ctrl+Num Lock or Ctrl+S does the same thing.)
==TIP==
	If you miss the error messages the first time, restart the computer and watch them again.
- Better yet, press F8 when you see the Starting Windows message. This displays a menu that allows you to select from several startup options. (Note that this won’t work on Windows 8, 8.1, or 10.)
## Double-Checking Your Network Settings
I swear that there are little green men who sneak into offices at night,
turn on computers, and mess up TCP/IP configuration settings just for
kicks. 
These little green men are affectionately known as networchons.
So one of the first things you do, after making sure that the computers are actually on and that the cables aren’t broken, is a basic review of the computer’s network settings.
Check :
- At a command prompt, run ipconfig to make sure that TCP/IP is up and running on the computer and that the IP addresses, subnet masks, and default gateway settings look right.
- Call up the network connection's Properties dialog box and make sure that the necessary protocols are installed correctly.
- Open the System Properties dialog box (double-click System in Control Panel) and check the Computer Name tab.
- Make sure that the computer name is unique and also that the domain or workgroup name is spelled properly.
- Double-check the user account to make sure that the user really has permission to access the resources he needs.
## Time To Experiment
Here are some ways you can narrow down the cause of the problem : 
- Try performing the same operation on someone else's computer
- If you're able to perform the operation on another computer without problems, try logging on to the network with another computer using your own username
- If you can't log on at another computer try waiting for a bit
## Who's on First
To find out who is currently logged on to a windows server
right-click the computer icon on the desktop
Choose manage form the menu
This brings up the computer management window
Open system tools in the tree list 
Then Open shared folder
Select sesion
A list of user who are logged on appears
==TIP==
	You can immediately disconnect all users by right-clicking Sessions in the Computer Management window and choosing All Tasks⇒ Disconnect All. Be warned, however, that this can cause users to lose data.
## Restarting a Client Computer
If restarting your computer doesn't seem to fix the problem you may need to turn your computer off and then turn it on again
Here are few things to try if you have trouble restarting your device
- If your computer refuses to respond to the Start⇒ Shut Down command, try pressing Ctrl+Alt+Delete.
  This is called the “three-finger salute.” It’s appropriate to say, “Queueue” while you do it.
- If pressing Ctrl+Alt+Delete doesn’t do anything, you’ve reached the last resort. The only thing left to do is turn off the computer by pressing the power On/Off button and holding it down for a few seconds.
## Booting in Safe mode
Windows provides a special start mode called safe mode that's designed to help fix misbehaving computers
Safe mode is especially useful when your computer has developed a problem that prevents you form using the computer at all
## Using System Restore
System Restore is a windows feature that periodically saves important windows configuration information and allows you to late return your system to a previously saved configuration
By default, windows saves restore point whenever you install new software on your computer or apply a system update.
Restore points are also saved automatically every seven days
System restore is turned on by default
To verify that the system restore is active follow the steps :
1. Right click computer in the start menu
2. Choose properties
3. Click system protection tab
   ![[Pasted image 20250715212837.png]]
4. Verify status for computer's c: drive is on
Few additional thoughts to remember about system restore are : 
- System Restore does not delete data files from your system. Thus, files in your Documents folder won’t be lost.
- System Restore does remove any applications or system updates you’ve installed since the time the restore point was made. Thus, you need to reinstall those applications or system updates — unless, of course, you determine that an application or system update was the cause of your problem in the first place.
- System Restore automatically restarts your computer. The restart may be slow because some of the changes made by System Restore happen after the restart.
- Do not turn off or cut power to your computer during System Restore. Doing so may leave your computer in an unrecoverable state.
- After completing a System Restore, you may discover that the user can’t log on to the computer because the computer complains about the “domain trust relationship” being lost. This happens because the internal password that Active Directory uses to verify the identity of the computer has been reset by the System Restore to a previous version. The only solution is to log in to a local account on the computer, leave the domain, reboot the computer, log in again using a local account, rejoin the domain, and reboot the computer again.
## Restarting Network Services
You can review the status of services by using the services tool![[Pasted image 20250715213122.png]]
To display it
Click the start button
Type services
Press Enter
==WARNING==
	Key services usually stop for a reason, so simply restarting a stopped service probably won’t solve your network’s problem — at least, not for long. You should review the System log to look for any error messages that may explain why the service stopped in the first place.
KEY WINDOWS SERVICES
![[Pasted image 20250715213222.png]]
## Restarting a Network Server
Sometimes the only way to flush out a network problem is to restart the network server that's experiencing trouble
To restart a network server follow these steps : 
1. Make sure that everyone is logged off the server
2. After you're sure the users have logged off, shut down the network server
3. Reboot the server computer or turn it off and then on again
4. Tell everyone to log back on and make sure that everyone can now access the network 
## Looking at Event Logs
One of the most useful troubleshooting techniques for diagnosing
network problems is to review the network operating system’s built-in
event logs.
These logs contain information about interesting and potentially troublesome events that occur during the daily operation of your network.
To display the event logs in a windows server, Use event viewer
Which is available from the administrative tools menu
EVENT VIEWER
![[Pasted image 20250715213523.png]]
The tree listing on the left side of Event Viewer lists five categories of events that are tracked: Application, Security, System, Directory Service, and File Replication Service. Select one of these options to see the log that you want to view. For details about a particular event, double-click the event to display a dialog box with detailed information about the event.
## Documenting Your Trials and Tribulations
Regardless of how you track your network problems, the tracking log
should include the information:
- The real name and the network username of the person reporting the problem
- The date the problem was first reported
- An indication of the severity of the problem
- Is it merely an inconvenience, or is a user unable to complete his or her work because of the problem? Does a work-around exist?
- The name of the person assigned to resolve the problem
- A description of the problem
- A list of the software involved, including versions
- A description of the steps taken to solve the problem
- A description of any intermediate steps that were taken to try to solve the problem, along with an indication of whether those steps were “undone” when they didn’t help solve the problem
- The date the problem was finally resolved