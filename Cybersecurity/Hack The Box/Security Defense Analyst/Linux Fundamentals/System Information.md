Alright, let's dive into learning about **system information** on Linux, but with a twist! We’ll turn this into a fun RPG-style adventure where you’re the system admin on a mission to gather intel on your Linux environment!

### 🌟 **Mission: Gather Intel on Your System** 🌟

Your mission, should you choose to accept it, is to uncover crucial information about the Linux system you’ve infiltrated. You’ll need to use the following commands as your toolkit to find out who you are, what system you're on, and how to connect remotely. Let’s embark on this journey!

|**Command**|**Description**|
|---|---|
|`whoami`|Displays current username.|
|`id`|Returns users identity|
|`hostname`|Sets or prints the name of current host system.|
|`uname`|Prints basic information about the operating system name and system hardware.|
|`pwd`|Returns working directory name.|
|`ifconfig`|The ifconfig utility is used to assign or to view an address to a network interface and/or configure network interface parameters.|
|`ip`|Ip is a utility to show or manipulate routing, network devices, interfaces and tunnels.|
|`netstat`|Shows network status.|
|`ss`|Another utility to investigate sockets.|
|`ps`|Shows process status.|
|`who`|Displays who is logged in.|
|`env`|Prints environment or sets and executes command.|
|`lsblk`|Lists block devices.|
|`lsusb`|Lists USB devices|
|`lsof`|Lists opened files.|
|`lspci`|Lists PCI devices.|
---

### **Character Sheet: Your Command Arsenal**

#### 🎭 **Who am I? (whoami)**
Imagine you've teleported onto an unknown spaceship (system). One of the first things you need to do is figure out your identity. Are you a regular crew member or someone with special privileges?

Use this command to find out:
```bash
whoami
```
*Result:* It will display your current username—your **in-game identity**!

---

#### 🆔 **What’s My Full Profile? (id)**
Now that you know who you are, let’s dive deeper into your identity. Maybe you’re part of a special group (admin privileges) that gives you access to more powerful features!

Run:
```bash
id
```
This will give you your **UID (User ID)** and **GID (Group ID)**, plus a list of all groups you belong to. If you're part of the **sudo** group, it means you have the power of root, the most powerful entity in the game!

  
System Information

```shell-session
cry0l1t3@htb[/htb]$ id

uid=1000(cry0l1t3) gid=1000(cry0l1t3) groups=1000(cry0l1t3),1337(hackthebox),4(adm),24(cdrom),27(sudo),30(dip),46(plugdev),116(lpadmin),126(sambashare)
```
---

#### 🖥️ **What's the Ship’s Name? (hostname)**
Next, you need to know the name of the ship (system) you're on. Every ship has a name, and you can reveal it with this simple spell:

```bash
hostname
```
Now you know the **hostname** (or spaceship name) you’ve landed on.

---

#### 🛡️ **Which Operating System is Protecting the Ship? (uname)**
It’s time to discover what kind of operating system this ship runs. This command will show you whether you’re dealing with Linux, Windows, or something else entirely.

Use the command:
```bash
uname
```

#### Uname

Let's dig into the `uname` command a bit more. If we type `man uname` in our terminal, we will bring up the man page for the command, which will show the possible options we can run with the command and the results.

  System Information

```shell-session

UNAME(1)                                    User Commands                                   UNAME(1)

NAME
       uname - print system information

SYNOPSIS
       uname [OPTION]...

DESCRIPTION
       Print certain system information.  With no OPTION, same as -s.

       -a, --all
              print all information, in the following order, except omit -p and -i if unknown:

       -s, --kernel-name
              print the kernel name

       -n, --nodename
              print the network node hostname

       -r, --kernel-release
              print the kernel release

       -v, --kernel-version
              print the kernel version

       -m, --machine
              print the machine hardware name

       -p, --processor
              print the processor type (non-portable)

       -i, --hardware-platform
              print the hardware platform (non-portable)

       -o, --operating-system
```

#### Uname to Obtain Kernel Release
For more details, run:
```bash
uname -a
```
This will give you **everything** about the system—kernel version, hardware architecture, and more.

Running `uname -a` will print all information about the machine in a specific order: kernel name, hostname, the kernel release, kernel version, machine hardware name, and operating system. The `-a` flag will omit `-p` (processor type) and `-i` (hardware platform) if they are unknown.

  System Information

```shell-session
cry0l1t3@htb[/htb]$ uname -a

Linux box 4.15.0-99-generic #100-Ubuntu SMP Wed Apr 22 20:32:56 UTC 2020 x86_64 x86_64 x86_64 GNU/Linux
```

From the above command, we can see that the kernel name is `Linux`, the hostname is `box`, the kernel release is `4.15.0-99-generic`, the kernel version is `#100-Ubuntu SMP Wed Apr 22 20:32:56 UTC 2020`, and so on. Running any of these options on their own will give us the specific bit output we are interested in.

  System Information

```shell-session
cry0l1t3@htb[/htb]$ uname -a

Linux box 4.15.0-99-generic #100-Ubuntu SMP Wed Apr 22 20:32:56 UTC 2020 x86_64 x86_64 x86_64 GNU/Linux
```

#### Uname to Obtain Kernel Release

Suppose we want to print out the kernel release to search for potential kernel exploits quickly. We can type `uname -r` to obtain this information.

  System Information

```shell-session
cry0l1t3@htb[/htb]$ uname -r

4.15.0-99-generic
```

With this info, we could go and search for "4.15.0-99-generic exploit," and the first [result](https://www.exploit-db.com/exploits/47163) immediately appears useful to us.

It is highly recommended to study the commands and understand what they are for and what information they can provide. Though a bit tedious, we can learn much from studying the manpages for common commands. We may even find out things that we did not even know were possible with a given command. This information is not only used for working with Linux. However, it will also be used later to discover vulnerabilities and misconfigurations on the Linux system that may contribute to privilege escalation. Here are a few optional exercises that we can solve for practice purposes, which will help us become familiar with some of the commands.

---

#### 📂 **Where Am I? (pwd)**
Your current location (directory) is important to know when navigating a new system. This is where the **pwd** command comes in handy:

```bash
pwd
```
It shows you exactly **where** you are in the directory tree. You wouldn’t want to get lost on a spaceship!

---

### **Networking Adventure: Who's Online?**

#### 🌐 **Who Else Is Onboard? (who)**
Before exploring the ship's network, check out who else is logged in. Maybe there are other players (users) on the ship!

Use:
```bash
who
```
You’ll get a list of **all logged-in users**, giving you a better idea of the crew.

---

#### 🛠️ **Set Up Your Network: ifconfig & ip**
Now that you’ve gained system access, you need to understand the **network configuration**.

- To view or configure network interfaces, run:
```bash
ifconfig
```
This reveals your **IP addresses** and network devices. Alternatively, use the **ip** command for more detailed control:
```bash
ip addr
```

Both of these will help you understand how the spaceship’s **networking systems** are set up!

---

#### 🕵️ **Track Network Activity: netstat & ss**
Maybe you want to track **network traffic** or see what **sockets** are in use.

- **netstat** is your go-to for network status:
```bash
netstat
```

- **ss** is another utility for investigating **sockets** and their connections:
```bash
ss
```

These commands allow you to monitor how the spaceship communicates with the **outside world**.

---

### **System Resources: Keep an Eye on Processes**

#### ⚙️ **What's Running in the Background? (ps)**
You need to know what’s running on the system. Is there a rogue process using up all your resources?

Use the **ps** command to see the list of active processes:
```bash
ps
```
It’s like checking the ship’s **system dashboard** for performance stats.

---

#### 💾 **Block Devices & Storage (lsblk, lsusb, lspci)**
Understanding the system's hardware is important. Use these commands to list various devices:

- **lsblk**: Lists all **block devices** (storage devices).
```bash
lsblk
```

- **lsusb**: Lists all connected **USB devices**.
```bash
lsusb
```

- **lspci**: Lists all **PCI devices** (connected cards like network or video cards).
```bash
lspci
```

---

### **System Monitoring: Open Files & Environment**

#### 📜 **List Open Files (lsof)**
Want to know what files are currently being used or accessed? Use the **lsof** command:
```bash
lsof
```
This shows a **list of open files** and which processes are using them.

---

#### 🌍 **Environment Variables (env)**
The **env** command lets you see your environment variables, a set of dynamic values that affect the way running processes behave on the system.

Run:
```bash
env
```
You’ll see a list of variables controlling your **user settings**, paths, and configurations.

---

### **Secret Weapon: SSH Login**

To connect remotely to other systems, you’ll need to use **SSH** (Secure Shell), the **teleportation device** for sysadmins.

📝 **Command:**
```bash
ssh <username>@<IP address>
```

This is how you **jump from one ship to another** and configure them from afar. It’s your ticket to remote exploration!

---

### 🎮 **Final Boss: Know Your Commands!**
You now have a toolkit of commands to gather all kinds of system information. But the real mastery comes from **knowing how to use them together**. For deeper insight into any command, check out its **man page** by typing:
```bash
man <command>
```

**Bonus Tip**: If a command is too long and confusing, head over to **explainshell.com** to get a full breakdown!

---

**Mission Accomplished!** 🚀 Now you’re ready to explore any Linux system, gather intel, and conquer the network. Keep practicing with these commands, and soon enough, you’ll be the supreme system admin of your space station!

## Logging In via SSH

`Secure Shell` (`SSH`) refers to a protocol that allows clients to access and execute commands or actions on remote computers. On Linux-based hosts and servers running or another Unix-like operating system, SSH is one of the permanently installed standard tools and is the preferred choice for many administrators to configure and maintain a computer through remote access. It is an older and very proven protocol that does not require or offer a graphical user interface (GUI). For this reason, it works very efficiently and occupies very few resources. We use this type of connection in the following sections and in most of the other modules to offer the possibility to try out the learned commands and actions in a safe environment. We can connect to our targets with the following command:

#### SSH Login

  System Information

```shell-session
kcecil1@htb[/htb]$ ssh [username]@[IP address]
```

VPN Servers

Warning: Each time you "Switch", your connection keys are regenerated and you must re-download your VPN connection file.

All VM instances associated with the old VPN Server will be terminated when switching to a new VPN server.  
Existing PwnBox instances will automatically switch to the new VPN server.

 US Academy 1 US Academy 4 US Academy 5 US Academy 2 EU Academy 3 US Academy 6 US Academy 3 EU Academy 1 EU Academy 4 EU Academy 5 EU Academy 6 EU Academy 2 

US Academy 4

![](https://academy.hackthebox.com/images/sparkles-solid.svg)Recommended

low Load

PROTOCOL

UDP 1337

TCP 443

DOWNLOAD VPN CONNECTION FILE

# Connect to Pwnbox

Your own web-based Parrot Linux instance to play our labs.

Pwnbox Location

UK110ms

Terminate Pwnbox to switch location

  Full Screen  Terminate   Reset 

Life Left: 99m

Connected to htb-haq5bim4cb:1 (htb-ac-1239954)

Enable step-by-step solutions for all questions

#### Questions

Answer the question(s) below to complete this Section and earn cubes!

Target(s): Click here to spawn the target system!  

Cheat Sheet

[

Download VPN Connection File

](https://academy.hackthebox.com/vpn/key)

 SSH to with user "htb-student" and password "HTB_@cademy_stdnt!"

+ 0  Find out the machine hardware name and submit it as the answer.

+10 Streak pts

 Submit

 Hint

+ 1  What is the path to htb-student's home directory?

+10 Streak pts

 Submit

+ 0  What is the path to the htb-student's mail?

+10 Streak pts

 Submit

+ 0  Which shell is specified for the htb-student user?

+10 Streak pts

 Submit

+ 0  Which kernel version is installed on the system? (Format: 1.22.3)

+10 Streak pts

 Submit

+ 1  What is the name of the network interface that MTU is set to 1500?

+10 Streak pts

 Submit

 [Previous](https://academy.hackthebox.com/module/18/section/67)

[Next](https://academy.hackthebox.com/module/18/section/75) 

 Cheat Sheet [Go to Questions](https://academy.hackthebox.com/module/18/section/70#questionsDiv)

##### Table of Contents

###### Introduction

[Linux Structure](https://academy.hackthebox.com/module/18/section/94)[Linux Distributions](https://academy.hackthebox.com/module/18/section/2091)[Introduction to Shell](https://academy.hackthebox.com/module/18/section/65)

###### The Shell

[Prompt Description](https://academy.hackthebox.com/module/18/section/66)[Getting Help](https://academy.hackthebox.com/module/18/section/67)  [System Information](https://academy.hackthebox.com/module/18/section/70)

###### Workflow

  [Navigation](https://academy.hackthebox.com/module/18/section/75)  [Working with Files and Directories](https://academy.hackthebox.com/module/18/section/78)  [Editing Files](https://academy.hackthebox.com/module/18/section/93)  [Find Files and Directories](https://academy.hackthebox.com/module/18/section/81)  [File Descriptors and Redirections](https://academy.hackthebox.com/module/18/section/79)  [Filter Contents](https://academy.hackthebox.com/module/18/section/80)  [Regular Expressions](https://academy.hackthebox.com/module/18/section/2092)  [Permission Management](https://academy.hackthebox.com/module/18/section/83)

###### System Management

  [User Management](https://academy.hackthebox.com/module/18/section/71)  [Package Management](https://academy.hackthebox.com/module/18/section/72)  [Service and Process Management](https://academy.hackthebox.com/module/18/section/73)  [Task Scheduling](https://academy.hackthebox.com/module/18/section/2093)  [Network Services](https://academy.hackthebox.com/module/18/section/2094)  [Working with Web Services](https://academy.hackthebox.com/module/18/section/74)  [Backup and Restore](https://academy.hackthebox.com/module/18/section/2095)  [File System Management](https://academy.hackthebox.com/module/18/section/2096)  [Containerization](https://academy.hackthebox.com/module/18/section/2097)

###### Linux Networking

  [Network Configuration](https://academy.hackthebox.com/module/18/section/2098)[Remote Desktop Protocols in Linux](https://academy.hackthebox.com/module/18/section/1776)

###### Linux Hardening

[Linux Security](https://academy.hackthebox.com/module/18/section/98)  [Firewall Setup](https://academy.hackthebox.com/module/18/section/2099)  [System Logs and Monitoring](https://academy.hackthebox.com/module/18/section/2100)

###### Linux Distributions vs Solaris

[Solaris](https://academy.hackthebox.com/module/18/section/2101)

###### Tips & Tricks

[Shortcuts](https://academy.hackthebox.com/module/18/section/82)

##### My Workstation

  Interact   Terminate