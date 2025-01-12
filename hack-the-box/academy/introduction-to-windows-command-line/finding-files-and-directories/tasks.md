---
description: 'Target(s): 10.129.198.63 (ACADEMY-ICL-WIN11)'
---

# Tasks

What command can be used to search for regular expression strings from command prompt?

<figure><img src="../../../../.gitbook/assets/image (190).png" alt=""><figcaption></figcaption></figure>

Using the skills acquired in this and previous sections, access the target host and search for the file named 'waldo.txt'. Submit the flag found within the file.

I first used the "where" command in powershell that didn't work at all so I entered the command prompt by entering the "cmd" command.&#x20;

Then I attempted to use where command to find the waldo.txt file, even with recursion it was not found, so I changed directories to the user folder and ran the command with recursion through all user folders and found that the file was in the user folder for MTanaka

So I changed directories, found the file and used the "type" command to output the file's contents to get the flag.

<figure><img src="../../../../.gitbook/assets/image (191).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (192).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (193).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (194).png" alt=""><figcaption></figcaption></figure>



