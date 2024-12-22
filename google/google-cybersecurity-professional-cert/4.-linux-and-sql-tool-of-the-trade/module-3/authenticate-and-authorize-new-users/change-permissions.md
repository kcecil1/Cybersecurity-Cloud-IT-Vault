# Change permissions

#### 🛠️ **Changing Permissions in Linux - Fun & ADHD-Friendly Notes** 🎉

Welcome to the world of **changing permissions** in Linux! It may seem like a lot at first, but don't worry—we're breaking it down into simple chunks! Let’s dive in! 🏊‍♂️

***

#### 🔐 **Why Change Permissions?**

In the life of a **security analyst**, you often need to change permissions when:

* A user switches teams or projects
* A user no longer needs access to certain files
* You need to protect files from accidental or deliberate changes

**Permissions** = **Control**! 💪

***

#### 🔧 **Introducing the Command: `chmod`**

* **`chmod`** stands for **change mode**, and it’s the magic command for adjusting permissions on files and directories.

You can think of `chmod` as the **gatekeeper** for files. You can open the gate, close the gate, or change who has the keys to the gate! 🗝️🚪

***

#### 👨‍👩‍👧‍👦 **Types of Users (aka "Who’s the Boss?")**

1. **User (u)**: The file's owner, aka YOU! 🎩
2. **Group (g)**: A team of users (think of your project squad). 👥
3. **Other (o)**: Everyone else who might access the system. 🌎

***

#### ➕➖ **Adding and Removing Permissions (It’s Simple Math!)**

* **`+`** = Add permissions (Let them in! 🟢)
* **`-`** = Take away permissions (Kick them out! 🚫)

***

#### 📝 **Types of Permissions**

1. **Read (r)** 📖: You can view the contents of a file or directory.
2. **Write (w)** ✍️: You can edit or create new content.
3. **Execute (x)** 🚀: You can run a file if it’s a program, or enter a directory.

***

#### 🖊️ **Symbolic Mode – What’s That?!**

Here’s the symbolic format for changing permissions:

* `chmod [who][action][permission] file`

For example:

* `chmod g+w,o-r access.txt`

**Translation**:

* **g+w** → Add **write** permission for **group**
* **o-r** → Remove **read** permission from **others**

***

#### 🔍 **Example Time!**

Let’s break down an example command to make it easy to understand:

```bash
chmod g+w,o-r access.txt
```

* We’re working on a file called **access.txt**.
* We want to **give** the **group (g)** **write** permissions (w).
* We want to **take away** the **other (o)** users' **read** permissions (r).

***

#### 🕵️‍♂️ **Checking Permissions with `ls -l`**

* **`ls -l`** shows the **permissions** of files and directories.
* You'll see something like this: `-rw-r--r--`
  * The first character is the **file type** (like a regular file `-` or a directory `d`).
  * The next **nine** characters show permissions in this order: **user** | **group** | **other**.
  * A **hyphen (-)** means **no permission**!

***

#### 🚨 **The Result**:

* Before the change:
  * Group **only** has **read** permission.
  * Others **can** read the file.
* After the change:
  * Group **now** has **write** permission.
  * Others **no longer** have read permission.

***

#### 💡 **Key Takeaways**

* **`chmod`** lets you **change permissions** for files and directories.
* The **user (u)**, **group (g)**, and **other (o)** can have **read (r)**, **write (w)**, and **execute (x)** permissions.
* Use **`+`** to **add** and **`-`** to **remove** permissions. It's like LEGO blocks—just put the right pieces in place!

***

With some practice, using Linux and `chmod` will feel as natural as breathing. Keep going—you’ve got this! 🌟
