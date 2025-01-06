# Skills Assessment - Windows Fundamentals

<figure><img src="../../../.gitbook/assets/image (38).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (39).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (40).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (41).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (42).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (43).png" alt=""><figcaption></figcaption></figure>

10.129.201.211

The cheat sheet is a useful command reference for this module.

| **Command**                                                    | **Description**                                                         |
| -------------------------------------------------------------- | ----------------------------------------------------------------------- |
| `xfreerdp /v:<target IP address> /u:htb-student /p:<password>` | RDP to lab target                                                       |
|  `Get-WmiObject -Class win32_OperatingSystem`                  | Get information about the operating system                              |
| `dir c:\ /a`                                                   | View all files and directories in the c:\ root directory                |
| `tree <directory>`                                             | Graphically displaying the directory structure of a path                |
| `tree c:\ /f \| more`                                          | Walk through results of the `tree` command page by page                 |
| `icacls <directory>`                                           | View the permissions set on a directory                                 |
| `icacls c:\users /grant joe:f`                                 | Grant a user full permissions to a directory                            |
| `icacls c:\users /remove joe`                                  | Remove a users' permissions on a directory                              |
| `Get-Service`                                                  | `PowerShell` cmdlet to view running services                            |
| `help <command>`                                               | Display the help menu for a specific command                            |
| `get-alias`                                                    | List `PowerShell` aliases                                               |
| `New-Alias -Name "Show-Files" Get-ChildItem`                   | Create a new `PowerShell` alias                                         |
| `Get-Module \| select Name,ExportedCommands \| fl`             | View imported `PowerShell` modules and their associated commands        |
| `Get-ExecutionPolicy -List`                                    | View the `PowerShell` execution policy                                  |
| `Set-ExecutionPolicy Bypass -Scope Process`                    | Set the `PowerShell` execution policy to bypass for the current session |
| `wmic os list brief`                                           | Get information about the operating system with `wmic`                  |
| `Invoke-WmiMethod`                                             | Call methods of `WMI` objects                                           |
| `whoami /user`                                                 | View the current users' SID                                             |
| `reg query <key>`                                              | View information about a registry key                                   |
| `Get-MpComputerStatus`                                         | Check which `Defender` protection settings are enabled                  |
| `sconfig`                                                      | Load Server Configuration menu in Windows Server Core                   |

<figure><img src="../../../.gitbook/assets/image (44).png" alt=""><figcaption></figcaption></figure>

Above, I used the xfreerdp command to remote into the windows machine.

<figure><img src="../../../.gitbook/assets/image (45).png" alt=""><figcaption></figcaption></figure>

I created the Company data folder. Right click and select properties.

<figure><img src="../../../.gitbook/assets/image (46).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (47).png" alt=""><figcaption></figcaption></figure>

Selected the sharing tab. Then selected advanced Sharing button

<figure><img src="../../../.gitbook/assets/image (48).png" alt=""><figcaption></figcaption></figure>

Select "Share this folder"

<figure><img src="../../../.gitbook/assets/image (49).png" alt=""><figcaption></figcaption></figure>

Select apply then ok

<figure><img src="../../../.gitbook/assets/image (50).png" alt=""><figcaption></figcaption></figure>

Close out of that popup menu and then open up the company data folder

<figure><img src="../../../.gitbook/assets/image (51).png" alt=""><figcaption></figcaption></figure>

Created a subfolder named "HR"

<figure><img src="../../../.gitbook/assets/image (52).png" alt=""><figcaption></figcaption></figure>

Search up and open "computer management app"

<figure><img src="../../../.gitbook/assets/image (53).png" alt=""><figcaption></figcaption></figure>

Select local users and groups.&#x20;

<figure><img src="../../../.gitbook/assets/image (54).png" alt=""><figcaption></figcaption></figure>

Right click on users and select "new user".

<figure><img src="../../../.gitbook/assets/image (55).png" alt=""><figcaption></figcaption></figure>

Type in User name and Full name as "Jim" and uncheck "User must change password at next login" per htb's instructions.

<figure><img src="../../../.gitbook/assets/image (56).png" alt=""><figcaption></figcaption></figure>

Create a password and click create&#x20;

<figure><img src="../../../.gitbook/assets/image (57).png" alt=""><figcaption></figcaption></figure>

Select the Groups folder in the side panel and create a new group called HR

<figure><img src="../../../.gitbook/assets/image (58).png" alt=""><figcaption></figcaption></figure>

Double click on HR and select 'add' and input Jim to the HR group

<figure><img src="../../../.gitbook/assets/image (59).png" alt=""><figcaption></figcaption></figure>

You can type the name in the field and select check names to select the actual user&#x20;

<figure><img src="../../../.gitbook/assets/image (60).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (61).png" alt=""><figcaption></figcaption></figure>

Hit Ok, apply ok, all that.

<figure><img src="../../../.gitbook/assets/image (62).png" alt=""><figcaption></figcaption></figure>

Go back to the company data folder and right click, select properties, sharing tab and then advanced sharing.

<figure><img src="../../../.gitbook/assets/image (63).png" alt=""><figcaption></figcaption></figure>

Select Permissions button

<figure><img src="../../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

Remove the 'Everyone' group from the permissions

<figure><img src="../../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

Select 'add'

<figure><img src="../../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

Type 'HR' then hit 'check names' then select ok

<figure><img src="../../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

Add change and read permission

<figure><img src="../../../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

Hit apply, and then OK. Go to the security tab in the properties&#x20;

<figure><img src="../../../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

Select advanced

<figure><img src="../../../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

Select disable inheritance

<figure><img src="../../../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

Select convert inherited permissions into explicit permissions on this object.

<figure><img src="../../../.gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>

Someone would select **"Convert inherited permissions into explicit permissions on this object"** when disabling inheritance to maintain the same set of permissions that the object currently has but make them independent of the parent object's permissions. Here's why this might be desirable:

1. **Maintain Existing Permissions:** This option ensures that the current permissions applied to the object remain intact. Disabling inheritance without converting the permissions would otherwise result in losing all inherited permissions, which could inadvertently lock users out or disrupt access control.
2. **Customization:** By converting inherited permissions to explicit permissions, you can modify or fine-tune permissions specific to the object without affecting or being affected by the parent object’s permissions.
3. **Preservation of Access Control:** If permissions were inherited from a parent object and those permissions are needed for the object to function properly or for certain users to retain access, converting them to explicit permissions ensures continuity.
4. **Granular Management:** Once permissions are explicit, they can be adjusted for the specific object without altering permissions of other objects that share the parent’s inheritance.

This is particularly useful in environments where permissions need to be adjusted for individual files, folders, or objects without propagating changes across the entire hierarchy.

<figure><img src="../../../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

hit 'apply' then hit add

<figure><img src="../../../.gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>

Click on 'select a principal'

<figure><img src="../../../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

Enter HR in the object name field and then select check names

<figure><img src="../../../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

Make sure the basic permissions that are selected are: Modify, Read & execute, List folder contents, Read and Write.

<figure><img src="../../../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>

Hit OK

Select OK in this menu as well:

<figure><img src="../../../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

Verify permissions for HR:

<figure><img src="../../../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>

Select 'close'

Go to the HR subfolder, right click on it and select properties:

<figure><img src="../../../.gitbook/assets/image (18).png" alt=""><figcaption></figcaption></figure>

In the sharing tab select advanced sharing.

<figure><img src="../../../.gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>

Whoops, actually back out of that and don't right click on the HR folder, instead right click inside of the company data folder:

<figure><img src="../../../.gitbook/assets/image (20).png" alt=""><figcaption></figcaption></figure>

Select the sharing tab, then the advanced sharing button and then in the new popup for advanced sharing select permissions

<figure><img src="../../../.gitbook/assets/image (21).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (22).png" alt=""><figcaption></figcaption></figure>

The SID changes to HR automatically

<figure><img src="../../../.gitbook/assets/image (23).png" alt=""><figcaption></figcaption></figure>

Go back to the security tab and select advanced

<figure><img src="../../../.gitbook/assets/image (24).png" alt=""><figcaption></figcaption></figure>

Enable and disable inheritance again ( I may be wrong about this step)

<figure><img src="../../../.gitbook/assets/image (25).png" alt=""><figcaption></figcaption></figure>

Hit 'add'&#x20;

Select a principle for permission entry pop up menu

<figure><img src="../../../.gitbook/assets/image (26).png" alt=""><figcaption></figcaption></figure>

Enter 'HR' and select okay... I feel like I already did this...

<figure><img src="../../../.gitbook/assets/image (27).png" alt=""><figcaption></figcaption></figure>

But 'modify' and 'write' permissions are missing for the company data folder. I must have only put the permissions for the 'hr' folder and since I disabled the inheritance I have to also modify these permissions back for the parent folder for anyone in the hr group.

<figure><img src="../../../.gitbook/assets/image (28).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (29).png" alt=""><figcaption></figcaption></figure>

Hit okay

Then hit apply and okay

<figure><img src="../../../.gitbook/assets/image (30).png" alt=""><figcaption></figcaption></figure>

Basically hit okay for every menu to get out of all menus.

For the following question, What is the name of the group that is present in the Company Data Share Permissions ACL by default, I believe the answer to this is "Everyone"&#x20;

<figure><img src="../../../.gitbook/assets/image (31).png" alt=""><figcaption></figcaption></figure>

Yolp. I was correct.

<figure><img src="../../../.gitbook/assets/image (32).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (33).png" alt=""><figcaption></figcaption></figure>

The question here is What is the name of the tab that allows you to configure NTFS permissions? I believe the answer is "Security" or "Sharing"

<figure><img src="../../../.gitbook/assets/image (34).png" alt=""><figcaption></figcaption></figure>

It was Security

The third question is What is the name of the service associated with "Windows Update?"

I ran Get-Service in the powershell and got a list of running services:

<figure><img src="../../../.gitbook/assets/image (35).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (36).png" alt=""><figcaption></figcaption></figure>

Looks Like I may have gotten lucky, since there is a windows update service running called wuauserv. I will enter that into the question field and see.

<figure><img src="../../../.gitbook/assets/image (37).png" alt=""><figcaption></figcaption></figure>

Yep, it was correct.

Next question is List the SID associated with the user account Jim you created.

Whelp... I already forgot about that lol.

































