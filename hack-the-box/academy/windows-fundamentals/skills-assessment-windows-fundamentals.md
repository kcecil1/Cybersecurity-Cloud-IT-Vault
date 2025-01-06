# Skills Assessment - Windows Fundamentals

<figure><img src="../../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

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

<figure><img src="../../../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

Above, I used the xfreerdp command to remote into the windows machine.

<figure><img src="../../../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

I created the Company data folder. Right click and select properties.

<figure><img src="../../../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

Selected the sharing tab. Then selected advanced Sharing button

<figure><img src="../../../.gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>

Select "Share this folder"

<figure><img src="../../../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

Select apply then ok

<figure><img src="../../../.gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>

Close out of that popup menu and then open up the company data folder

<figure><img src="../../../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

Created a subfolder named "HR"

<figure><img src="../../../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

Search up and open "computer management app"

<figure><img src="../../../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>

Select local users and groups.&#x20;

<figure><img src="../../../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

Right click on users and select "new user".

<figure><img src="../../../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>

Type in User name and Full name as "Jim" and uncheck "User must change password at next login" per htb's instructions.

<figure><img src="../../../.gitbook/assets/image (18).png" alt=""><figcaption></figcaption></figure>

Create a password and click create&#x20;

<figure><img src="../../../.gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>

Select the Groups folder in the side panel and create a new group called HR

<figure><img src="../../../.gitbook/assets/image (20).png" alt=""><figcaption></figcaption></figure>

Double click on HR and select 'add' and input Jim to the HR group

<figure><img src="../../../.gitbook/assets/image (21).png" alt=""><figcaption></figcaption></figure>

You can type the name in the field and select check names to select the actual user&#x20;

<figure><img src="../../../.gitbook/assets/image (22).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (23).png" alt=""><figcaption></figcaption></figure>

Hit Ok, apply ok, all that.

<figure><img src="../../../.gitbook/assets/image (24).png" alt=""><figcaption></figcaption></figure>

Go back to the company data folder and right click, select properties, sharing tab and then advanced sharing.

<figure><img src="../../../.gitbook/assets/image (25).png" alt=""><figcaption></figcaption></figure>



















