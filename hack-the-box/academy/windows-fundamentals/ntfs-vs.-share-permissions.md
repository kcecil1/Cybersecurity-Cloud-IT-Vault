# NTFS vs. Share Permissions

Below is a step-by-step guide that will help you gain hands-on experience with NTFS vs. share permissions on Windows. We’ll walk through creating a network share, testing access with Linux tools (like `smbclient`), modifying share and NTFS permissions, and observing the effects in Windows. Finally, we’ll look at monitoring those shares and connections through various built-in Windows tools.

***

### 1. Overview of Key Concepts

#### **NTFS Permissions vs. Share Permissions**

1. **Share Permissions** (applied via the “Sharing” tab):
   * Control access when a resource is accessed over the network (e.g., via SMB).
   * Are simpler in scope: **Read**, **Change**, and **Full Control**.
   * Are enforced **only** when someone accesses the folder over the network.
2. **NTFS Permissions** (applied via the “Security” tab on an NTFS-formatted partition):
   * Apply both locally and over the network.
   * More granular (e.g., **Modify**, **Read & Execute**, **Write**, etc.).
   * By default, child folders **inherit** permissions from the parent folder, although you can disable inheritance.

> **Important**: When accessing a shared folder remotely, the **effective** permission = **the most restrictive** of the Share permission **and** the NTFS permission.
>
> For example, if the Share permission is set to “Full Control” but the NTFS permission is only “Read,” users accessing the folder over SMB will effectively only have **Read** permission.

#### **SMB and Firewall Considerations**

* The **Server Message Block (SMB)** protocol is what Windows uses to share files/printers over the network.
* **Windows Defender Firewall** may block SMB traffic (especially from devices not on the same domain/workgroup).
* You can enable or disable inbound/outbound firewall rules for SMB in the Windows Defender Firewall with Advanced Security console (`wf.msc`).

***

### 2. Setting up the Lab Environment

**Goal**: You will create a shared folder on a Windows 10 machine and attempt to connect to it from a Linux environment (such as a VM, “Pwnbox,” or other Linux system).

#### **Prerequisites**

1. A **Windows 10** machine (physical or virtual).
2. A **Linux** system (physical or virtual) on the same network or with a routed connection so it can reach the Windows 10 machine.
3. (Optional) Administrator privileges on the Windows 10 box (to configure firewall rules if needed).

***

### 3. Creating a Shared Folder on Windows

1. **Log in** to your Windows 10 box.
2. **Right-click** on the **Desktop** and select **New** → **Folder**.
3. Name the folder something like `Company Data`.
4. **Right-click** the `Company Data` folder → **Properties** → **Sharing** tab.
5. Click **Advanced Sharing...**.
6. **Check** the box **Share this folder**. The share name defaults to `Company Data`.
7. Click on **Permissions**. You will see a default entry for `Everyone` (with **Read** permission by default).
8. Click **OK** → **OK** → **Close** to finish.

> **Note**: By default, Windows might limit the number of concurrent users that can connect (usually 20 on a Windows 10 Pro machine), but you can customize that number in **Advanced Sharing** → **Limit the number of simultaneous users to**.

***

### 4. Testing Firewall Settings (If Needed)

If your Linux client is not on the same domain or Windows workgroup, the firewall may block SMB connections. You can do the following tests:

1. On Windows 10, open **Windows Defender Firewall** (type “Windows Defender Firewall” in the Start menu).
2. Click **Advanced settings** (this opens `wf.msc`).
3. On the left, click **Inbound Rules**.
4. Find the **File and Printer Sharing (SMB-In)** rules:
   * Enable them if they are disabled. (Make sure you enable the rules corresponding to the network profile you’re using: Domain, Private, or Public.)
5. Alternatively, for a **quick** but less secure test, you could briefly disable the firewall:
   * **Control Panel** → **System and Security** → **Windows Defender Firewall** → **Turn Windows Defender Firewall on or off** → Turn Off.
   * **Only** do this in a controlled lab environment for testing.

***

### 5. Verifying the Share from Linux (Using smbclient)

1. On your Linux system, open a **terminal**.
2.  Run the following command (replacing `SERVER_IP` with your Windows 10 machine’s IP, and `htb-student` with an actual user on the Windows box if needed):

    ```bash
    smbclient -L //SERVER_IP -U htb-student
    ```
3. When prompted, enter the password for `htb-student`.
   *   You should see something like:

       ```
       Sharename       Type      Comment
       ---------       ----      -------
       ADMIN$          Disk      Remote Admin
       C$              Disk      Default share
       Company Data    Disk
       IPC$            IPC       Remote IPC
       ```
4.  Connect to the share:

    ```bash
    smbclient "//SERVER_IP/Company Data" -U htb-student
    ```
5. Test basic commands (like `dir`, `ls`, `get <filename>`, `put <filename>` if your share permissions allow them).

> **Potential Issue**: If you can’t connect at all, confirm that firewall rules are correct or the firewall is off for your test environment. Also confirm that the username/password is correct and that the account has permissions.

***

### 6. Observing Share vs. NTFS Permissions

#### **Step A: Observe the Default (Read) Permissions**

1. On Windows, right-click the **`Company Data`** folder → **Properties** → **Sharing** → **Advanced Sharing...** → **Permissions**.
   * By default, `Everyone` is set to **Read**.
2. On the **Security** tab (NTFS permissions), note the default permissions. Typically, your user has **Full Control** or **Modify** on a folder you created. The **`Everyone`** group might not even appear by default in the Security tab.
3.  Go back to your **Linux** terminal with the open SMB session and try to **upload** (put) a file:

    ```bash
    smb: \> put /etc/hosts
    ```

    * If the share permission for `Everyone` is only **Read**, you should get an **Access Denied** error, or it may say “NT\_STATUS\_ACCESS\_DENIED”.
    * This demonstrates that **Share permissions** + **NTFS permissions** together are limiting your access.

#### **Step B: Change the Share Permission to “Full Control”**

1. On Windows, go back to the folder’s **Sharing** tab → **Advanced Sharing...** → **Permissions**.
2. Set `Everyone` to **Full Control**.
3. **Apply** and **OK** out of all windows.

> **Remember**: Even with **Full Control** share permission, if the NTFS permission for `Everyone` is still “Read,” you’ll still be limited to Read effectively.

#### **Step C: Observe NTFS Permissions in Security Tab**

1. Right-click `Company Data` → **Properties** → **Security** tab.
2. Click **Advanced** if you want to see the full **Access Control List (ACL)** with inheritance details.
3. You can add or remove a group (e.g., `Everyone`), or change permissions to test how it affects your remote access.
4. **Try** adding `Everyone` to the Security tab with **Full Control**:
   * Click **Edit** → **Add** → type `Everyone` → select **Full Control** → **OK**.
   * If you do this, both the Share and NTFS permissions are at Full Control, meaning you (as “Everyone”) can add/edit/delete files.
5. **Back in your Linux SMB session**, see if you can:
   * **Upload** files (`put`).
   * **Create** directories.
   * **Delete** files.
   * Confirm these operations now work.

***

### 7. Mounting the Share via CIFS on Linux

Instead of using `smbclient`, you can mount the share directly into your Linux filesystem:

1.  **Install** the **cifs-utils** package (if not already installed):

    ```bash
    sudo apt-get update && sudo apt-get install cifs-utils
    ```
2.  **Create** a mount point on your Linux system, e.g., `/mnt/companydata`:

    ```bash
    sudo mkdir /mnt/companydata
    ```
3.  **Mount** the share:

    ```bash
    sudo mount -t cifs -o username=htb-student,password=Academy_WinFun! //SERVER_IP/"Company Data" /mnt/companydata
    ```

    * Adjust the username/password/IP/share name accordingly.
    * If successful, you can now **cd** into `/mnt/companydata` and see or manipulate files (according to your effective permissions).

***

### 8. Monitoring & Auditing on Windows

#### **A. Using the `net share` Command**

In your Windows 10 **Command Prompt** or **PowerShell**, type:

```bash
net share
```

You should see:

```
Share name   Resource                        Remark
---------    --------                        ------
C$           C:\                             Default share
IPC$                                         Remote IPC
ADMIN$       C:\WINDOWS                      Remote Admin
Company Data C:\Users\htb-student\Desktop\Company Data
```

* Notice **C$** is the administrative share for the entire `C:` drive, automatically created by Windows.
* The share you created, **Company Data**, will also appear here.

#### **B. Using Computer Management**

1. Right-click **This PC** → **Manage** or search **Computer Management** in the Start menu.
2. Navigate to **System Tools** → **Shared Folders**:
   * **Shares**: shows shared folders and their paths.
   * **Sessions**: shows who is currently connected.
   * **Open Files**: shows which files remote users have open.

This is **very** handy for diagnosing file locks, seeing who is connected, etc.

#### **C. Viewing Logs in Event Viewer**

1. Open the **Event Viewer** (type “Event Viewer” in Start).
2. Expand **Windows Logs** → **Security**.
   * Look for **Audit Success** or **Audit Failure** events related to file sharing or logons.
3. Expand **Windows Logs** → **System** for events about the server service (SMB) and any firewall logs.
4. (Optional) If you want deeper auditing, you can enable **Object Access Auditing** in local or group policy to log file-level access events.

***

### 9. Things to Try and Observe

1. **Remove “Everyone” from Share Permissions** and attempt connecting again:
   * See if you can even see or list the share.
2. **Disable Inheritance** on the NTFS Security tab:
   * Right-click `Company Data` → **Properties** → **Security** → **Advanced** → **Disable inheritance**.
   * Modify permissions to something unique (like read-only for your account). Test.
3. **Enable or disable specific firewall rules** for SMB on Windows to see the effect in real time.

***

### 10. Summary of Key Takeaways

1. **Both NTFS permissions and Share permissions** matter when connecting via SMB:
   * The **most restrictive** of the two sets is applied.
2. **Windows Defender Firewall** can block inbound SMB traffic if not configured properly.
3. **Shares can be enumerated** using `smbclient -L` or `net share`.
4. **Default Administrative Shares** (like `C$`) are automatically created by Windows.
5. **Computer Management** → **Shared Folders** and **Event Viewer** are critical for monitoring share usage and troubleshooting.

By walking through these steps, you’ll become more comfortable with how Windows shares operate, how to control them with NTFS and share permissions, and how to investigate or audit their usage. This is essential knowledge for understanding Windows security—and crucial for responding effectively if (or when) a breach or malicious activity occurs via SMB.
