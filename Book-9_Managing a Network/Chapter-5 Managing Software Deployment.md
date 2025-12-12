# Understanding Software Licenses
When we install software there is text of a software agreement before the purchase. There are some typical agreement contains restrictions and that are : 
- You're allowed to install the software on one and only one computer
- The license agreement probably allows you to make a backup copy of the disks/discs
- You aren't allowed to reverse-engineer the software
- Some software restricts the kinds of applications it can be used for
- Some software has export restrictions that prevent you from taking it out of the country
- Nearly all software licenses limit the liability of the software vendor to replacing defective installation disks/discs
- Retail : A retail software license usually grants you the right for a single user to install and use the software
  The main benefit of a retail license is that it stays with the user when the user upgrades his or her computer
- OEM : It stands for Original equipment manufacturer
  For example, if you purchase a computer from Dell and order Microsoft Office Professional along with the computer, you’re getting an OEM license. The most important thing to know about an OEM license is that it applies only to the specific computer for which you purchased the software.
- Volume : Allows you to install and use the software on more than one computer
  MICROSOFT VOLUME LICENSE PLANS
  ![[Pasted image 20250716110823.png]]
- Subscription
## Using a license Server
Some programs let you purchase network licenses that enable you to
install the software on as many computers as you want, but regulate the
number of people who can use the software at any given time.
One of the most commonly used license server software is FlexNet publisher by Flexera Software
FlexNet Publisher uses special license files issued by a software vendor to indicate how many licenses of a given product you purchased.
EXAMPLE OF A LICENSE FILE FOR AUTOCAD
![[Pasted image 20250716111022.png]]
For example, what if you have AutoCAD installed on a notebook computer, but you want to use it while you’re away from the office? 
In that case, you have two options
- Use virtual private network (VPN) software to connect to the network
- Borrow a license
==TIP==
	In most cases, the license server is a mission-critical application as important as any other function on your network. If the license server goes down, all users who depend on it will be unable to work. Don’t worry; they’ll let you know. They’ll be lining up outside your door demanding to know when you can get the license server up and running so they can get back to work.
## Options for Deploying Network Software
#### Deploying Software Manually
==WARNING==
	When you finish manually installing software from a CD or DVD, don’t forget to remove the disc from the drive! It’s easy to leave the disc in the drive, and if the user rarely or never uses the drive, it might be weeks or months before anyone discovers that the disc is missing. By that time, you’ll be hard-pressed to remember where it is.
To install software manually the setup will ask to enter a serial number, registration number, license key or other code that proves you purchased the software
#### Running Setup from a network share
If you plan on installing a program on more than two or three computers
on your network, you’ll find it much easier to run the Setup program
from a network share rather than from the original CDs or DVDs. 
To do so, follow these steps:
1. Create a network share and a folder within the share where you can store the setup program and other files required to install the program
2. Copy the entire contents of the program's CD or DVD on the folder 
   To do so, insert the CD or DVD in your computer’s CD/DVD drive. Then, use Windows Explorer to select the entire contents of the disc and drag it to the folder
   Alternatively, you can choose Start⇒ Run to open a command prompt. Then, enter a command, such as this:![[Pasted image 20250716111559.png]]
   In this example, d: is the drive letter of your CD/DVD drive, server1 is the name of your file server, and software and someprogram are the names of the share and folder you created
3. To install the program on a client computer open windows explorer window navigate to the share and folder you create and double click the setup.exe file
4. Follow the instructions display by the setup program
#### Installing Silently
In some cases, the Setup program itself has a command line switch that
causes it to run silently. You can usually find out what command line
switches are available by entering the following at a command prompt:
![[Pasted image 20250716111756.png]]
With luck, you’ll find that the Setup program itself has a switch, such as
/quiet or /silent, that installs the program with no interaction, using
the program's default settings.
If the Setup program doesn't offer any command line switches, don’t despair. 
Follow these steps to silently install the software
1. Open an Explorer Window and navigate to
   Windows 10 (as well as previous versions later than XP): C:\Users\name\AppData\Local\Temp
   Windows XP: C:\Documents and Settings\name\Local Settings\Temp
   Then, delete the entire contents of this foler
2. Run the setup program and follow the installation steps right up to the final step
3. Return to the Temp Folder and then poke around until you find .msi file created by the setup program 
   The .msi file is the actual Windows Installer program that Setup runs to install the program. It may have a cryptic name, such as 84993882.msi.
4. Copy the .msi file to the network share from which you want to install the program on your client computers
5. (optional) Rename the .msi file to setup.msi
6. The notepad to create a batch file to run the .msi file with /quiet switch
   ![[Pasted image 20250716112138.png]]
##### Create an administrative installation image
For Microsoft software, this silent setup program is called an 'administrative installation image'
To create an administrative image, you simply run the configuration tool
supplied by the vendor. 
The configuration tool lets you choose the installation options you want to have applied when the software is installed. 
Then, it creates a network setup program on a network share that you specify. 
You can then install the software on a client computer by opening an Explorer window, navigating to the network share where you saved the network setup program, and running the network setup program.
#### Pushing out software with group policy
One final option you should consider for network software deployment
is using Windows Group Policy to automatically install software to
network users
Advertising software on a computer means that a small portion of the software is downloaded to the computer — just enough to display an icon for the program on the Start menu and to associate Excel with the Excel file extensions
## Keeping Software up to Date
![[Pasted image 20250716112905.png]]
{
A user installs a retail-licensed program on their work desktop and their home laptop, as permitted by the EULA. If the user leaves the company, which action is compliant with the license agreement?
he user must uninstall the software from the company desktop, but can keep it on their personal laptop.
Right answer
The license is tied to the individual user. They must ensure it is no longer on company property, but they retain the right to use it personally as per the agreement.
An administrator is using the 'xcopy d:\*.* \\server1\software\someprogram\*.* /s' command. What would be the consequence of omitting the '/s' switch?
Only the files in the root of the D: drive would be copied, and any installation files in subfolders would be missing.
Right answer
The `/s` switch instructs `xcopy` to copy directories and subdirectories, except for empty ones. Without it, only top-level files are copied.
An administrator is trying to perform a silent installation of a program whose setup file does not have a `/quiet` or `/silent` switch. They follow the procedure to capture the `.msi` file from the Temp folder, but cannot find it. What is a likely reason for this failure?
The setup program is not using the Windows Installer service and therefore does not create a temporary `.msi` file.
Right answer
The technique of capturing an `.msi` file only works for installers that are wrappers for the Windows Installer. Some programs use different, proprietary installation technologies.
}