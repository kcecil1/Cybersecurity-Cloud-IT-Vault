Imagine you’re on an epic space adventure, hopping between planets (directories), piloting your ship (terminal), and constantly needing updates from your control center (the bash prompt). Your control center tells you essential things, like where you are, what your ship’s name is, and which brave astronaut (user) is at the helm.

When you first log in, your control center gives you a pretty basic status report:

**`<username>@<hostname>:<current directory> $`**

- **username** is YOU, the pilot (or astronaut, if you prefer).
- **hostname** is your spaceship's cool name.
- **current directory** is the planet or space station you’re on right now (which folder you’re in).

Let’s say you’ve landed at your home planet (home directory). Instead of showing you the full coordinates, your control center smartly shows a little `~`. You get this when you’re in familiar territory:

**`<username>@<hostname> [~] $`**

### The Symbols of Power
When you’re a regular space traveler, the prompt ends with a `$`, meaning, “Hey, you’re good, but don’t get too crazy with your commands.”

But… when you enter *super astronaut* mode, also known as **root** (the admin), your prompt ends with a mighty `#`, showing you’re in charge of EVERYTHING in the galaxy. Look out!

**`root@spaceship [/galaxy] #`**

---

### A Little Customization Goes a Long Way
Your control center (bash prompt) can do more than just show basic info. Let’s upgrade it with some awesome features, like adding the current time or even the system’s IP address. These things help when you’re working on missions (like penetration tests) where timing and location matter.

You can tweak the prompt to show these neat extras using **special characters** like:
- `\u` – shows your username (who’s flying the ship).
- `\h` – shows your spaceship's name (hostname).
- `\w` – gives the full coordinates of your location (full path).

You can even add timestamps to track when you did things!
- `\t` – current time in 24-hour format (space travelers use this).
- `\@` – current time in 12-hour format (for the Earth-bound folks).

Imagine your prompt looking like this:
**`<username>@<hostname> [<full path>] <time> $`**

Now, you’ll always know who you are, where you are, and what time it is!

### Colors and Bling for Your Space Station!
Just like how a cool spaceship isn’t complete without some flashy lights and colors, you can add *themes* and *colors* to your terminal. This makes it easier to see what’s important and just makes your terminal look cooler while you’re zipping around the galaxy.

---

### But Wait, There's More! The Bash Prompt as a Tool
Think of your bash prompt like a multi-tool in space. You can use it to:
- Track your **IP address** (know which planet/system you're hacking).
- Show the **status of your last command** (was the mission successful?).
- Display the **number of jobs** your terminal is managing (how many missions are running in the background).

Your prompt can be customized in the `.bashrc` file, where you can play around and test how you want it to look. Want to be even fancier? Use tools like **bash-prompt-generator** or **powerline** to make your bash prompt look as advanced as the command center on a starship.

---

And there you have it—your bash prompt is like the heads-up display in your spaceship, showing you critical info at all times, and making sure you’re ready to run commands, jump to new systems, or complete your hacking missions in style. Happy space travels!

Prompt Description

```shell-session
<username>@<hostname><current working directory>$
```

  
Prompt Description

```shell-session
<username>@<hostname>[~]$
```

Prompt Description

```shell-session
root@htb[/htb]#
```

### Unprivileged - User Shell Prompt

  Prompt Description

```shell-session
$
```

### Privileged - Root Shell Prompt

  Prompt Description

```shell-session
#
```

|**Special Character**|**Description**|
|---|---|
|`\d`|Date (Mon Feb 6)|
|`\D{%Y-%m-%d}`|Date (YYYY-MM-DD)|
|`\H`|Full hostname|
|`\j`|Number of jobs managed by the shell|
|`\n`|Newline|
|`\r`|Carriage return|
|`\s`|Name of the shell|
|`\t`|Current time 24-hour (HH:MM:SS)|
|`\T`|Current time 12-hour (HH:MM:SS)|
|`\@`|Current time|
|`\u`|Current username|
|`\w`|Full path of the current working directory|
