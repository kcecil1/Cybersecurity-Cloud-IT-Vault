# Filter Contents

Let's walk through this lesson in an ADHD-friendly way, breaking it down into smaller steps with fun examples and quick exercises to help you practice each command easily. Think of this as a game where you unlock different filtering powers with each tool!

***

#### **1. `more` & `less`: Browsing through Files**

Imagine you're looking at a long document like a treasure map! You can scroll through it using the pagers:

* **`more`**: Lets you see the file page by page. Scroll with spacebar and quit with `q`.
  * Command: `more /etc/passwd`
  * **Practice**: Try scrolling through the `/etc/passwd` file to see all users on the system.
* **`less`**: Like `more`, but even more powerful. Scroll with arrows, search with `/`, and quit with `q`.
  * Command: `less /etc/passwd`
  * **Practice**: Open the file, search for a specific word like "root" by typing `/root`.

***

#### **2. `head` & `tail`: Get a Sneak Peek!**

What if you only want a glimpse of the top or bottom of a file?

* **`head`**: Shows the first 10 lines by default. Think of this as a preview!
  * Command: `head /etc/passwd`
  * **Practice**: Run `head` and see the first few users in `/etc/passwd`.
* **`tail`**: Gives you the last 10 lines. It's like looking at the final scene of a movie!
  * Command: `tail /etc/passwd`
  * **Practice**: Check out the last few users in the system with `tail`.

***

#### **3. `sort`: Organize the Chaos**

Sometimes, things are messy! Let's sort it out, literally.

* **`sort`**: Sorts the lines of a file alphabetically or numerically.
  * Command: `cat /etc/passwd | sort`
  * **Practice**: Use `sort` on `/etc/passwd` to list the users alphabetically.

***

#### **4. `grep`: The Search Master**

Need to find a specific user or something special? This is like using a magnifying glass to zoom in on exactly what you're looking for!

* **`grep`**: Searches for lines that match a pattern.
  * Command: `grep "/bin/bash" /etc/passwd`
  * **Practice**: Find all users who have `/bin/bash` as their shell by searching with `grep`.
* **Exclude results with `-v`**: Let's say you want to exclude all users with a shell like `/bin/false`.
  * Command: `grep -v "false" /etc/passwd`
  * **Practice**: Run this to filter out users who don't have valid shells.

***

#### **5. `cut`: Slice & Dice!**

You can pick out specific pieces of text from each line, like cutting a cake.

* **`cut`**: Extracts specific parts of each line.
  * Command: `cut -d":" -f1 /etc/passwd`
  * **Practice**: Extract just the usernames from `/etc/passwd`.

***

#### **6. `tr`: Switch Things Around**

What if you want to replace certain characters? You can switch them up with `tr`!

* **`tr`**: Replaces characters.
  * Command: `tr ":" " " < /etc/passwd`
  * **Practice**: Replace colons with spaces in `/etc/passwd` to make it more readable.

***

#### **7. `column`: Make It Neat and Tidy!**

Want your data to be displayed like a table? Use `column` to align things neatly.

* **`column`**: Aligns text into columns.
  * Command: `cat /etc/passwd | tr ":" " " | column -t`
  * **Practice**: Run this to format `/etc/passwd` like a tidy table!

***

#### **8. `awk`: A Powerful Sorting Wizard**

Take your sorting powers to the next level. You can use `awk` to grab specific columns!

* **`awk`**: Prints specific columns of text.
  * Command: `awk -F: '{print $1, $3}' /etc/passwd`
  * **Practice**: Use `awk` to display usernames and their UIDs from `/etc/passwd`.

#### This works too:

```bash
awk -F ':' '{print $1, $3}' /etc/passwd
```

#### Explanation:

1. **`-F ':'`**: The `-F` option specifies the field separator for `awk`. In this case, it's a colon (`:`), which is the separator used in `/etc/passwd`.
2. **`'{print $1, $3}'`**: This is the action to be performed for each line of the file. It tells `awk` to print the first field (`$1`, which is the username) and the third field (`$3`, which is the user ID) from each line.
3. **`/etc/passwd`**: This is the input file, which contains information about system users.

Once you run the corrected command, you should see output that shows the usernames and user IDs from the `/etc/passwd` file.

***

#### **9. `sed`: The Ultimate Replacer**

Imagine you’re editing a long scroll and you want to replace a word throughout the whole thing.

* **`sed`**: Finds and replaces text in a file.
  * Command: `sed 's/bash/HTB/g' /etc/passwd`
  * **Practice**: Replace "bash" with "HTB" in `/etc/passwd`.

***

#### **10. `wc`: Count It Up!**

Want to count how many lines or words are in your results? `wc` is your tool!

* **`wc`**: Word count tool (counts lines, words, and characters).
  * Command: `grep "/bin/bash" /etc/passwd | wc -l`
  * **Practice**: Count how many users have `/bin/bash` as their shell.

***

#### **Bonus Challenge!**

Using all these tools, try to complete the following exercises:

1. **Find the username "cry0l1t3"** in `/etc/passwd`.
2. **Display just the usernames** from `/etc/passwd`.
3. **Show "cry0l1t3" and their UID**, separated by a comma.
4. **Display all users with their UID and shell**, separated by commas, and exclude the ones with "nologin" or "false".

Sure! Let's walk through each task one at a time, with explanations and commands to help you understand how to achieve each step.

#### 1. **Find the username "cry0l1t3" in `/etc/passwd`**.

The `/etc/passwd` file contains information about system users, with each line representing a user. To find a specific user, we can use the `grep` command.

**Command:**

```bash
grep "cry0l1t3" /etc/passwd
```

**Explanation:**

* `grep` searches for the string `"cry0l1t3"` in the `/etc/passwd` file.
* This will return the line where the user `cry0l1t3` is defined, which includes their username, password placeholder, user ID (UID), group ID (GID), user info, home directory, and shell.

***

#### 2. **Display just the usernames from `/etc/passwd`**.

To display just the usernames (the first field in `/etc/passwd`), we can use `awk` to print the first field of each line.

**Command:**

```bash
awk -F ':' '{print $1}' /etc/passwd
```

**Explanation:**

* `-F ':'` tells `awk` to use the colon (`:`) as the field separator (which is the delimiter used in `/etc/passwd`).
* `'{print $1}'` tells `awk` to print only the first field, which corresponds to the usernames.

***

#### 3. **Show "cry0l1t3" and their UID, separated by a comma**.

To display both the username `cry0l1t3` and their UID, we need to extract the first field (username) and third field (UID) from `/etc/passwd`, but only for the user `cry0l1t3`. We can use `grep` and `awk` together for this.

**Command:**

```bash
grep "cry0l1t3" /etc/passwd | awk -F ':' '{print $1 "," $3}'
```

**Explanation:**

* `grep "cry0l1t3" /etc/passwd`: Filters out the line for the user `cry0l1t3`.
* `awk -F ':' '{print $1 "," $3}'`: Uses `awk` to print the first field (username) and the third field (UID), separated by a comma.

***

#### 4. **Display all users with their UID and shell, separated by commas, and exclude the ones with "nologin" or "false"**.

We need to:

* Print the first field (username), third field (UID), and seventh field (shell) for all users.
* Exclude users whose shell is `nologin` or `false`.

**Command:**

```bash
awk -F ':' '$7 !~ /(nologin|false)/ {print $1 "," $3 "," $7}' /etc/passwd
```

**Explanation:**

* `-F ':'`: Sets the field separator as a colon (`:`).
* `$7 !~ /(nologin|false)/`: This part of the command filters out lines where the seventh field (shell) contains either `nologin` or `false`.
* `{print $1 "," $3 "," $7}`: Prints the username (field 1), UID (field 3), and shell (field 7), separated by commas.

***

#### Summary of Commands:

1.  **Find username "cry0l1t3"**:

    ```bash
    grep "cry0l1t3" /etc/passwd
    ```
2.  **Display just the usernames**:

    ```bash
    awk -F ':' '{print $1}' /etc/passwd
    ```
3.  **Show "cry0l1t3" and their UID, separated by a comma**:

    ```bash
    grep "cry0l1t3" /etc/passwd | awk -F ':' '{print $1 "," $3}'
    ```
4.  **Display all users with their UID and shell, excluding "nologin" or "false"**:

    ```bash
    awk -F ':' '$7 !~ /(nologin|false)/ {print $1 "," $3 "," $7}' /etc/passwd
    ```

Let me know if you'd like more detailed explanations or if something needs clarification!

***

#### **Practice Makes Perfect!**

The best way to get comfortable with these commands is to play around with them. Try filtering different files, and mix and match tools to become a filtering wizard! Each tool is like unlocking a new superpower in your Linux journey.

Have fun practicing! Let me know if you get stuck!

## Filter Contents

### Question 1

#### "How many services are listening on the target system on all interfaces? (Not on localhost and IPv4 only)"

Students first need to SSH into the spawned target machine using the credentials `htb-student:HTB_@cademy_stdnt!`:

Code: shell

```shell
ssh htb-student@STMIP
```

&#x20; Filter Contents

```shell-session
┌─[eu-academy-2]─[10.10.14.46]─[htb-ac413848@pwnbox-base]─[~]
└──╼ [★]$ ssh htb-student@10.129.141.238

The authenticity of host '10.129.141.238 (10.129.141.238)' 
can't be established. Are you sure you want to continue 
connecting (yes/no/[fingerprint])? Yes
htb-student@10.129.141.238's password:

Welcome to Ubuntu 18.04.5 LTS (GNU/Linux 4.15.0-123-generic x86_64)
<SNIP>
```

Many approaches can be taken to solve this question.

A first approach is whereby students use the `netstat` command with the `-t` (short version of `--tcp`) flag, the `-u` (short version of `--udp`) flag, the `-l` (short version of `--listening`) flag to list listening sockets, and the `-n` flag (short version of `--numeric`) to show numerical addresses instead of trying to determine symbolic hosts, ports or user names:

Code: shell

```shell
netstat -tuln
```

&#x20; Filter Contents

```shell-session
htb-student@nixfund:~$ netstat -tuln

Active Internet connections (only servers)
P. Recv-Q Send-Q Local Add.  Foreign Add. State      
tcp 0      0    0.0.0.0:993  0.0.0.0:*    LISTEN
<SNIP>
udp 0      0    127.0.0.53:53 0.0.0.0:*
```

However, students will notice that there are some sockets listed at the end that are not listening, thus, they need to filter them out using `grep`:

Code: shell

```shell
netstat -tuln | grep 'LISTEN'
```

&#x20; Filter Contents

```shell-session
htb-student@nixfund:~$ netstat -tuln | grep 'LISTEN'

tcp  0  0 0.0.0.0:993     0.0.0.0:*  LISTEN      
tcp  0  0 127.0.0.1:3306  0.0.0.0:*  LISTEN
<SNIP>
```

At last, students need to exclude (filter out) using `grep` any socket that is listening on localhost (i.e. 127.0.0.\*) or uses IPv6, and then use the `wc` command with the `-l` flag to print the number of desired interfaces, which is `7`:

Code: shell

```shell
netstat -tuln | grep 'LISTEN' | grep -v "127.0.0\|tcp6" | wc -l
```

&#x20; Filter Contents

```shell-session
htb-student@nixfund:~$ netstat -tuln | grep 'LISTEN' | grep -v "127.0.0\|tcp6" | wc -l
7
```

///////////////////////////////////////////////////////////////// 2. Determine what user the ProFTPd server is running under. Submit the username as the answer. ////////////////////////////////////////////////////////////////

To determine what user the **ProFTPd server** is running under, you can follow these steps:

#### 1. **Check the ProFTPd Configuration File**

The ProFTPd server usually runs under a specific user, which is defined in its configuration file (`proftpd.conf`). This file is typically located in `/etc/proftpd/` or `/etc/` depending on your system.

You can use the `grep` command to search for the user specified in the configuration file:

**Command:**

```bash
grep -i "User" /etc/proftpd/proftpd.conf
```

**Explanation:**

* `grep -i "User"`: Searches for the line that contains "User" (the user ProFTPd runs as).
* `/etc/proftpd/proftpd.conf`: This is the typical location of the ProFTPd configuration file.

The output should show you the username that the ProFTPd server is running under.

#### 2. **Check Running Processes**

Another way to find out which user ProFTPd is running as is by checking the running processes using the `ps` command:

**Command:**

```bash
ps aux | grep proftpd
```

**Explanation:**

* `ps aux`: Lists all running processes.
* `grep proftpd`: Filters the list to show only processes related to ProFTPd.

The output will include information on the user running the ProFTPd process, which will be listed in the first column.

#### 3. **Submit the Username**

Once you find the username from either of the above steps, submit that as your answer.

Let me know if you need more help with this!

From the output of the `ps aux | grep proftpd` command, you can see the user under which the **ProFTPd server** is running:

```
proftpd   1845  0.0  0.1 126440  3628 ?        Ss   18:32   0:00 proftpd: (accepting connections)
htb-stu+  6351  0.0  0.0  13144  1044 pts/0    S+   19:25   0:00 grep --color=auto proftpd
```

#### How to interpret this:

* The first line represents the **ProFTPd process**.
* The **first column** (`proftpd`) indicates the **user** under which the ProFTPd server is running.

#### Conclusion:

In this case, the ProFTPd server is running under the user `proftpd`.

You can now submit `proftpd` as the answer to the question.

Let me know if you need more clarification!

////////////////////////////////////////////////////////////////////////// Use cURL from your Pwnbox (not the target machine) to obtain the source code of the "https://www.inlanefreight.com" website and filter all unique paths of that domain. Submit the number of these paths as the answer. ////////////////////////////////////////////////////////////////////////// Let's make this fun by imagining you’re a **cyber detective** on a mission to extract hidden paths from a mysterious website! You’ve got some special tools (commands) in your detective kit, and your goal is to gather clues (paths) to uncover hidden secrets.

#### **Step 1: Sneaking into the Website (Fetching the Source Code)**

You're ready to take a look inside the website's source code, but there’s a security guard at the door (SSL/TLS warnings). No worries! You’ve got a special pass (`-k`) to sneak past. And to be stealthy, you want to make sure you’re silent (`-s`).

**Detective Tool:**

```bash
curl https://www.inlanefreight.com -k -s
```

This fetches the **source code** of the website. Think of it as opening a locked journal to see what secrets it holds.

***

#### **Step 2: Decode the Clues (Cleaning the Code)**

The website’s source code has URLs wrapped in **single apostrophes ('')** and **double quotes ("")**. You need to clean up the clues by replacing them with newlines so each clue (URL) appears on a new line for easy reading.

**Detective Tool for Single Apostrophes:**

```bash
curl https://www.inlanefreight.com -k -s | tr "'" "\n"
```

This is like cleaning off the dust on the first set of clues. You’re making sure URLs wrapped in apostrophes get their own line.

**Detective Tool for Double Quotes:**

```bash
curl https://www.inlanefreight.com -k -s | tr "'" "\n" | tr '"' "\n"
```

Now you’ve wiped away the second layer of dust. All URLs, whether in single or double quotes, are now in neat rows for you to inspect.

***

#### **Step 3: Finding the Secret Domain Paths**

Next, you want to focus only on **clues** that lead to **inlanefreight.com**. Time to bring out your magnifying glass (the `grep` command) to zoom in on only the paths that matter.

**Detective Tool:**

```bash
curl https://www.inlanefreight.com -k -s | tr "'" "\n" | tr '"' "\n" | grep "https://www.inlanefreight.com"
```

This tool is like a special filter that grabs only the clues that start with `https://www.inlanefreight.com`. Now you have a list of valuable paths that lead deeper into the mystery.

***

#### **Step 4: Sorting and Counting Unique Clues**

You notice that some clues (paths) may repeat. You don’t want duplicates! So you use your sorting powers to make sure all clues are **unique**. Once sorted, you count them to see how many unique paths you’ve uncovered.

**Detective Tool:**

```bash
curl https://www.inlanefreight.com -k -s | tr "'" "\n" | tr '"' "\n" | grep "https://www.inlanefreight.com" | sort -u | wc -l
```

Here’s what’s happening:

* **`sort -u`**: This sorts the paths and removes duplicates (so you only have unique ones).
* **`wc -l`**: Finally, you count how many unique paths you’ve found.

#### **Mission Complete: You Uncover 34 Hidden Paths!**

You successfully used your detective skills (commands) to find **34 unique paths** hidden in the website’s source code. Case solved!

Let me know if you want to run through another mission! 😄
