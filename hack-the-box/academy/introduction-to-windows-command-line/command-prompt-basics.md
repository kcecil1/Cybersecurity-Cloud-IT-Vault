# Command Prompt Basics

Alright! Let's embark on a quirky, ADHD-friendly adventure into the **world of command-line kung fu**! 🥋💻

***

**🥚 Step 1: Meet Cmd.exe, the Command Ninja!** Imagine cmd.exe as your loyal ninja sidekick. It's always there, waiting for your orders, ready to execute commands like a pro. This is your dojo, where you'll practice your first moves. 🥷✨

***

**🚪 Step 2: Enter the Ninja Dojo** To find cmd.exe (a.k.a. the Command Prompt), all you have to do is:

1. Smash that **Start** button on your keyboard or screen. 🎯
2. Type "cmd" (like you're calling your ninja pal) and hit Enter. BOOM, you're in! 🎆

***

**🔍 Step 3: What the Shell is a Shell?!** Think of the shell as a translator between you and your computer. You type commands (your ancient ninja techniques), and the shell turns them into action, like opening files, running programs, or investigating a mysterious system issue. 🕵️‍♂️💻

***

**🏋️‍♂️ White-Belt Training Begins!** Before you master the crazy flips and shadow-jumping moves (a.k.a. advanced commands), let’s start with basics like:

* Typing "help" to see all the cool stuff cmd.exe can do.
* Navigating your computer like a stealthy ninja using "cd" (Change Directory).

**🎉 You’re already leveling up! Go explore, and keep that ninja energy alive!** 🥷💻✨

<figure><img src="../../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

Alright, let’s jazz this up into a fun, ADHD-friendly adventure! ⚡

***

#### **Meet CMD.exe: The OG Command Warrior** 🥋

CMD.exe (aka **The Command Prompt**) is like the Gandalf of Windows—wise, powerful, and always there when you need it. ✨ It's been around forever, learning from its DOS ancestor, **COMMAND.COM**, but still kicking butt in the modern world. 💻

***

#### **What Can CMD Do?**

Think of CMD as your trusty toolbox. It lets you: 🛠️ Change passwords like a tech wizard.\
🌐 Check network statuses and play detective.\
🚀 Run commands _fast_ without fancy graphics slowing you down.

Fun Fact: It’s a _minimalist_ ninja—saving your computer’s memory and CPU power while still being a beast! 🥷

***

#### **CMD vs. PowerShell: The Legacy Showdown!** ⚔️

PowerShell might be the shiny new kid with all the bells and whistles, but CMD is that grizzled veteran who’s _seen some things_. And guess what? It’s still pulling its weight! 💪

***

#### **Quick Story Time!** 📖

Picture this: You're on a pentest mission, ready to break into systems like a hacker spy 🕵️‍♂️. Suddenly, **PowerShell gets blocked** by some strict rules (AppLocker says NOPE 🚫).

What do you do?\
&#xNAN;_&#x53;ummon CMD.exe._

You wield this “ancient” tool to **gain access**, **elevate privileges**, and keep the mission alive. 💼🖤 It’s like finding an old crowbar in a locked dungeon—unexpected, but totally clutch.

***

#### **Pro Tip for Ninjas & Admins** 🧠

Modern systems are full of legacy tools that _admins forget about_. CMD.exe is one of them, and knowing how to use it is like having a skeleton key for digital locks. 🗝️

So, don’t sleep on CMD—master it, and it’ll always have your back! 🎮💻✨

<figure><img src="../../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

Let’s transform this into an ADHD-friendly, fun, and easy-to-grasp walkthrough! 🎉

***

#### **How to Access CMD: The Basics** 🚪

Before we dive into using CMD like a pro, let’s answer the burning question:\
**How do you even get to CMD in the first place?**

It’s simple—but it depends on whether you're working on the computer in person (_local access_) or trying to access it from afar (_remote access_). Let’s break it down!

***

#### **🏠 Local Access: The Hands-On Approach**

This is the “I’m standing right here with the computer” method. You’ve got direct physical control like a boss! 🖥️👊

**Two Quick Ways to Launch CMD:**

1. **The Run Ninja Shortcut:**
   * Press **Windows Key + R**.
   * Type `cmd`, hit Enter. Boom, you’re in! 🎯
2. **The Archaeologist’s Path:**
   * Open **File Explorer**.
   * Navigate to `C:\Windows\System32`.
   * Double-click on **cmd.exe**.\
     (Feeling fancy? Drag it to your taskbar for quick access later!)

***

#### **🌐 Remote Access: The Tech Wizard Way**

This is where you access the machine from another location—kind of like controlling a robot. 🤖 You’ll need the computer to be on the same network or accessible via an internet route.

**Tools to Work Your Magic:**

* **Telnet:** Old-school, but insecure (avoid unless desperate). 😬
* **SSH:** The cool, encrypted option. 🔒
* **PsExec/WinRM:** Power tools for Windows nerds. 🛠️
* **RDP (Remote Desktop Protocol):** Full-screen access like you’re sitting there. 🖥️

***

#### **Scenario Time: Be the Sysadmin Hero!** 🦸‍♂️

Imagine this:\
You’re the system admin. Someone from your company’s branch office in another region calls, saying their computer is acting up. You ask yourself:

1. **Where are they?** Same building, city, or across the globe? 🗺️
2. **Can you walk to them?** If yes, go local. If no, go remote. 🚶‍♂️↔️🌐
3. **Are they online?** If yes, remote tools can help. If no, prepare for some troubleshooting drama. 🎭

***

#### **The Security Catch: Handle With Care!** 🔐

Remote access tools are a sysadmin's dream—until they’re not. If a bad actor gets their hands on valid credentials or finds misconfigurations, they could wreak havoc. 😱

To keep your network safe:

1. **Set strong passwords.** 🛡️
2. **Limit who can use remote tools.** 🚧
3. **Monitor remote access logs.** 👀

***

#### **Summary: Choose Your Access Adventure!** 🎮

* **Local Access:** You’re physically there; launch CMD with ease.
* **Remote Access:** You’re a network ninja using tools to work your magic from afar.
* **Be mindful of security.** Always lock down those remote tools! 🛠️🔒

Now, go forth and launch CMD like the tech wizard you are! 🎩✨

<figure><img src="../../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

Let’s make learning **Command Prompt basics** fun, visual, and action-packed! 🎮✨

***

#### **Navigating the Command Prompt: Walking the Hallways** 🏛️

Think of the Command Prompt as a spooky mansion full of hallways (_directories_) and doors (_files and subdirectories_). Your goal? Explore it like a curious adventurer!

1. **Start in a hallway.** You’re in a directory like `C:\Users\htb\Desktop`.
2. **Look around!** Use the `dir` command to peek behind doors and see what’s in the room.

***

#### **The "dir" Command: Your Detective Glasses 🕵️‍♂️**

When you type `dir` and hit Enter, CMD does its magic:

```plaintext
C:\Users\htb\Desktop> dir
```

👀 **What You’ll See:**

* **Directories (folders):** Represented by `<DIR>`. These are new hallways you can enter!
* **Files:** Things you can interact with—open, edit, or run.

📜 **What the Output Tells You:**

* File and folder names.
* File sizes (in bytes).
* Dates and times files were created or modified.
* The free space on your drive.

It’s like a treasure map to your system! 🗺️

***

#### **Case Study: Windows Recovery Mode** 🛠️

Sometimes, you’re called in for “serious business” troubleshooting—like when a system is broken, locked, or refusing to cooperate. Enter **Recovery Mode**, the secret underground lair of Windows troubleshooting.

**How to Get to Recovery Mode CMD:**

1. Boot from a **Windows installation disc** or recovery media.
2. Choose **Repair Mode** during setup.
3. Select **Command Prompt** from the options.

💡 **Pro Tip:** In Recovery Mode, CMD lets you troubleshoot like a pro—fix file systems, repair boot configurations, and even reset passwords!

***

#### **Hack or Myth: Sticky Keys Exploit** 🕵️‍♂️💻

Here’s where CMD gets spicy. Imagine you’re using Recovery Mode for _creative problem-solving_:

1. Replace the **Sticky Keys** executable (`sethc.exe`) with a copy of `cmd.exe`.
   * This can be done using CMD commands while in Recovery Mode.
2. Reboot the system.
3. At the login screen, press **Shift five times**.

🎉 **Voila!** Instead of Sticky Keys, you get a **Command Prompt with SYSTEM-level permissions**—the ultimate superuser access! 🦸‍♂️

⚠️ **Security Note:** While this is useful for recovery, it’s also a major security risk. Always lock down Recovery Mode access!

***

#### **CMD’s Built-In Help: Your New Best Friend** 🛟

Before moving on to ninja-level commands, remember that CMD loves to help. Use these:

* **`help`**: Lists all available commands.
* **`command /?`**: Explains what a specific command does.

📚 **Example:**

```plaintext
C:\> help dir
Displays a list of files and subdirectories in a directory.
```

***

#### **Ready for More?** 🚀

Now that you’ve mastered the basics of navigation and recovery, get ready to dive deeper into **cmd.exe's built-in help tools**. It’s time to unlock even more command-line kung fu! 🥋💻

<figure><img src="../../../.gitbook/assets/image (156).png" alt=""><figcaption></figcaption></figure>
