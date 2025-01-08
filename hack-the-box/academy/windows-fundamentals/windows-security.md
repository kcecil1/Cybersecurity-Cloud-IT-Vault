# Windows Security

<figure><img src="../../../.gitbook/assets/image (139).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (140).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (141).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (142).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (143).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (144).png" alt=""><figcaption></figcaption></figure>

I attempted to find the user account folder in the directory but it wasn't present, and looking in lusrmgr tool, his account exists (Bob Smith), but there is no profile path, meaning he most likely never signed in to where the system could create his user folder.

<figure><img src="../../../.gitbook/assets/image (146).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (145).png" alt=""><figcaption></figcaption></figure>

Not really wanting to go that deep in the weeds I checked the academy walkthrough and there was a command I forgot about that can list the system info for an account that hasn't been signed into yet.&#x20;

<figure><img src="../../../.gitbook/assets/image (147).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (148).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (149).png" alt=""><figcaption></figcaption></figure>

Copy and pasted the SID (Security Identifier) into the task field and submitted.

<figure><img src="../../../.gitbook/assets/image (150).png" alt=""><figcaption></figcaption></figure>

#### Step-by-Step Guide: How to Think Through This Problem 🧠💡

***

**1. Understand the Question**

* **What’s being asked?**\
  You need to find out if any **third-party security application** is **disabled at startup** for the current user.
* **Key terms to understand:**
  * **Third-party security app:** Any software not native to Windows but designed for security (e.g., antivirus, firewall).
  * **Startup:** Programs that launch automatically when the user logs in.

***

**2. Break It Down into Subproblems**

* How do I find **startup programs** for the current user?
* How do I identify if a program is **third-party** and **security-related**?
* How do I know if it’s **disabled**?

***

**3. Look for Clues (Think Where the Info Might Be Stored)**

* **Startup entries:** Usually stored in:
  * Windows Registry:
    * `HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run`
    * `HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion\Run`
  * Task Manager Startup tab.
* Disabled programs won’t run at startup but may still exist in these locations.

<figure><img src="../../../.gitbook/assets/image (151).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (152).png" alt=""><figcaption></figcaption></figure>

Hmmm... Looks like the answer could be NordVPN...

<figure><img src="../../../.gitbook/assets/image (153).png" alt=""><figcaption></figcaption></figure>

Seems like in the task manager startup tab that NordVPN is disabled at startup.

<figure><img src="../../../.gitbook/assets/image (154).png" alt=""><figcaption></figcaption></figure>

I submitted the answer, I was correct.

***

***

#### Windows Security Fun-Time: ADHD Edition 🎮

**Windows Security = Big Deal** 🚨

* It’s got LOTS of features = bigger playground 🛝 for attackers.
* Misconfigurations happen easily—even if patched = uh-oh! 🔧❌

**Why Attackers Love It** 🖤

* Built-ins can be abused (yikes). 🛠️🔓
* History of vulnerabilities = super effective exploits! 💥

**Microsoft: "We Got This!"** 💪

* Security upgrades! 🛡️
* New features to block, detect, and defend! 🕵️‍♂️

***

**Meet the Security Principles:** 🌟

* **Who?** Users, computers, threads, processes. 🤖
* **What?** They need permission to act! ✅
* **Why?** Harder for baddies to break in. 🦹‍♀️🚫

***

**SID = Your VIP Pass 🎫**

In cybersecurity, **SID** typically stands for **Security Identifier**. It is a unique value used to identify objects such as users, groups, or computers in Microsoft environments, particularly in Windows operating systems.

* Unique ID for EVERY user. No clones allowed! 🧑‍🤝‍🧑🚫
* Example: SID = "Name Tag" + "Role in Party." 🎉

**SID Breakdown:**

* **Identifier Authority** = Club owner.
* **Relative ID (RID)** = Your special badge. 🎖️

**Active Directory Bonus:** SID = “Domain Name + VIP Code.” 💾🏢

You’re now the Windows security champ! 🏆

<figure><img src="../../../.gitbook/assets/image (64).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

Let's break down the SID piece by piece.

| **Number**                      | **Meaning**          | **Description**                                                                                                                                                                                    |
| ------------------------------- | -------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| S                               | SID                  | Identifies the string as a SID.                                                                                                                                                                    |
| 1                               | Revision Level       | To date, this has never changed and has always been `1`.                                                                                                                                           |
| 5                               | Identifier-authority | A 48-bit string that identifies the authority (the computer or network) that created the SID.                                                                                                      |
| 21                              | Subauthority1        | This is a variable number that identifies the user's relation or group described by the SID to the authority that created it. It tells us in what order this authority created the user's account. |
| 674899381-4069889467-2080702030 | Subauthority2        | Tells us which computer (or domain) created the number                                                                                                                                             |
| 1002                            | Subauthority3        | The RID that distinguishes one account from another. Tells us whether this user is a normal user, a guest, an administrator, or part of some other group                                           |

#### Windows Security: SAM, ACE, ACL & UAC 🚀 ADHD Style!

***

**SAM & ACE: Teamwork Dreamwork 🛠️**

* **SAM** = Grants rights to execute network processes. 🎟️
  * **SAM**: Security Accounts Manager
* **ACE** = Manages who gets access. Think "Access Boss!" 👑
  * **ACE**: Access Control Entry – Specifies who/what gets access.
    * Lives in **ACLs**: Lists saying, "You can touch this. You can't." ✋✅
      * **ACL**: Access Control List – List of ACEs for access management.

***

**ACL = Security Bouncer 💪**

* **DACL**: Who's allowed in? 🤔
  * **DACL**: Discretionary Access Control List – Who can access.
* **SACL**: Who's watching? 👀
  * **SACL**: System Access Control List – Logs who accesses.

Every process/thread = Checked by **LSA** using access tokens. 🎫\
Tokens = Your ID card (SID + security deets). 🆔✨

* **LSA**: Local Security Authority – Validates access tokens.

***

**User Account Control (UAC): Malware's Nemesis 🛡️**

* **UAC**: User Account Control – Prevents unauthorized changes/malware.
* **What it does:** Blocks sneaky stuff like malware. 🕵️‍♂️❌
* **How it works:**
  * Standard users = "Sorry, you can't sit here!" 🙅‍♂️
  * Admin users = "Do you REALLY want to install this?" 🤨

**Consent Prompt = Roadblock:**

* **Malware:** "Let me in!" 🚪
* **UAC:** "Password or confirmation, please." ⛔

***

**Visualize:**

* UAC = A giant STOP sign. 🛑
* Users = Drivers with keys. 🚗🔑

**Congrats! You leveled up in Windows Security! 🎉**

<figure><img src="../../../.gitbook/assets/image (3) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (2) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### Windows Registry: Fun & ADHD-Friendly Dive 🎮🚀

***

**Registry Basics 🛠️**

The **Registry** = The brain of Windows 🧠!

* **What is it?** A database storing all low-level system & app settings. 🗂️
* **Open it:** Type `regedit` in the search bar or command line. 🚪🔓

<figure><img src="../../../.gitbook/assets/image (4) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

***

**Structure = Fancy Tree 🌳**

* **Root Keys (Folders):** Main branches starting with `HKEY`. 🌟
  * Example: `HKEY_LOCAL_MACHINE` (HKLM) = Local system settings.
* **Subkeys (Subfolders):** Smaller branches inside the root keys. 🌿
* **Values (Entries):** Specific settings. 📝

***

**Value Types = Data Flavors 🍦**

Here’s the scoop:

* **REG\_BINARY:** Binary data (010101). 🤖
* **REG\_DWORD:** 32-bit numbers (e.g., 4294967295). 🔢
* **REG\_EXPAND\_SZ:** Strings with variables like `%PATH%`. 📝💡
* **REG\_MULTI\_SZ:** Multiple strings like a list. 📝📝📝
* **REG\_QWORD:** 64-bit numbers (big brain math). 🧠🔢

<figure><img src="../../../.gitbook/assets/image (5) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

***

**Where’s It Stored? 🗄️**

System registry = Files under:\
📁 `C:\Windows\System32\Config`

<figure><img src="../../../.gitbook/assets/image (129).png" alt=""><figcaption></figcaption></figure>

\
User-specific stuff = **HKCU** (HKEY\_CURRENT\_USER) stored in `NTUSER.DAT`. 🏠

<figure><img src="../../../.gitbook/assets/image (130).png" alt=""><figcaption></figcaption></figure>

***

**Run & RunOnce Keys 🏃‍♂️**

Want programs to auto-start?

* **Run Keys:** Apps always start at boot/login. 🚀
  * Example: `HKEY_LOCAL_MACHINE\...\Run`
* **RunOnce Keys:** Apps run once, then gone! 🧹

<figure><img src="../../../.gitbook/assets/image (131).png" alt=""><figcaption></figcaption></figure>

***

**Real-World Examples 🌍**

**Global (all users):**

```bash
reg query HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion\Run
```

<figure><img src="../../../.gitbook/assets/image (132).png" alt=""><figcaption></figcaption></figure>

**Current user:**

```bash
reg query HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run
```

<figure><img src="../../../.gitbook/assets/image (133).png" alt=""><figcaption></figcaption></figure>

***

**Acronym Breakdown:**

* **HKLM:** HKEY Local Machine.
* **HKCU:** HKEY Current User.
* **REG:** Registry Entry Group (not official, but it works!).

***

Congrats, you’re now a Registry Wizard! 🧙‍♂️✨



#### **Application Whitelisting & AppLocker: ADHD-Friendly Crash Course 🎮**

***

**What’s Application Whitelisting? 🛡️**

* **Whitelist = Good List:** Only approved software/apps can run. ✅
* **Goal:** Keep malware & unapproved apps OUT! 🚫🦠
* **Key Idea:** "Zero Trust" — Everything is bad unless it’s allowed. ❌👀✅

***

**Whitelist vs. Blacklist ⚔️**

* **Whitelist:** Only GOOD apps run. (Easier admin life!) 🧙‍♂️
* **Blacklist:** Block BAD apps—but new ones keep showing up! 😤
* **Why Whitelist?** Recommended by NIST (National Institute of Standards and Technology) for high-security setups. 🏢

***

**Challenges of Whitelisting: 🏋️**

* Hard to set up in BIG networks! 🌐
* Solution: Start in **Audit Mode** to test without breaking stuff. 🛠️

***

**Meet AppLocker! 🚪🔒**

* Microsoft’s **App Whitelisting Hero**, introduced in Windows 7. 🦸‍♂️
* Controls who can run:
  * **Executables** 🛠️
  * **Scripts** 📜
  * **Installers** 📦
  * **DLLs** 🔗
  * **Packaged Apps & Installers** 📦🎉

**DLL** - Dynamic Link Library

* A file that contains code and data used by multiple programs simultaneously.

***

**How Does AppLocker Work? 🤓**

* **Rules Based On:**
  * **File Attributes:**
    * Publisher (digital signature).
    * Product/File name & version.
  * **File Path:** Where the app lives. 🏠
  * **File Hash:** Unique fingerprint! 🖐️
* Apply rules to **users** or **groups** (flexible!). 🧑‍🤝‍🧑

***

**Start Smart with AppLocker:**

1. **Audit Mode:** Test rules first. 🧪
2. **Enforce Rules:** When you're confident, lock it down! 🔐

***

🎉 Now you're ready to tackle whitelisting and AppLocker like a pro! 🚀

***

***

#### Local Group Policy: ADHD-Friendly Overview 🎮🔧

***

**What’s Local Group Policy? 🛠️**

* **Purpose:** Lets admins control & configure system settings. 🎛️
* **Where?** Works on individual machines (with or without domains). 🖥️
* **Why?** For tweaking settings or locking down security. 🛡️

***

**How to Open It:**

* Start Menu ➡️ Type `gpedit.msc` ➡️ Boom! You’re in! 🚪🔓

***

**Two Main Sections in Local Group Policy Editor:**

1. **Computer Configuration:** For machine-wide settings. 🖥️
2. **User Configuration:** For settings affecting specific users. 👤

<figure><img src="../../../.gitbook/assets/image (134).png" alt=""><figcaption></figcaption></figure>

***

**Cool Things You Can Do: 😎**

* **Enable Credential Guard:**
  * **Why?** Blocks credential theft attacks. 🕵️‍♀️
  * **How?** Enable **Turn On Virtualization Based Security** under Local Computer Policy.

<figure><img src="../../../.gitbook/assets/image (135).png" alt=""><figcaption></figcaption></figure>

* **Lock It Down:**
  * Restrict app installs or runs. 🚫💾
  * Enforce strong passwords. 🔐
* **Advanced Auditing:** Track who’s doing what! 🕵️
* **Configure AppLocker:** Add whitelisting rules directly! ✅

***

**Why Use Local Group Policy?**

* Access settings you can't touch in the Control Panel. 🤯
* Strengthen security for individual machines. 🔒

***

🎉 **Tip:** Dive in and explore! Local Group Policy is your sandbox for locking down Windows. 🧰✨

***

***

**Windows Defender Antivirus: ADHD-Friendly Breakdown 🎮🛡️**

***

**What Is Windows Defender Antivirus?**

* **AKA:** Built-in, free antivirus for Windows. 💸
* **History:**
  * Started as anti-spyware for **Windows XP**. 🕵️
  * Became **built-in antivirus** with Vista/Server 2008. 🎉
  * Got its current name in **Windows 10 Creators Update**. 🏗️

***

**Key Features You’ll Love! 💖**

1. **Real-Time Protection:** Stops known threats _as they happen_. ⏱️
2. **Cloud-Delivered Protection:**
   * Suspicious files? Sent to the cloud for analysis. ☁️🔍
   * Files are "locked" until deemed safe. 🔒
3. **Tamper Protection:**
   * Blocks sneaky changes via Registry, PowerShell, or Group Policy. 🚫🛠️
4. **Controlled Folder Access:**
   * **Ransomware Protection:** Prevents unauthorized changes to files/folders. 💾🛡️
   * Add exclusions to avoid flagging tools like **pentest scripts**. 🧰

***

**Managing Windows Defender 🧙‍♂️**

* **Control Center:** Access settings, tweak protections. 🎛️
*   **PowerShell Cmdlet:**

    * Use `Get-MpComputerStatus` for a status check! 🖥️

    ```bash
    PS C:\htb> Get-MpComputerStatus | findstr "True"
    ```

    Shows which protections are active (e.g., real-time, tamper). ✅

***

**Why Defender Rocks! 🎸**

* **Great Detection Rates:** Competes with paid antivirus solutions. 🥇
* **No Bloatware:** Unlike some antiviruses, it doesn’t bog your system with extra junk. 🚀

***

**The Fine Print 📜**

* **Not Perfect:**
  * It catches common tools (like Metasploit payloads & Mimikatz). 🐱‍💻
  * Bypassing is still possible, but harder with updates. 🔄
* **Defense-in-Depth:**
  * Use alongside good **patching** & **configurations**—it’s not a magic shield. 🛠️

***

**TL;DR:** Windows Defender = reliable, free, low-bloat antivirus. Use it smartly with other security measures for a rock-solid defense! 🛡️✨

<figure><img src="../../../.gitbook/assets/image (136).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (137).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (138).png" alt=""><figcaption></figcaption></figure>

