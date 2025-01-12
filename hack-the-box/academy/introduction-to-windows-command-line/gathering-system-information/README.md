# Gathering System Information

**Windows Host Enumeration: The ADHD-Friendly Treasure Hunt Edition!**

***

#### 🎯 **What’s the Mission?**

You’re now a digital treasure hunter, tasked with exploring and understanding your computer like a pro hacker or defender! Your goal: **uncover system secrets, map the environment, and plan your next move.** Let’s make it fun, quick, and practical!

***

### 🌍 **Step 1: Know the Terrain**

Imagine you’ve landed on a mysterious island (your computer). Before you start digging for treasure, you need a map! Here's what to find:

1. **General System Info:** What’s this island? (Hostname, OS version, patches, etc.)
2. **Networking Info:** Who are its neighbors? (IP address, gateways, subnets)
3. **User Info:** Who’s here? (Users, groups, permissions)
4. **Shares & Resources:** Where’s the loot? (Shared folders, network access)

***

### 🧭 **Step 2: Gather System Info with Command Prompts**

#### 🖥️ **General System Info: Who Are You?**

1.  **`systeminfo`** – _The all-knowing oracle of info!_

    * Outputs your hostname, OS version, patches, and more.

    ```bash
    systeminfo
    ```

    Example gems you’ll find:

    * Host Name: DESKTOP-X
    * OS Name: Windows 10 Pro
    * Installed Hotfixes: (security patches)
2.  **`hostname`** – _Quickly find your island’s name._

    ```bash
    hostname
    ```
3.  **`ver`** – _Your OS version at a glance!_

    ```bash
    ver
    ```

***

#### 🌐 **Networking Info: Mapping the Neighborhood**

1.  **`ipconfig`** – _Spy on your network connections._

    * Shows your IP address, gateway, and DNS.

    ```bash
    ipconfig
    ```
2.  **`arp -a`** – _Who’s visited the island?_

    * Lists other devices your computer has communicated with.

    ```bash
    arp -a
    ```
3.  **Bonus:** **`netstat`** – _Current connections and open ports._

    ```bash
    netstat -ano
    ```

***

#### 🧑‍💻 **User Info: Who’s on the Island?**

1.  **`whoami`** – _Who are you logged in as?_

    ```bash
    whoami
    ```
2.  **`whoami /priv`** – _What cool powers (privileges) do you have?_

    ```bash
    whoami /priv
    ```
3.  **`whoami /groups`** – _What tribes (groups) are you part of?_

    ```bash
    whoami /groups
    ```
4.  **`net user`** – _Lists all user accounts on the island._

    ```bash
    net user
    ```

***

#### 💼 **Shares & Resources: Where’s the Treasure?**

1.  **`net share`** – _Lists local shares on the host._

    ```bash
    net share
    ```
2.  **`net view`** – _Peek at all shared resources across the network._

    ```bash
    net view
    ```

***

### 🧩 **Step 3: Puzzle Pieces = Map**

Now that you’ve gathered the info, put it together:

* **Host Info:** Does the OS have known vulnerabilities?
* **Network Info:** What devices could be allies or threats?
* **User Info:** Are there admin accounts you can escalate to?
* **Resources:** Are there shared folders with juicy info?

***

### 🚀 **Pro Tips: Make it Efficient!**

* Use **single commands** for maximum stealth. Example: `systeminfo` = instant goldmine.
* Use piping and filtering for targeted searches:
  * `systeminfo | find "OS Version"` – Only show the OS version.
  * `netstat -ano | find "LISTEN"` – Show only listening ports.

***

### 🎮 **Gamify the Process!**

* **Set a Timer:** Can you find the hostname, IP, and a shared resource in 5 minutes?
* **Score Points:** +10 for finding a patch, +20 for finding admin privileges!
* **Avoid the Traps:** Don’t raise suspicions by running too many commands too quickly.

***

### 🏆 **Victory Lap: Why Enumeration Rocks**

* **Hackers (Red Team):** Find entry points, vulnerabilities, or ways to escalate privileges.
* **Defenders (Blue Team):** Spot misconfigurations, ensure security, and understand your environment better.

***

#### 🐾 **Next Steps**

Congrats, treasure hunter! You’ve mapped your island and its surroundings. In the next adventure, we’ll learn how to dig deeper into **specific files and directories.** Keep the energy up and snacks nearby—your journey has just begun! 🎉

