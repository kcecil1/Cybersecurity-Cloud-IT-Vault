---
description: Meow Lab on Hack the Box (Tier 0) Starting Point.
---

# Basic Penetration Testing using Telnet (Meow)

Here I am pinging my target (10.129.166.206) to see if I am on the same network segment or that it is on:\


<figure><img src="../../../../.gitbook/assets/image (47) (1).png" alt=""><figcaption></figcaption></figure>

Next I'm running NMAP (network mapper) to scan which ports are open and what service they are running on the target machine:

<figure><img src="../../../../.gitbook/assets/image (48) (1).png" alt=""><figcaption></figcaption></figure>

The only port out of a 1000 ports open is port 23, which is running the "Telnet" service.

Here I try to connect to the target with telnet:

<figure><img src="../../../../.gitbook/assets/image (49) (1).png" alt=""><figcaption></figcaption></figure>

I attempted to login with different user account names with blank password

<figure><img src="../../../../.gitbook/assets/image (50) (1).png" alt=""><figcaption></figcaption></figure>

Looks like root was correct:

<figure><img src="../../../../.gitbook/assets/image (51) (1).png" alt=""><figcaption></figcaption></figure>

I used "ls /" command to list directories and then "cd /root" to change directories to the root directory. Then I ran the list or ls command again to reveal the flag.txt file which I then concatenated with the "cat" command which output the file's contents revealing the "flag" to me.

<figure><img src="../../../../.gitbook/assets/image (52) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (53) (1).png" alt=""><figcaption></figcaption></figure>

