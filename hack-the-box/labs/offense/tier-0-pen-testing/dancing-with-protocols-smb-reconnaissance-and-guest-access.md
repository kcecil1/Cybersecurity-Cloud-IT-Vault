---
description: >-
  Penetration Testing with Hack the Box's Dancing lab from Starting Point Tier
  0.
---

# Dancing with Protocols: SMB Reconnaissance and Guest Access (Dancing)

<figure><img src="../../../../.gitbook/assets/image (22) (1) (1).png" alt=""><figcaption></figcaption></figure>

The answer is "Server Message Block"

<figure><img src="../../../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

I will attempt to use NMAP to just scan the IP address of the target, since these easy machines typically will tell / show me what port is being used for the protocol they want me to learn.

<figure><img src="../../../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

Hmmm... I'm not really sure what I'm looking at here... I will have to investigate further by asking AI what all the output means.

\
Grok 2 said:

Here's a simple breakdown of the Nmap scan output you've provided:

1. Scan Command: nmap -sC -sV 10.129.199.54 - This command tells Nmap to scan the IP address 10.129.199.54 with default scripts (-sC) and attempt to detect service versions (-sV).
2. Host Information:
   * Host is up: The target machine is active and responded to the scan.
   * Latency: The time it took for the host to respond was 0.067 seconds.
3. Ports and Services:
   * 135/tcp: Open and running msrpc (Microsoft Remote Procedure Call), which is used for communication between Windows processes.
   * 139/tcp: Open for netbios-ssn, which is part of the NetBIOS over TCP/IP protocol suite, used for file and printer sharing services in Windows.
   * 445/tcp: Open and likely running microsoft-ds (Microsoft Directory Services), commonly used for Windows file sharing and Active Directory.
4. Service Detection:
   * Operating System: The services detected suggest this is a Windows operating system. The notation cpe:/o:microsoft:windows indicates a Common Platform Enumeration for a version of Microsoft Windows.
5. Host Script Results:
   * smb2-time: Shows the current date and time as reported by the SMB (Server Message Block) service on the target, which is 2024-12-31T08:55:52. There's no start date available, which might be due to the configuration or policy settings on the SMB service.
   * smb2-security-mode: Indicates the security settings for SMB version 2. It mentions that message signing is enabled but not required, which is a security feature to ensure the integrity of the communication.
6. Clock Skew: There's a discrepancy of about 4 hours between your computer's time and the target's reported time, suggesting that the target's clock might be set incorrectly or there could be a timezone difference.
7. Service Detection and Reporting: Nmap encourages users to report any inaccuracies in service detection to help improve its database.
8. Scan Summary:
   * The scan took about 19.92 seconds to complete and scanned one IP address.

\
This output provides a snapshot of the network services available on the target machine, its operating... I guess Grok gave up at that point.

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

That didn't really give me any conclusive information about what port smb operates at... I'd assume that it operates at one of the open ports scanned by nmap though... either 135 msrpc, 139 netbios-ssn or 445 microsoft-ds?\
\
So I asked Grok specifically:

<figure><img src="../../../../.gitbook/assets/image (57) (1).png" alt=""><figcaption></figcaption></figure>

Here is the AI's output:\
SMB (Server Message Block) primarily uses port 445. Here's a breakdown of the ports mentioned:

* Port 135: This port is used by Microsoft RPC (Remote Procedure Call) services, which can facilitate SMB communication but isn't directly used for SMB file sharing itself. RPC is a protocol that allows one program to request a service from a program on another computer without having to understand the network's details.
* Port 139: This port is associated with NetBIOS Session Service, which was used by earlier versions of SMB (SMB 1.0) over NetBIOS. This setup allowed for file and printer sharing in Windows environments but has largely been deprecated in favor of direct SMB over TCP/IP on port 445.
* Port 445: This is the primary port used by SMB for file sharing, printer sharing, and other services in modern Windows networks. SMB uses this port to operate over TCP/IP directly without needing NetBIOS.

\
So, while ports 135 and 139 might be related to services that interact with SMB or older versions of it, port 445 is where you'll find SMB in action for file sharing and related network services in current Windows environments.

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

Alright so it's port 445.

<figure><img src="../../../../.gitbook/assets/image (58) (1).png" alt=""><figcaption></figcaption></figure>

Task 3's answer was already revealed by the nmap scan:

<figure><img src="../../../../.gitbook/assets/image (60) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (59) (1).png" alt=""><figcaption></figcaption></figure>

For the following task 4 I attempted to answer with the command "ls" but that was incorrect. I shamelessly selected the hint icon, which told me to attempt using the 'man smbclient' command to bring up the list of commands to find it myself:

<figure><img src="../../../../.gitbook/assets/image (63) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (62) (1).png" alt=""><figcaption></figcaption></figure>

The answer ended up being "-L"

<figure><img src="../../../../.gitbook/assets/image (64) (1).png" alt=""><figcaption></figcaption></figure>

The next task, task 5 is asking me how many shares are there on the Dancing lab... I have absolutely no idea. Guess it's time to ask AI again.

<figure><img src="../../../../.gitbook/assets/image (65).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (66).png" alt=""><figcaption></figcaption></figure>

I don't really have a password so I attempted to just use the command "smbclient -L //10.129.199.54"

<figure><img src="../../../../.gitbook/assets/image (67).png" alt=""><figcaption></figcaption></figure>

I got lucky that there wasn't a password set so I was able to just hit enter to skip that. I assumed the four entries were the numbe of shares and I was correct:

<figure><img src="../../../../.gitbook/assets/image (68).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (69).png" alt=""><figcaption></figcaption></figure>

I have no idea what share I can access with a blank password. So I asked AI again...

<figure><img src="../../../../.gitbook/assets/image (70).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (71).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (72).png" alt=""><figcaption></figcaption></figure>

It looks like task 6 is only looking for one answer and that answer is most likely "WorkShares" considering the answer is long and uses a hint with the letter "s" at the end. But it actually looks like I was able to log in with a blank passwork to not only "WorkShares" but also "IPC$":

<figure><img src="../../../../.gitbook/assets/image (73).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (74).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (75).png" alt=""><figcaption></figcaption></figure>

Task 7 is asking for what command I can use within the SMB shell to download the files I find... I'm not sure but I'm going to use an educated guess and say the command "get"

<figure><img src="../../../../.gitbook/assets/image (76).png" alt=""><figcaption></figcaption></figure>

Looks like I was correct. The problem is I don't really know how I would use it, I can't seem to figure out how to list anything from the directory of the SMB in order to download something...

<figure><img src="../../../../.gitbook/assets/image (77).png" alt=""><figcaption></figcaption></figure>

But I'm guessing the final task will force me to figure that out.

<figure><img src="../../../../.gitbook/assets/image (78).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (79).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (80).png" alt=""><figcaption></figcaption></figure>

I had to ask how to find files in order to even use the get command to download anything in the first place... and then asked about the "." and ".." directories, I guess "." is the current directory and ".." is the directory right above the current one. So the only option I have left is to just try to change directories to either "Amy.J" or "James.P"

<figure><img src="../../../../.gitbook/assets/image (81).png" alt=""><figcaption></figcaption></figure>

I changed directies into Amy.J and listed the contents then moved back up one level and then changed directories into James.P directory and listed the contents of the directory, striking gold with a file named "flag.txt"

<figure><img src="../../../../.gitbook/assets/image (82).png" alt=""><figcaption></figcaption></figure>

Then I used the get command to download the file to my linux machine, then used the exit command to quit the smbclient. \
Then I printed my working directory, listed the contents, found the file and then used the concatenate command to read the files contents, revealing the root flag to me, which I then copy and pasted into the final task for submission.

<figure><img src="../../../../.gitbook/assets/image (83).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (84).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (85).png" alt=""><figcaption></figcaption></figure>
