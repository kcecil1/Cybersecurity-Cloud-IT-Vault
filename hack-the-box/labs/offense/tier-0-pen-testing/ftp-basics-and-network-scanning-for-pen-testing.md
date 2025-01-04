---
description: >-
  FTP, Protocols, Reconnaissance, Anonymous/Guest Access (Fawn Machine Starting
  Point Tier 0)
---

# FTP Basics and Network Scanning for Pen Testing (Fawn)

I was able to answer the first few flag questions without looking up the answers, luckily.

<figure><img src="../../../../.gitbook/assets/image (6) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (2) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

For task 5 I shamelessly asked X.AI (GROK 2) the answer:

<figure><img src="../../../../.gitbook/assets/image (3) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (4) (1) (1).png" alt=""><figcaption></figcaption></figure>

I went on ahead and first used NMAP to just scan to see what ports were open, seems they only left the ftp port or port 21 open, interestingly.&#x20;

I then typed the command that Grok gave me.

<figure><img src="../../../../.gitbook/assets/image (5) (1) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (6) (1) (1).png" alt=""><figcaption></figcaption></figure>

It showed the answer for the next task in the output on the linux terminal already:

<figure><img src="../../../../.gitbook/assets/image (7) (1).png" alt=""><figcaption></figcaption></figure>

Hilariously, I misunderstood the hinted text in the next task so I entered in "ftp -h" in the terminal, and it gave me the help menu by default, showing that the real command is "ftp -?"

<figure><img src="../../../../.gitbook/assets/image (8) (1).png" alt=""><figcaption></figcaption></figure>

I ended up guessing this one, lol.

<figure><img src="../../../../.gitbook/assets/image (9) (1).png" alt=""><figcaption></figcaption></figure>

I misread the question task here so jumped the gun and put "220" for the response code, which was incorrect, that is the code for ready for new user, while htb was looking for successful login response code of "230"

<figure><img src="../../../../.gitbook/assets/image (11) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (10) (1).png" alt=""><figcaption></figcaption></figure>

I knew the answer to this task already luckily:

<figure><img src="../../../../.gitbook/assets/image (12) (1).png" alt=""><figcaption></figcaption></figure>

Again, I didn't know the answer to the following task so I shamelessly asked Grok 2 for the answer. It's really helpful since it not only told me how to download the file but also how to specify where I want to download it, change the filepath/ directory, etc.

<figure><img src="../../../../.gitbook/assets/image (13) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (14) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (15) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (16) (1).png" alt=""><figcaption></figcaption></figure>

So after relogging back into the ftp since it timed out, I entered the "ls" command to list the files on the ftp server. There appeared to be only one inconspicuous file obviously named "flag.txt." I entered the command 'get flag.txt' and it downloaded for me, luckily into a directory I could easily find without having to do a lot of fancy stuff.

<figure><img src="../../../../.gitbook/assets/image (17) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (18) (1).png" alt=""><figcaption></figcaption></figure>

I then exited out of the ftp server with "ctrl z" in the terminal, entered "ls" to list my current directory's files, and then entered "cat flag.txt" to output the text from the file. I then copy and pasted it to the text field of the last task.

<figure><img src="../../../../.gitbook/assets/image (19) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (20) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (21) (1).png" alt=""><figcaption></figcaption></figure>
