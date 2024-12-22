# Reference guide, Linux

It looks like I missed some commands! Let's include everything properly this time in the same fun and ADHD-friendly style. Here’s the complete reference guide:

***

## **Linux: Cybersecurity Command Superpowers! 🌟**

### **Table of Awesomeness**

1. Navigate the file system 🧭
2. Read files 📜
3. Manage the file system 🛠️
4. Filter content 🔍
5. Manage users and permissions 👤
6. Get help in Linux 🚑

***

#### **1. Navigate the File System 🧭**

Explore your way through the Linux jungle!

* **`cd` – Change Directions!**
  * `cd reports` -> Jump into the **reports** folder!
  * `cd /home/analyst/reports` -> Full path teleport to **reports**!
  * `cd ..` -> Go back one folder!
* **`ls` – Look Stuff Up!**
  * `ls` -> What's in this folder?
  * `ls /home/analyst/reports` -> Peek into the **reports** folder!
  * `ls -a` -> Check out **hidden** files!
  * `ls -l` -> Spy on file permissions, owners, and more!
  * `ls -la` -> Get **ALL** the details, including hidden files!
* **`pwd` – Where Am I?**
  * Type `pwd` to **show your location** in the Linux labyrinth!
* **`whoami` – Who’s the Boss?**
  * Type `whoami` to find out your **username**!

***

#### **2. Read Files Like a Pro 📜**

Get the scoop on what’s inside!

* **`cat` – Cat's Outta the Bag!**
  * `cat updates.txt` -> Reveal the entire **updates.txt** file!
* **`head` – Just the Beginning**
  * `head updates.txt` -> Show me the first **10 lines**!
  * `head -n 5 updates.txt` -> Or just give me the first **5 lines**!
* **`less` – Scroll at Your Pace!**
  * `less updates.txt` -> Scroll through **updates.txt** calmly.
* **`tail` – The Grand Finale!**
  * `tail updates.txt` -> Show the last **10 lines**!
  * `tail -n 5 updates.txt` -> Or just the last **5 lines**!

***

#### **3. Manage the File System 🛠️**

You’re the architect of your file kingdom!

* **`cp` – Copy-Paste Master!**
  * `cp permissions.txt /home/analyst/logs` -> Copy the **permissions.txt** file to the **logs** folder!
* **`mkdir` – Create Your Own Folders!**
  * `mkdir network` -> Make a new **network** folder!
  * `mkdir /home/analyst/logs/network` -> Create a folder inside **logs**!
* **`mv` – Move (or Rename) Like a Pro!**
  * `mv permissions.txt /home/analyst/logs` -> Move **permissions.txt** to **logs**!
  * `mv permissions.txt perm.txt` -> Rename **permissions.txt** to **perm.txt**!
* **`nano` – Edit Files in a Snap!**
  * `nano permissions.txt` -> Open or create **permissions.txt** in the **nano** editor!
* **`rm` – Bye Bye Files!**
  * `rm permissions.txt` -> Delete **permissions.txt**!
  * `rmdir network` -> Remove the empty **network** folder!
* **`touch` – Create New Files Instantly!**
  * `touch newfile.txt` -> Create a new empty file called **newfile.txt**!

***

#### **4. Filter Content 🔍**

Find what you're looking for like a detective!

* **`find` – Find All the Things!**
  * `find /home/analyst/projects` -> Find everything in the **projects** folder!
  * `find /home/analyst/projects -name "*log*"` -> Look for files with **log** in the name!
  * `find /home/analyst/projects -mtime -3` -> Find files modified in the **last 3 days**!
* **`grep` – Hunt Down Specific Lines!**
  * `grep OS updates.txt` -> Find all lines with **OS** in **updates.txt**!
* **`|` – Pipe Power!**
  * `ls /home/analyst/reports | grep users` -> List all files containing **users**!

***

#### **5. Manage Users & Permissions 👤**

Be the ruler of user privileges!

* **`chmod` – Change Permissions!**
  * `chmod u+rwx,g+rwx,o+rwx file.txt` -> Give **everyone** full permissions on **file.txt**!
  * `chmod g-rw bonuses.txt` -> Remove group **read/write** permissions on **bonuses.txt**!
* **`chown` – Own It!**
  * `sudo chown fgarcia file.txt` -> Change owner of **file.txt** to **fgarcia**!
* **`groupdel` – Delete a Group!**
  * `sudo groupdel accounting` -> Delete the **accounting** group!
* **`sudo` – Superpowers Activated!**
  * `sudo useradd fgarcia` -> Add user **fgarcia** with superpowers!
* **`useradd` – Add New Users!**
  * `sudo useradd -g security fgarcia` -> Add **fgarcia** to the **security** group!
* **`usermod` – Modify Users!**
  * `sudo usermod -a -G marketing fgarcia` -> Add **fgarcia** to the **marketing** group!
* **`userdel` – Delete Users!**
  * `sudo userdel fgarcia` -> Remove **fgarcia** from the system!

***

#### **6. Get Help in Linux 🚑**

Need help? Linux has got you covered!

* **`apropos` – What Does That Command Do Again?**
  * `apropos password` -> Search manual pages with the word **password**!
* **`man` – Manual Pages to the Rescue!**
  * `man chmod` -> Get the **full details** on how to use the **chmod** command!
* **`whatis` – Quick Info!**
  * `whatis nano` -> Get a quick description of the **nano** editor!

***

#### **Ready to level up your Linux skills? 🚀 Each command is like a new power-up in your toolbox!**

***

This guide covers **all the commands** you provided! Enjoy your Linux adventures with some extra fun along the way!
