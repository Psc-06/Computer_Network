# Using PowerShell
To open PowerShell follow these steps
1. Press the window key on your keyboard and then type PowerShell
2. Press the enter key![[Pasted image 20250710220750.png]]
==TIP==
	If you want to perform administrative functions while in PowerShell, you’ll need to open PowerShell as an administrator. To do that, right-click the Windows PowerShell icon and choose Run As Administrator.
==WARNING==
	PowerShell is an incredibly powerful administrative tool, and opening a PowerShell window as an administrator can be risky if you aren’t sure what you’re doing. I suggest that while you’re learning PowerShell, you do so on your desktop computer rather than on one of your servers. At least if you make serious mistakes on your own desktop computer, you won’t bring down everyone else! (I’m half joking here. As a network administrator, you know how to be careful. But it’s a good idea to experiment on your own computer or one you’ve designated as a sandbox rather than on a critical server!)
Few difference between the command prompt and PowerShell is
- Though it’s not apparent in the figure, the background for a PowerShell window is blue rather than black.
- The title bar indicates that you’re in Windows PowerShell.
- The welcome banner at the top of the window announces that you’re using PowerShell.
- Although the command prompt is similar to the prompt for a standard command shell, the current directory is prefixed with PS to remind you that you’re in PowerShell.
# Understanding PowerShell Commands
PowerShell supports four distinctly different kinds of commands you can run directly from the PowerShell prompt : 
- Native commands: A native command is a standard Windows command that you would ordinarily run at a normal command prompt. Traditional commands such as xcopy, ipconfig, and ping can all be run from a PowerShell prompt.
- Cmdlets: A cmdlet (which is short for commandlet) is the basic built-in PowerShell command. All cmdlet names follow a consistent verb-noun format.
- Scripts: A script is a collection of PowerShell commands saved to a text file with the extension .ps1. You can run a script at a PowerShell prompt simply by typing the name of the script, without the extension. In short, scripts are PowerShell's equivalent for batch files.
- Functions: A function is a set of PowerShell commands that you give a name. Then you can run the named set of commands using the function's name as if it were a command. Here’s a simple example that creates and then calls a function:![[Pasted image 20250710221238.png]]
The first command entered above creates a function named rnd. The list of commands to be executed for the function is enclosed within curly braces; in this example, just a single command is used (Get- Random). This line creates a function named rnd that runs the Get- Random cmdlet.
The second command calls the rnd function that display another random number.
# Using Cmdlets
For example, in the Get-Random cmdlet, the verb is Get and the noun is
Random.
Nouns in PowerShell are always singular. For example, the command
that retrieves a list of all system services is called get-service, not getservices.
To see the list of all the verbs of get-verb cmdlet type get-verb in the PowerShell
PowerShell names are not case-sensitive
## Using Parameters
Most cmdlets let you use parameters that allow you to customize the behavior of the cmdlet
Parameter names are preceded by a hyphen and followed by the parameter value
![[Pasted image 20250710221701.png]]
Some Parameters don't have values,
In that case you just list the parameter name without a subsequent value
![[Pasted image 20250710221809.png]]
This cmdlet, Get-ChildItem, is PowerShell's equivalent to the dir command: It lists the contents of the current directory. The -recurse parameter tells Get-ChildItem to list not just the current directory, but all subdirectories as well.
POWERSHELL COMMON PARAMETERS
![[Pasted image 20250710222022.png]]
Some cmdlet parameters are positional, which means that you can omit
the parameter name and just list the parameter values. For the
Get_Random cmdlet, -Maximum is the first positional parameter. So, if you
simply specify a value without a parameter name, Get-Random uses the
value as the -Maximum parameter:
![[Pasted image 20250710222044.png]]
## Getting help
PowerShell includes an extensive collection of help information that you can access via the Get-Help cmdlet.
For Example![[Pasted image 20250710222147.png]]
![[Pasted image 20250710222152.png]]
You can use several additional parameters to get even more help information
- Examples: Displays examples of the cmdlet, along with a detailed explanation of what each example does.
- -Detailed: Provides more detailed help.
- -Full: Displays all available help information.
- -Online: Opens a web browser homed on Microsoft's help page for the cmdlet.
# Using Aliases
An Alias is an alternative name for a cmdlet.
For example
Get-ChildItem is the PowerShell equivalent of the dir command, and the PowerShell provides dir as an alias for the Get-ChildItem command
![[Pasted image 20250710222505.png]]
If you want to see a list of all the aliases that are available, use the Get-
Alias cmdlet. To narrow the list down to show just the aliases for a
particular cmdlet, use the -Definition parameter, as in this example:
![[Pasted image 20250710222528.png]]
If you want to create your own aliases, you can use the Set-Alias command
This command requires two parameters -name which provides the name of the alias and a -value which indicated that will be aliases
![[Pasted image 20250710222633.png]]
To remove an alias use Remote-item Cmdlet
![[Pasted image 20250710222725.png]]
# Using the Pipeline
With cmdlets, the information that is piped is not simple text but complete obejcts
An object is an amalgamation of data, as well as executable code.
Objects have properties, which are named characteristics of the object, and methods, which are named function that the object can perform
You can easily manipulate the output displayed for a cmdlet by piping the output to one of several commonly used cmdlets that sort, filter, or otherwise format the objects in the pipeline. 
For example, if you want to show the contents of a folder in reverse alphabetical order, you can pipe the Get-ChildItem cmdlet's output into the Sort-Object cmdlet and use the -Descending parameter to reverse the order:
![[Pasted image 20250710223105.png]]
![[Pasted image 20250710223110.png]]
If you want to pick and choose which properties to display when you use
Get-ChildItem, you can use the Select-Object cmdlet. 
For example:![[Pasted image 20250710223139.png]]
You can select more than one property by separating the property names
with commas
![[Pasted image 20250710223200.png]]
Here's an example that invokes three cmdlets: The first gets the contents of the current folder, the second selects just the Name property, and the third sorts the list in descending order:
![[Pasted image 20250710223223.png]]
# Using Providers
A provider is a source of data that is consumed by many of PowerShell's command
For example, the Get-ChildItem command consumes information from a provider called Filesystem, which represents the host computer's file system.
PowerShell provides several providers besides Filesystem. To see them
all, you can use the Get-PSProvider command:![[Pasted image 20250710223415.png]]
(
The provided list appears to describe different PowerShell providers and some of their capabilities or characteristics. Let's break down each one:
Each line generally follows this format: `ProviderName Capabilities {Scope or DriveName}`
Here's an explanation of each entry:
- **Registry**
    - **Provider Name:** `Registry`
    - **Capabilities:**
        - `ShouldProcess`: This indicates that cmdlets operating on the Registry provider support the `-WhatIf` and `-Confirm` parameters. These parameters are crucial for safe scripting, allowing you to preview the effect of a command before making changes (`-WhatIf`) or requiring confirmation before execution (`-Confirm`).
        - `Transactions`: This is a powerful capability. It means that operations performed on the Registry can be grouped into a single, atomic transaction. If any part of the transaction fails, all changes can be rolled back, ensuring data consistency. This is similar to database transactions.
    - **Scope/Drive Names:** `{HKLM, HKCU}`. These are the default drives or scopes exposed by the Registry provider.
        - `HKLM`: HKEY_LOCAL_MACHINE, a root key in the Windows Registry that contains settings for all users on the computer.
        - `HKCU`: HKEY_CURRENT_USER, a root key in the Windows Registry that contains settings for the currently logged-in user.
- **Alias**
    - **Provider Name:** `Alias`
    - **Capabilities:**
        - `ShouldProcess`: Cmdlets working with aliases support `-WhatIf` and `-Confirm`. This means you can preview or confirm changes when creating, modifying, or removing aliases.
    - **Scope/Drive Name:** `{Alias}`. This is the drive that the Alias provider exposes, allowing you to navigate and manage PowerShell aliases as if they were files or folders.
- **Environment**
    - **Provider Name:** `Environment`
    - **Capabilities:**
        - `ShouldProcess`: Cmdlets interacting with environment variables support `-WhatIf` and `-Confirm`. You can safely preview or confirm modifications to environment variables.
    - **Scope/Drive Name:** `{Env}`. This is the drive exposed by the Environment provider, allowing you to manage system and user environment variables.
- **Filesystem**
        - **Provider Name:** `FileSystem`
    - **Capabilities:**
        - `Filter`: This indicates that cmdlets for the Filesystem provider support the `-Filter` parameter. The `-Filter` parameter allows you to specify a filter string to select specific items (e.g., files with a certain extension or name pattern) more efficiently than using `Where-Object`.
        - `ShouldProcess`: Cmdlets like `Remove-Item`, `Copy-Item`, etc., support `-WhatIf` and `-Confirm`, enabling safer file system operations.
        - `Credentials`: This is a very important capability. It means that cmdlets operating on the Filesystem can accept credentials (e.g., a username and password) to access resources that require authentication. This is essential for working with network shares or remote file systems where the current user's credentials might not have sufficient permissions.
    - **Scope/Drive Names:** `{C, D}`. These represent typical hard drive letters (drives) exposed by the Filesystem provider, allowing you to navigate and manage files and folders. The actual drives available will vary by system.
- **Function**
    - **Provider Name:** `Function`
    - **Capabilities:**
        - `ShouldProcess`: Cmdlets for managing PowerShell functions (e.g., `New-Function`, `Remove-Function`) support `-WhatIf` and `-Confirm`.
    - **Scope/Drive Name:** `{Function}`. This is the drive exposed by the Function provider, allowing you to interact with PowerShell functions as if they were items in a file system.
- **Variable**
    - **Provider Name:** `Variable`
    - **Capabilities:**
        - `ShouldProcess`: Cmdlets for managing PowerShell variables support `-WhatIf` and `-Confirm`.
    - **Scope/Drive Name:** `{Variable}`. This is the drive exposed by the Variable provider, allowing you to interact with PowerShell variables as if they were items in a file system.
**In summary, this list describes:**
- **PowerShell Providers:** These are components that allow PowerShell to treat different data stores (like the Registry, file system, or environment variables) as if they were file system drives, making them navigable and manageable with common cmdlets (e.g., `Get-Item`, `Set-Item`, `Remove-Item`).
- **Provider Capabilities:** These indicate specific features or parameters that cmdlets working with that provider support, enhancing their functionality and safety.   
- **Default Drives/Scopes:** These are the "roots" of the data stores exposed by each provider, similar to how `C:\` is a root for the Filesystem.   
This information is fundamental to understanding how PowerShell interacts with various system components and data stores.
)
# Using Scripts
A script is a collection of PowerShell commands saved to a text file with the extension .ps1
For example, suppose you routinely want to know what processes are consuming the most memory resources. You can do that using a combination of several cmdlets:
- Use Get-Process to get a list of active processes.
- Use Select-Object to select just the ProcessName and WS properties. (WS stands for working set, which is one of the key memory indicators in a Windows system.)
- Use Sort-Object to sort the result in descending order on the WS property.
- Use Select-Object again to select just the top ten results.
IT WILL LOOK LIKE THIS
![[Pasted image 20250710224155.png]]
To ease this we can create a .ps1 file with the command
![[Pasted image 20250710224220.png]]
Then to run this file just write the file name in the PowerShell
Before you run scripts in PowerShell, you have to make a few preparations
- Run PowerShell with administrator permissions
- Enable scripts execution by using the Set-Execution Policy Cmdlet
  set the execution policy to unrestricted
- Save your scripts to a location you can easily access
![[Pasted image 20250710224421.png]]
Some additional features are ; 
- Variables, which let you store and later retrieve values and objects.
- Functions, which let you create a set of PowerShell commands that you give a name to. Then you can run the named set of commands using the function’s name as if it were a command.
- Advanced Functions, which let you create functions with parameters.
- Logic statements, including `While, Do…While, Do…Until, For, Foreach, If, and Switch.`