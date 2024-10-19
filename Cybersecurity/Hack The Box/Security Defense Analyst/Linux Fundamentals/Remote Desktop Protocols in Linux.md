### 🚀 **Remote Desktop Protocols in Linux - Fun & ADHD-Friendly Lesson!**

Let’s dive into **remote desktop protocols** like **RDP**, **VNC**, and **XServer** in Linux! These tools let you connect to computers and manage them remotely—think of it like having your screen on a system far away. Perfect for troubleshooting, installing software, and remote administration. 🖥️

---

### 🎉 **XServer - It’s Everywhere!**
**XServer** is part of the **X Window System** (aka X11), and it’s built into most Linux desktops. It communicates with the operating system so you can see graphical stuff like windows! 

- **Fun fact**: XServer uses **ports 6000-6009** for connecting the display and other computers. You can even **forward X11** securely with **SSH**! But be careful; without SSH, it’s like an open window to hackers.

📄 **To configure X11 Forwarding**, open the SSH config on the server and allow forwarding:
```bash
cat /etc/ssh/sshd_config | grep X11Forwarding
X11Forwarding yes
```

To forward an app from a remote machine (like running **Firefox**):
```bash
ssh -X htb-student@<remote_ip> /usr/bin/firefox
```

---

### 🛡️ **X11 Security (Or Lack of It...)**
- **X11 is unencrypted**, so without SSH, it’s vulnerable to attacks like **keylogging** and **screenshot snooping**. 
- Pro tip: **Tunnel X11** through SSH to encrypt your data!

---

### 🌐 **VNC - Share Your Screen Like a Pro**
**VNC (Virtual Network Computing)** is a remote desktop protocol that lets you **view and control** another computer as if you were in front of it. Unlike X11, **VNC uses TCP 5900** (and 5901, 5902... for additional displays). 🔑

Install **TigerVNC** with **XFCE4** for a stable remote desktop experience:
```bash
sudo apt install xfce4 xfce4-goodies tigervnc-standalone-server -y
```
Set a password for VNC:
```bash
vncpasswd
```
---

### ⚙️ **VNC Setup – Easy Peasy**
Create the config and startup files:
```bash
touch ~/.vnc/xstartup ~/.vnc/config
cat <<EOT >> ~/.vnc/xstartup
#!/bin/bash
unset SESSION_MANAGER
unset DBUS_SESSION_BUS_ADDRESS
/usr/bin/startxfce4
EOT

cat <<EOT >> ~/.vnc/config
geometry=1920x1080
dpi=96
EOT

chmod +x ~/.vnc/xstartup
```
Start the **VNC server**:
```bash
vncserver
```
Check your VNC sessions:
```bash
vncserver -list
```

---

### 🔒 **Make VNC More Secure with SSH Tunneling**
We’re all about security! Create a secure **SSH tunnel** for your VNC connection:
```bash
ssh -L 5901:127.0.0.1:5901 -N -f -l htb-student <remote_ip>
```

Then, connect using **xtightvncviewer**:
```bash
xtightvncviewer localhost:5901
```

---

### 🔥 **Quick Commands for Practice!**
Here’s a handy list of all commands we talked about:

1. **Allow X11 forwarding in SSH**:
   ```bash
   cat /etc/ssh/sshd_config | grep X11Forwarding
   ```

2. **Run a remote application over SSH (X11 forwarding)**:
   ```bash
   ssh -X htb-student@<remote_ip> /usr/bin/firefox
   ```

3. **Install TigerVNC and XFCE4**:
   ```bash
   sudo apt install xfce4 xfce4-goodies tigervnc-standalone-server -y
   ```

4. **Set a VNC password**:
   ```bash
   vncpasswd
   ```

5. **Create the xstartup and config files**:
   ```bash
   touch ~/.vnc/xstartup ~/.vnc/config
   ```

6. **Add necessary configs for VNC**:
   ```bash
   cat <<EOT >> ~/.vnc/xstartup
   #!/bin/bash
   unset SESSION_MANAGER
   unset DBUS_SESSION_BUS_ADDRESS
   /usr/bin/startxfce4
   EOT

   cat <<EOT >> ~/.vnc/config
   geometry=1920x1080
   dpi=96
   EOT
   ```

7. **Make the xstartup file executable**:
   ```bash
   chmod +x ~/.vnc/xstartup
   ```

8. **Start the VNC server**:
   ```bash
   vncserver
   ```

9. **List active VNC sessions**:
   ```bash
   vncserver -list
   ```

10. **Create an SSH tunnel for VNC**:
    ```bash
    ssh -L 5901:127.0.0.1:5901 -N -f -l htb-student <remote_ip>
    ```

11. **Connect to VNC through SSH tunnel**:
    ```bash
    xtightvncviewer localhost:5901
    ```

---

And that's your **fun, ADHD-friendly guide** to remote desktop protocols in Linux! You’re now ready to control systems from afar like a pro! 🎉























#### X11Forwarding

  Remote Desktop Protocols in Linux

```shell-session
kcecil1@htb[/htb]$ cat /etc/ssh/sshd_config | grep X11Forwarding

X11Forwarding yes
```

With this we can start the application from our client with the following command:

  Remote Desktop Protocols in Linux

```shell-session
kcecil1@htb[/htb]$ ssh -X htb-student@10.129.23.11 /usr/bin/firefox

htb-student@10.129.14.130's password: ********
<SKIP>
```


#### TigerVNC Installation

  Remote Desktop Protocols in Linux

```shell-session
htb-student@ubuntu:~$ sudo apt install xfce4 xfce4-goodies tigervnc-standalone-server -y
htb-student@ubuntu:~$ vncpasswd 

Password: ******
Verify: ******
Would you like to enter a view-only password (y/n)? n
```


#### Configuration

  Remote Desktop Protocols in Linux

```shell-session
htb-student@ubuntu:~$ touch ~/.vnc/xstartup ~/.vnc/config
htb-student@ubuntu:~$ cat <<EOT >> ~/.vnc/xstartup

#!/bin/bash
unset SESSION_MANAGER
unset DBUS_SESSION_BUS_ADDRESS
/usr/bin/startxfce4
[ -x /etc/vnc/xstartup ] && exec /etc/vnc/xstartup
[ -r $HOME/.Xresources ] && xrdb $HOME/.Xresources
x-window-manager &
EOT
```

  Remote Desktop Protocols in Linux

```shell-session
htb-student@ubuntu:~$ cat <<EOT >> ~/.vnc/config

geometry=1920x1080
dpi=96
EOT
```

Additionally, the `xstartup` executable needs rights to be started by the service.

  Remote Desktop Protocols in Linux

```shell-session
htb-student@ubuntu:~$ chmod +x ~/.vnc/xstartup
```

Now we can start the VNC server.

#### Start the VNC server

  Remote Desktop Protocols in Linux

```shell-session
htb-student@ubuntu:~$ vncserver

New 'linux:1 (htb-student)' desktop at :1 on machine linux

Starting applications specified in /home/htb-student/.vnc/xstartup
Log file is /home/htb-student/.vnc/linux:1.log

Use xtigervncviewer -SecurityTypes VncAuth -passwd /home/htb-student/.vnc/passwd :1 to connect to the VNC server.
```

In addition, we can also display the entire sessions with the associated ports and the process ID.

#### List Sessions

  Remote Desktop Protocols in Linux

```shell-session
htb-student@ubuntu:~$ vncserver -list

TigerVNC server sessions:

X DISPLAY #     RFB PORT #      PROCESS ID
:1              5901            79746
```

To encrypt the connection and make it more secure, we can create an SSH tunnel over which the whole connection is tunneled. How tunneling works in detail we will learn in the [Pivoting, Tunneling, and Port Forwarding](https://academy.hackthebox.com/module/details/158) module.

#### Setting Up an SSH Tunnel

  Remote Desktop Protocols in Linux

```shell-session
kcecil1@htb[/htb]$ ssh -L 5901:127.0.0.1:5901 -N -f -l htb-student 10.129.14.130

htb-student@10.129.14.130's password: *******
```

Finally, we can connect to the server through the SSH tunnel using the `xtightvncviewer`.

#### Connecting to the VNC Server

  Remote Desktop Protocols in Linux

```shell-session
kcecil1@htb[/htb]$ xtightvncviewer localhost:5901

Connected to RFB server, using protocol version 3.8
Performing standard VNC authentication

Password: ******

Authentication successful
Desktop name "linux:1 (htb-student)"
VNC server default format:
  32 bits per pixel.
  Least significant byte first in each pixel.
  True colour: max red 255 green 255 blue 255, shift red 16 green 8 blue 0
Using default colormap which is TrueColor.  Pixel format:
  32 bits per pixel.
  Least significant byte first in each pixel.
  True colour: max red 255 green 255 blue 255, shift red 16 green 8 blue 0
Same machine: preferring raw encoding
```