# Wireshark Network Linux Windows VM

In this project I did the following in Azure:

* Created a resource group
* created 2 virtual machines
  * windows 10 vm
  * ubuntu linux vm
  * configured passwords for each
  * configured memory and OS vers
  * published to my Azure resource group
* installed Wireshark on the windows machine
* Setup windows machine to ping endlessly to the linux machine
* analyzed the ICMP traffic with Wireshark (filtered only for ICMP)
* configured Azure firewall for linux machine to block all ICMP requests
* Note in wireshark that the ICMP requests were no longer receiving a response from the linux machine
* SSH into Linux machine with username, IP and password
  * Used Wireshark in windows machine to filter and observe SSH traffic
* Create a script file to run in windows CLI to release DCHP IP and RENEW IP request
  * This prevents from being disconnected from RDC (remote desktop connection)
  * Used Wireshark to filter and analyze DCHP requests between the Linux and Windows machines
* Used Wireshark to filter and analyze DNS traffic

Azure resources created:

* Resource Groups
* Azure Virtual Networks and Subnets
* Azure Virtual Machines (Windows and Linux \[Ubuntu])
  * Azure Network Security Groups (Firewall Resource)

Using Wireshark to capture icmp traffic on windows machine when pinging to linux machine !

<figure><img src="../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

Configure security Firewall rule to block all ICMP requests&#x20;

<figure><img src="../../.gitbook/assets/image (4) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

Then watch as timeout occurs for all ICMP requests to linux vm from windows vm, then ping requests complete again after firewall rule deleted

<figure><img src="../../.gitbook/assets/image (3) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

I used chat gpt to explain to me how to connect to the gui of the linux machine, it told me to install xrdp through ssh on my local windows powershell, so I updated and installed xrdp remotely through ssh to the linux machine:

!\[\[Pasted image 20240922161610.png]]

Using powershell to remote into ubuntu VM with SSH and analyze SSH traffic with WireShark:

!\[\[Pasted image 20240924190233.png]]

!\[\[Pasted image 20240924190345.png]]

Capturing DCHP release and renew IP requests

!\[\[Pasted image 20240924200920.png]]

Observe DNS traffic with wireshark:

!\[\[Pasted image 20240924201644.png]]
