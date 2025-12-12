Windows provides two distinct built-in ways to do this:

- Remote Desktop Connection (RDC) is designed to let you log into a Windows computer from a remote location. This is useful for managing a server without having to actually go to the computer room and accessing the server’s console, or for accessing a virtual server that has no physical console.
- Remote Assistance is used to connect to an existing session of another Windows computer so that you can provide technical support for the other user.
# Enabling Remote Desktop Connection 
Before you can use RDC to access a server, you must enable remote access on the server.
To do that follow these steps : 
1. Open the control panel and click system
2. Click the Remote Settings Link
   ![[Pasted image 20250715115320.png]]
3. Select the Allow remote connection to this computer radio button
4. Click ok
## Connecting Remotely
After you've enabled remote access on a server, you can connect to the server by using the Remote Desktop Client that's automatically installed with Windows. 
To do that follow these steps:
1. Click the Start button and type the word remote. Then click the Remote Desktop connection icon
   ![[Pasted image 20250715115509.png]]
2. Enter the name of the computer you want to connect to
3. Click the connect button
4. Enter your username and password then click Ok
   ![[Pasted image 20250715115548.png]]
5. Use the remote computer   ![[Pasted image 20250715115611.png]]
Here are a few other tips for working with Remote Desktop Connection: 
- Remote Desktop allow only one user at a time to log in to remote computer
- When you're using the Remote Desktop connection client, you can't just press Alt + Tab to get another program running on the client computer
- If you minimize the RDC client window, you have to provide your logon credentials again when you return
- RDC has several useful configuration options that you can access by click the options button
## Using keyboard shortcuts for Remote desktop
KEYBOARD SHORTCUTS FOR REMOTE DESKTOP
![[Pasted image 20250715115906.png]]
## Configuring Remote Desktop Options
Before you connect to a remote desktop session, you can set a variety of
options that affect how the remote desktop session will behave.
To  summon these options
Click the Start button
Type the word Remote
Click the remote desktop connection icon
Click the show options button at the bottom left of the window
![[Pasted image 20250715120021.png]]
==TIP==
	When you click the Save or Save As buttons, your settings are saved to an .rdp file. .rdp files are associated with the Remote Desktop Connection program, so you can double-click an .rdp file to open a saved connection. In other words, an .rdp file is a handy shortcut to a remote connection.
#### Setting the Display Options
![[Pasted image 20250715120112.png]]
Options available in the display options are : 
- Display configuration size slider
- Use all my monitor for remote session
- Choose the color depth of the remote session drop-down list
  Use this drop-down list to choose the color quality of the remote desktop. Over slower connections, reducing the color depth will help performance
- Display the connection bar when I use the Full screen
  The connection bar is a thin bar at the top of the screen that enables you to switch back to normal windowed mode.
   If you deselected this box, you'll have to remember that you can press Ctrl+Alt+Break to switch between full-screen and windowed mode.
#### Setting the Local Resources options
![[Pasted image 20250715120336.png]]
Options available in Local resources tab are :
- Remote Audio
- Apply Windows key combinations drop-down list
- Local devices and resources
You can also share local drives with the remote session
To do so 
Click More
Select the drives that you want to make available to the remote session
![[Pasted image 20250715120534.png]]
#### Setting the Experience Options
![[Pasted image 20250715120600.png]]
The Options on the Experience tab controls various settings that affect the responsiveness of your remote connections
The Options are :
- Choose your Connection speed to optimize performance drop-down list
- Persistent Bitmap Caching
- Reconnect If the connection is dropped
#### Setting the Advanced options
![[Pasted image 20250715120749.png]]
The advanced tab of the remote desktop connection lets you control two features
- Server Authentication : Determines what to do if an authentication problem such as an unknown security certificate is encountered when connecting to the server. The default action is to warn the user, but allow the user to continue if desired
- Connect from Anywhere: These settings are used only when you use an advanced server role called Remote Desktop Gateway to manage remote access to computers on your network.
# Using Remote Assistance
Windows include a handy feature called Remote Assistance, which is designed to let your provide technical support to an end user without going to the user's location
## Enabling Remote Assistance
To enable remote assistance and to use remote assistance follow these steps : 
1. Click the Start button type remote assistance and click allow remote assistance invitations to be sent from this computer
   ![[Pasted image 20250715121205.png]]
2. Select the Allow remote connections to this computer options
3. Click the Advanced button
   ![[Pasted image 20250715121229.png]]
4. Select the allow this computer to be controlled remotely check box
5. Click Ok
6. Click ok
## Inviting Someone to Help you via Remote assistance session
To invite someone to remote assistance follow these steps
1. Click the start button, type invite and then click invite someone to connect to your PC![[Pasted image 20250715121345.png]]
2. Click Invite someone you trust to help you![[Pasted image 20250715121401.png]]
3. Click save this invitation as a file, and save the invitation file to a convenient disk location
4. If you use Microsoft Outlook, you can alternatively choose use email to send an invitation. This options fires up outlook and creates an email with the invitation file already attached
   ![[Pasted image 20250715121514.png]]
5. Email the invitation file to the person you want to help you
6. Wait for your helper to request the password
   ![[Pasted image 20250715121540.png]]
7. Click Yes![[Pasted image 20250715121548.png]]
## Responding to a Remote Assistance Invitation
If you’ve received an invitation to a Remote Assistance session, you can
establish the session by these steps:
1. Click the Start button type invite and then click invite someone to connect to your PC
2. Click help someone who has invited you
3. Click use an invitation file
4. Locate the invitation file you were sent, select it and click Open![[Pasted image 20250715121717.png]]
==TIP==
	As an alternative to Steps 1 through 3, you can simply double-click the invitation file you received. This will launch Windows Remote Assistance and prompt you for the password.
5. Enter the password given to you by the user requesting help and then click Ok![[Pasted image 20250715121807.png]]
6. To take control of the user's computer, click request control
7. Do your thing
8. If necessary use the chat window to communicate with the user
   ![[Pasted image 20250715121833.png]]
9. To conclude the remote assistance session, simple close the remote assistance window