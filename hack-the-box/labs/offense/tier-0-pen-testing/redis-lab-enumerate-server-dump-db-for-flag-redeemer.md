---
description: >-
  Hack the Box Starting Point Tier 0 Redeemer Machine, focusing on Redis,
  Vulnerability Assessment, Databases, Reconnaissance, Anonymous/Guest Access
---

# Redis Lab: Enumerate Server, Dump DB for Flag (Redeemer)

<figure><img src="../../../../.gitbook/assets/image (86).png" alt=""><figcaption></figcaption></figure>

Hmmm... I scanned the ports with NMAP but the scan came back that all 1000 ports were closed.

<figure><img src="../../../../.gitbook/assets/image (87).png" alt=""><figcaption></figcaption></figure>

The HTB writeup shows me to include a "-p-" flag into the command... This endedup scanning the full range of over 60,000 ports.&#x20;

<figure><img src="../../../../.gitbook/assets/image (88).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (89).png" alt=""><figcaption></figcaption></figure>

Finally, task 1 is complete...

<figure><img src="../../../../.gitbook/assets/image (90).png" alt=""><figcaption></figcaption></figure>

Oh, and task 2:

<figure><img src="../../../../.gitbook/assets/image (91).png" alt=""><figcaption></figcaption></figure>

Also task 3:

<figure><img src="../../../../.gitbook/assets/image (92).png" alt=""><figcaption></figcaption></figure>

According to the writeup, the answer to task 4 is "redis-cli"

<figure><img src="../../../../.gitbook/assets/image (93).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (94).png" alt=""><figcaption></figcaption></figure>

The writeup said I needed to install the redis-cli in order to continue onward so I entered the following command:

<figure><img src="../../../../.gitbook/assets/image (96).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (95).png" alt=""><figcaption></figcaption></figure>

Looks like it was already installed, so all that it did was just make two updates.

Next up was checking the help menu.

<figure><img src="../../../../.gitbook/assets/image (97).png" alt=""><figcaption></figcaption></figure>

This output is likely to help me answer the next task.

<figure><img src="../../../../.gitbook/assets/image (98).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (99).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (100).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (101).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (102).png" alt=""><figcaption></figcaption></figure>

Looks like the answer to task 5 was close to the top of the output for help menu:

<figure><img src="../../../../.gitbook/assets/image (103).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (104).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (105).png" alt=""><figcaption></figcaption></figure>

To get the answer for task 6, I had to use the -h command to get the host name, this sort of accesses the host for me. giving me a little prompt with the host name:

<figure><img src="../../../../.gitbook/assets/image (106).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (107).png" alt=""><figcaption></figcaption></figure>

Of course I already typed in the "info" command here - suggested by the machine's writeup of-course. This command shows or returns information and statistics about the redis server.

<figure><img src="../../../../.gitbook/assets/image (110).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (108).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (109).png" alt=""><figcaption></figcaption></figure>

I skipped a lot of the other info to show the bottom output which is 'Keyspace."

<figure><img src="../../../../.gitbook/assets/image (111).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (112).png" alt=""><figcaption></figcaption></figure>

The answer to task 7 was at the beginning of the "info" command's output.

<figure><img src="../../../../.gitbook/assets/image (113).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (114).png" alt=""><figcaption></figcaption></figure>

Task 8 finally relates to the "Keyspace" section of the "info" command's output - the output at the very bottom / end. Keyspace section shows how many databases there are and the number of keys for each database as well as how many have an expiration. in the keyspace section of my output it shows there is only 1 database - called out with the index of "0" or "db0"

<figure><img src="../../../../.gitbook/assets/image (115).png" alt=""><figcaption></figcaption></figure>

Task 8 is asking for what command is used to select the desired database in redis, well according to the writeup, the command is "select."

<figure><img src="../../../../.gitbook/assets/image (116).png" alt=""><figcaption></figcaption></figure>

Don't judge me for using a writeup... to be fair, HTB gives literally zero points and no hacker rank what so ever for any labs that are retired or that have writeups.&#x20;

<figure><img src="../../../../.gitbook/assets/image (117).png" alt=""><figcaption></figcaption></figure>

So I will use the select command to literally select the only available database, "0" or zero.

<figure><img src="../../../../.gitbook/assets/image (118).png" alt=""><figcaption></figcaption></figure>

It gave me a response of "OK.' Wow. That was... underwhelming.

<figure><img src="../../../../.gitbook/assets/image (119).png" alt=""><figcaption></figcaption></figure>

Task 9 asks for how many keys are present with Database zero, that was already given in the "info" commands output in the Keyspace section.

<figure><img src="../../../../.gitbook/assets/image (120).png" alt=""><figcaption></figcaption></figure>

Literally the next sentence in the writeup gives the answer... lol I'm shameless. It's okay, I'm learning and the active labs will still brutalize me when I work on them.

<figure><img src="../../../../.gitbook/assets/image (121).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (123).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (124).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (125).png" alt=""><figcaption></figcaption></figure>

I literally have no idea what the flag has anything to do with these keys, unless these keys are hash values, which would make sense considering how long the value is that they are expecting for the input field lol.

<figure><img src="../../../../.gitbook/assets/image (126).png" alt=""><figcaption></figcaption></figure>

Just a stab in the dark... but I tried "get flag" and it outputed a pretty long string of numbers and characters... looks like a hash to me lol. I will copy and paste it into the final task's input and see if I was right.

<figure><img src="../../../../.gitbook/assets/image (127).png" alt=""><figcaption></figcaption></figure>

Guess so lol. Had to redeem myself at least a little bit by trying something without looking at the writeup lol...
