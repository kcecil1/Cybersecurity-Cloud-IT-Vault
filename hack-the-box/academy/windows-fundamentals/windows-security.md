# Windows Security

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

<figure><img src="../../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

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

<figure><img src="../../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

#### Windows Registry: Fun & ADHD-Friendly Dive 🎮🚀

***

**Registry Basics 🛠️**

The **Registry** = The brain of Windows 🧠!

* **What is it?** A database storing all low-level system & app settings. 🗂️
* **Open it:** Type `regedit` in the search bar or command line. 🚪🔓

<figure><img src="../../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

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

<figure><img src="../../../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

***

**Where’s It Stored? 🗄️**

System registry = Files under:\
📁 `C:\Windows\System32\Config`\
User-specific stuff = **HKCU** (HKEY\_CURRENT\_USER) stored in `NTUSER.DAT`. 🏠

***

**Run & RunOnce Keys 🏃‍♂️**

Want programs to auto-start?

* **Run Keys:** Apps always start at boot/login. 🚀
  * Example: `HKEY_LOCAL_MACHINE\...\Run`
* **RunOnce Keys:** Apps run once, then gone! 🧹

***

**Real-World Examples 🌍**

**Global (all users):**

```bash
reg query HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion\Run
```

**Current user:**

```bash
reg query HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run
```

***

**Acronym Breakdown:**

* **HKLM:** HKEY Local Machine.
* **HKCU:** HKEY Current User.
* **REG:** Registry Entry Group (not official, but it works!).

***

Congrats, you’re now a Registry Wizard! 🧙‍♂️✨
