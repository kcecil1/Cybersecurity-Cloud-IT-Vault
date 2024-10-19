
---

### 🗂️ **How Many Partitions Exist in Pwnbox?**

You're on a mission to find out how many **partitions** exist on your Pwnbox! Partitions are like the **different sections** of your hard drive, where files and systems live. Think of them like the different rooms in a house 🏠—each one with its own purpose.

---

### 🚀 **Using `fdisk -l` to List Partitions**
To find out how many partitions are there, you can use the **fdisk command** with the `-l` flag, which lists all the partition tables on your system.

Here's the magic command:
```bash
sudo fdisk -l
```

---

### 📊 **Example Output:**
When you run the command, you’ll see something like this:
```bash
Disk /dev/vda: 40 GiB, 42949672960 bytes, 83886080 sectors
Units: sectors of 1 * 512 = 512 bytes
Device     Boot    Start      End  Sectors  Size Id Type
/dev/vda1  *        2048 81885183 81883136   39G 83 Linux
/dev/vda2       81887230 83884031  1996802  975M  5 Extended
/dev/vda5       81887232 83884031  1996800  975M 82 Linux swap / Solaris
```

---

### 🛠️ **Breaking It Down:**
You’ve got **three partitions** on your Pwnbox:
1. **/dev/vda1** – Your main partition where all the magic happens (the main OS).
2. **/dev/vda2** – An **extended partition** (it acts like a container for other partitions).
3. **/dev/vda5** – A **swap partition** (used as extra memory when your system runs out of RAM).

**Boom!** The answer is **3 partitions**.

Now, you can confidently answer the question: **How many partitions exist in our Pwnbox?** Answer: **3**

---

Now you’re officially a **partition pro**! 🎉