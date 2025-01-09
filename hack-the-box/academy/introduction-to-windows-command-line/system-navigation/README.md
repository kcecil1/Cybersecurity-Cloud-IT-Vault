# System Navigation

#### Summary of the Lesson: System Navigation in Command Prompt

This lesson provides foundational knowledge of navigating the Windows filesystem using the Command Prompt, which is crucial for both regular users and cybersecurity professionals. Key concepts and commands covered include:

***

#### **Core Navigation Commands**

1. **Listing Directories (`dir`)**:
   * Displays the contents of the current directory.
   * Can use `/` arguments for advanced search and output options.
2. **Finding the Current Directory (`cd` or `chdir`)**:
   * Running `cd` without arguments shows the current working directory.
3. **Changing Directories (`cd` or `chdir`)**:
   * Navigate using **absolute paths** (e.g., `C:\Users\htb\Pictures`) or **relative paths** (e.g., `.\Pictures`).
   * Use `..\` to move up one or more levels in the directory hierarchy.
4. **Exploring the Filesystem (`tree`)**:
   * `tree` provides a visual listing of directories and subdirectories.
   * Add `/F` to include files in the output.

***

#### **Filesystem Hierarchy Concepts**

* **Root Directory (`C:\`)**:
  * The starting point of the file system, inherited from MS-DOS.
* **Absolute Path**:
  * Specifies a full path from the root to the target directory.
* **Relative Path**:
  * References directories relative to the current working directory.

***

#### **Efficient Navigation Techniques**

* Combine `cd` with `..\..\..` to quickly move up multiple levels.
* Use `tree` for system-wide exploration but be mindful of potentially overwhelming outputs, which can be interrupted with `Ctrl-C`.

***

#### **Interesting Directories for Security Context**

Certain directories are particularly useful or exploitable:

1. **Global Temporary Files (`%SYSTEMROOT%\Temp`)**:
   * Fully accessible to all users, useful for low-privilege activities.
2. **User-Specific Temporary Files (`%TEMP%`)**:
   * Specific to each user, useful for localized reconnaissance or payloads.
3. **Public Directory (`%PUBLIC%`)**:
   * Readily accessible to all users, less likely to be monitored.
4. **Program Files Directories**:
   * Contain installed applications, revealing potential software to exploit.

***

#### **Practical Applications**

* Efficiently navigate and explore the filesystem to identify valuable directories and files.
* Gain familiarity with command-line tools for handling outputs and performing reconnaissance tasks.

By mastering these navigation techniques, users can better understand and interact with the Windows environment, enabling further exploration into system information and cybersecurity practices.

```cmd-session
C:\Users\htb\Desktop> dir
  
 Volume in drive C has no label.
 Volume Serial Number is DAE9-5896

 Directory of C:\Users\htb\Desktop

06/11/2021  11:59 PM    <DIR>          .
06/11/2021  11:59 PM    <DIR>          ..
06/11/2021  11:57 PM                 0 file1.txt
06/11/2021  11:57 PM                 0 file2.txt
06/11/2021  11:57 PM                 0 file3.txt
04/13/2021  11:24 AM             2,391 Microsoft Teams.lnk
06/11/2021  11:57 PM                 0 super-secret-sauce.txt
06/11/2021  11:59 PM                 0 write-secrets.ps1
               6 File(s)          2,391 bytes
               2 Dir(s)  35,102,117,888 bytes free
```

\


```cmd-session
C:\htb> cd 

C:\htb  
```

```cmd-session
C:\htb> cd 

C:\htb  
```



Note: `C:\` is the root directory of all Windows machines and has been determined so since it is inception in the MS-DOS and Windows 3.0 days. The "C:\\" designation was used commonly as typically "A:\\" and "B:\\" were recognized as floppy drives, whereas "C:\\" was recognized as the first internal hard drive of the machine.



**Absolute Path**

&#x20; System Navigation

```cmd-session
C:\htb> cd C:\Users\htb\Pictures

C:\Users\htb\Pictures> 

```

**Relative Path**

&#x20; System Navigation

```cmd-session
C:\htb> cd .\Pictures

C:\Users\htb\Pictures> 
```

We are currently in the `C:\Users\htb\Pictures` directory provided in our previous example. However, we wish to quickly move all the way back to the root of the file system in just one command. To do so, we can perform the following:

&#x20; System Navigation

```cmd-session
C:\Users\htb\Pictures>  cd ..\..\..\

C:\>
```

**Listing the Contents of the File System**

&#x20; System Navigation

```cmd-session
C:\htb\student\> tree

Folder PATH listing
Volume serial number is 26E7-9EE4
C:.
├───3D Objects
├───Contacts
├───Desktop
├───Documents
├───Downloads
├───Favorites
│   └───Links
├───Links
├───Music
├───OneDrive
├───Pictures
│   ├───Camera Roll
│   └───Saved Pictures
├───Saved Games
├───Searches
└───Videos
    └───Captures
```

From a hacker perspective, this can be super useful when searching for files and folders with juicy information we may want, like configurations, project files and folders, and maybe even that holy grail, a file or folder containing passwords. We can utilize the `/F` parameter with the tree command to see a listing of each file and the directories along with the directory tree of the path.

**Tree /F**

&#x20; System Navigation

```cmd-session
C:\htb\student\> tree /F

Folder PATH listing
Volume serial number is 26E7-9EE4
C:.
├───3D Objects
├───Contacts
├───Desktop
│       passwords.txt.txt
│       Project plans.txt
│       secrets.txt
│
├───Documents
├───Downloads
├───Favorites
│   │   Bing.URL
│   │
│   └───Links
├───Links
│       Desktop.lnk
│       Downloads.lnk
│
├───Music
├───OneDrive
├───Pictures
│   ├───Camera Roll
│   └───Saved Pictures
├───Saved Games
├───Searches
│       winrt--{S-1-5-21-1588464669-3682530959-1994202445-1000}-.searchconnector-ms
│
└───Videos
    └───Captures

    <SNIP>
```

From this example, we can quickly get a feel for the system and see some juicy files such as `passwords.txt.txt` and `secrets.txt`. Of course, since this performs a complete listing of every single file and directory on a system, we must be aware of how much output this command will kick up. Later during the module, we will learn a more manageable way of handling the output and working with other command line applications to manipulate it into a much more desirable format. For now, be aware that after attempting to run this command, we should probably interrupt its execution using `Ctrl-C` after retrieving the desired information.

### Interesting Directories

As promised, we have nearly reached the end of this section. With our current skill set, navigating the system should be much more approachable now than initially seemed. Let us take a minute to discuss some directories that can come in handy from an attacker's perspective on a system. Below is a table of common directories that an attacker can abuse to drop files to disk, perform reconnaissance, and help facilitate attack surface mapping on a target host.

| Name:               | Location:                            | Description:                                                                                                                                                                                                                                                                     |
| ------------------- | ------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| %SYSTEMROOT%\Temp   | `C:\Windows\Temp`                    | Global directory containing temporary system files accessible to all users on the system. All users, regardless of authority, are provided full read, write, and execute permissions in this directory. Useful for dropping files as a low-privilege user on the system.         |
| %TEMP%              | `C:\Users\<user>\AppData\Local\Temp` | Local directory containing a user's temporary files accessible only to the user account that it is attached to. Provides full ownership to the user that owns this folder. Useful when the attacker gains control of a local/domain joined user account.                         |
| %PUBLIC%            | `C:\Users\Public`                    | Publicly accessible directory allowing any interactive logon account full access to read, write, modify, execute, etc., files and subfolders within the directory. Alternative to the global Windows Temp Directory as it's less likely to be monitored for suspicious activity. |
| %ProgramFiles%      | `C:\Program Files`                   | folder containing all 64-bit applications installed on the system. Useful for seeing what kind of applications are installed on the target system.                                                                                                                               |
| %ProgramFiles(x86)% | `C:\Program Files (x86)`             | Folder containing all 32-bit applications installed on the system. Useful for seeing what kind of applications are installed on the target system.                                                                                                                               |

The table provided above is by no means an all-encompassing list of all interesting directories on a Windows host. However, these will likely be targeted as they are useful to attackers.



















\
