# Core commands for navigation and reading files

Let’s turn this video transcript into fun, ADHD-friendly notes! Think of navigating the **Linux file system** like exploring a **forest of directories**. You’re the **adventurer**, and commands are your tools to explore!

***

#### 🌳 **Navigating the Linux File System: Like Exploring a Tree**

* **Imagine a tree** 🌲: It starts with the **roots** (the base), and everything branches out from there. In Linux, the **root directory** is like the trunk of the tree, where everything begins.
  * The **root directory** is represented by a **slash ( / )**.
  * **Subdirectories** are like the branches—they grow from the root and spread out further and further.

***

#### 🔎 **Why This Matters for Security Analysts**

* As a **security analyst**, you need to navigate the file system like an explorer, looking for **logs** and **files** that can help you understand what’s going on with the system.
  * You’ll analyze **log files** to check for **unauthorized access** or to see how applications are being used.

***

#### 🛠️ **Key Commands for Navigating the File System**

Here are the **essential commands** you’ll need to explore the file system:

1. **pwd**: Prints the **working directory** (aka where you are in the file system).
2. **ls**: Lists the **files and directories** in your current directory.
3. **cd**: **Changes directories**—this is how you move between different places in the file system.

***

#### 🔄 **Let’s Try These Commands!**

1. **pwd**: Type this to see where you are. It’s like checking your **location on a map**.
   * Example output: `/home/analyst`
2. **ls**: Use this to **see what’s around you** in the directory. It’s like looking at your surroundings.
   * Example output: `logs/ oldreports/ projects/ reports/ updates.txt`
3. **cd logs**: If you want to move into the **logs** directory to check for unauthorized access, this command will take you there!
   * After that, use `pwd` again to confirm you’re in the **logs** directory.

***

#### 📂 **Reading File Contents: Looking Inside Files**

As a **security analyst**, you’ll need to **read file contents** to find important information, like configuration settings or user access reports.

* **cat**: This command shows the **entire content** of a file—perfect when you need to see everything at once.
* **head**: If the file is too long, use this to only display the **first 10 lines**. It’s like getting a sneak peek before diving deeper.

***

#### 📝 **Example: Using cat and head**

1. Type: `cat access.txt`—this will give you the **full content** of the file.
2. Type: `head access.txt`—this will only show you the **first 10 lines** of the file.

***

#### 🏆 **What You’ve Learned**

* You now know how to **navigate the file system** using commands like `pwd`, `ls`, and `cd`.
* You also know how to **read files** using `cat` and `head`—super helpful for finding info quickly!

***

#### 🔜 **Next Up: Managing the System**

You’ve just taken your first steps into exploring the file system like a true security analyst! Next, we’ll dive into **managing the system** with even more cool commands. 🚀
