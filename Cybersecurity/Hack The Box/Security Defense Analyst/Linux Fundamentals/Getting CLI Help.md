# Getting CLI Help

Alright, let’s take a journey into the magical world of _getting help_ in the terminal—think of it like having a helpful sidekick always by your side on your command-line adventure!

#### 🛠️ **The Command-Line Sidekick: Man Pages & Help Functions**

Imagine you're exploring a new land (i.e., a new tool) that you’ve never seen before. You don’t want to wander aimlessly, so what do you do? You ask for help! Luckily, the terminal has its own "guidebooks" called **man pages** (short for manual) and **help functions**.

**Man Pages: The Complete Guidebook!**

Every tool you use in the terminal comes with a guidebook, and you can open it by typing `man` followed by the tool's name. It’s like opening a scroll filled with ancient wisdom (detailed explanations) about the tool and what it can do.

📝 **Syntax:**

```bash
kcecil1@htb[/htb]$ man <tool>
```

**Example**:\
Let’s say we want to learn about `curl` (a tool for transferring data across the web).

```bash
kcecil1@htb[/htb]$ man curl
```

Getting Help

```shell-session
curl(1)                                                             Curl Manual                                                            curl(1)

NAME
       curl - transfer a URL

SYNOPSIS
       curl [options] [URL...]

DESCRIPTION
       curl  is  a tool to transfer data from or to a server, using one of the supported protocols (DICT, FILE, FTP, FTPS, GOPHER, HTTP, HTTPS,  
       IMAP, IMAPS,  LDAP,  LDAPS,  POP3,  POP3S,  RTMP, RTSP, SCP, SFTP, SMB, SMBS, SMTP, SMTPS, TELNET, and TFTP). The command is designed to work without user interaction.

       curl offers a busload of useful tricks like proxy support, user authentication, FTP upload, HTTP post, SSL connections, cookies, file transfer resume, Metalink,  and more. As we will see below, the number of features will make our head spin!

       curl is powered by libcurl for all transfer-related features.  See libcurl(3) for details.

Manual page curl(1) line 1 (press h for help or q to quit)
```

💡 When you run that command, you’ll see a guidebook open up. It tells you that `curl` can handle all kinds of things like **HTTP, FTP, SSL connections**, and even **cookies**! Who knew your terminal could handle cookies?

But beware! Man pages can get lengthy—like those thick fantasy novels. If it’s too much, don't worry. You can hit **q** anytime to quit. You’re in control.

***

**Help Functions: The Quick Tips!**

Not in the mood for reading long scrolls (man pages)? No problem! There's a **quicker** way to get just the most important details using the `--help` function or `-h` for short. It’s like asking the tool directly for a brief overview of what it can do.

📝 **Syntax:**

```bash
kcecil1@htb[/htb]$ <tool> --help
```

Getting Help

```shell-session
kcecil1@htb[/htb]$ curl --help

Usage: curl [options...] <url>
     --abstract-unix-socket <path> Connect via abstract Unix domain socket
     --anyauth       Pick any authentication method
 -a, --append        Append to target file when uploading
     --basic         Use HTTP Basic Authentication
     --cacert <file> CA certificate to verify peer against
     --capath <dir>  CA directory to verify peer against
 -E, --cert <certificate[:password]> Client certificate file and password
<SNIP>
```

Or the **short version**:

```bash
<tool> -h
```

**Example**:\
If you wanted to see what `curl` can do _without_ reading a whole manual, you'd type:

```bash
curl --help
```

Or the short version:

```bash
curl -h
```

**Example:**

&#x20; Getting Help

```shell-session
kcecil1@htb[/htb]$ curl -h

Usage: curl [options...] <url>
     --abstract-unix-socket <path> Connect via abstract Unix domain socket
     --anyauth       Pick any authentication method
 -a, --append        Append to target file when uploading
     --basic         Use HTTP Basic Authentication
     --cacert <file> CA certificate to verify peer against
     --capath <dir>  CA directory to verify peer against
 -E, --cert <certificate[:password]> Client certificate file and password
<SNIP>
```

Now, you get a neat, concise list of all the tool’s commands. It's like having a cheat sheet in your pocket while you’re coding away! 🌟

***

#### **apropos: The Command Detective! 🔍**

Let’s say you remember part of a command but not the whole thing. What do you do? _apropos_ comes to the rescue! It searches through command descriptions to help you find what you’re looking for, like a detective sniffing out clues.

📝 **Syntax:**

```bash
apropos <keyword>
```

**Example**:\
You want to know more about `sudo` (a command to run things with admin privileges). You'd run:

```bash
apropos sudo
```

**Example:**

&#x20; Getting Help

```shell-session
kcecil1@htb[/htb]$ apropos sudo

sudo (8)             - execute a command as another user
sudo.conf (5)        - configuration for sudo front end
sudo_plugin (8)      - Sudo Plugin API
sudo_root (8)        - How to run administrative commands
sudoedit (8)         - execute a command as another user
sudoers (5)          - default sudo security policy plugin
sudoreplay (8)       - replay sudo session logs
visudo (8)           - edit the sudoers file
```

Your terminal will show you a list of all the `sudo`-related commands, like `sudoers`, `sudoedit`, and more. It’s like flipping through a menu at a restaurant and seeing all the delicious options 🍽️.

***

#### **explainshell: The Command Whisperer**

Lastly, if you’re ever staring at a long command and thinking, “What does this even mean?!” there’s a secret weapon called **explainshell.com**. You can paste any confusing command into it, and it’ll break down each part for you like a wise old wizard explaining a spell.

🔗 **Link**: [explainshell.com](https://explainshell.com)

***

#### **Quick Recap – Your Command-Line Toolkit 🛠️:**

1. **Man Pages (`man <tool>`)**: Full guidebook with all the details.
2. **Help (`<tool> --help` or `<tool> -h`)**: A quick cheat sheet.
3. **apropos (`apropos <keyword>`)**: The detective that finds commands for you.
4. **explainshell**: The online helper to decode long commands.

***

Now, go forth, fellow explorer, and may your terminal journeys be filled with clarity and awesome commands!
