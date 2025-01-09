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
