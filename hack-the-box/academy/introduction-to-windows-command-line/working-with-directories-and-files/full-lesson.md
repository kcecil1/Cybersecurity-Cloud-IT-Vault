# Full Lesson

**Windows Directories & Files: The ADHD-Friendly, Fun-Filled Guide**\
&#xNAN;_(Imagine you’re on a wild treasure hunt through a hotel loaded with hidden hallways, secret rooms, and epic loot!)_

***

### 1. Directories: The Hotel & Hallways Analogy

* **Drive (C:) = The Hotel**\
  Think of the entire hard drive as a big hotel.
* **Main Directories = The Floors**\
  Inside the hotel, each floor (like `Windows`, `Users`, `Program Files`) is a directory.
* **Sub-Folders = Hallways**\
  Each hallway leads you to different rooms (subfolders). For example, `C:\Users\htb` is a hallway inside the “Users” floor.
* **Files = The Rooms**\
  Finally, behind each door (file) lies something interesting—maybe a text doc, maybe a top-secret plan!

#### Handy Commands for Navigating:

* `cd` (change directory) – Walk to a different hallway.
* `dir` – Peek around the hallway to see which rooms and other hallways exist.
* `tree` – Zoom out and get a big map of the entire floor/hallway structure.

***

### 2. Creating New Hallways (Folders)

You can use **either** `md` or `mkdir` (they do the exact same thing, like magic twins).

```bash
md new-directory
mkdir yet-another-dir
```

Now you’ve built yourself some brand-new hallways to store all your secret goodies!

***

### 3. Removing Hallways (Folders)

* **`rd`** or **`rmdir`** – Tear down that hallway.
*   If a hallway is full of stuff (not empty), Windows will fuss at you. Use the magic spell: `/S`

    ```bash
    rd /S SomeHallway
    ```

    You’ll be asked, “Are you sure?” so you don’t accidentally blow up your precious data.

***

### 4. Moving Hallways (Folders)

*   **`move`** – Shift an entire hallway (and everything in it) to a new floor.

    ```bash
    move example C:\Users\htb\Documents\example
    ```
* **`xcopy`** – Like a bigger, fancier copy command that can preserve some file attributes.
* **`robocopy`** – The ultimate unstoppable moving/copying beast. Perfect for big operations and preserving timestamps, permissions, etc.

_(Pro Tip: `robocopy` is so powerful it’s like summoning a bulldozer. Use `/MIR` carefully because it “mirrors” and can delete things at the destination if they’re not in the source.)_

***

### 5. Working with Files: A Quick Tour

#### **Listing & Viewing Files**

* `dir` – List all files.
* `tree /F` – Show all files and folders in a big tree.
* `more filename.txt` – Read a file page by page (great for big files!).
* `type filename.txt` – Dump the entire file’s contents into the terminal at once (watch out, it can scroll past quickly!).

#### **Creating & Modifying Files**

1.  **`echo` + Redirect**

    ```bash
    echo Hello World > myfile.txt   # Creates or overwrites  
    echo Another line >> myfile.txt # Appends to the file
    ```
2. **`fsutil file createNew filename.txt [size_in_bytes]`**\
   Creates an empty file of a certain size (for those times you want a “dummy” file).
3.  **`ren` or `rename`**

    ```bash
    ren oldname.txt newname.txt
    ```

    Give your file a stylish new name.
4. **Input/Output Redirection**
   * `>` – Output to a file (overwrite).
   * `>>` – Output to a file (append).
   * `<` – Feed file contents as input to a command.
   * `|` – Pipe the output of one command into another (like chaining spells!).

**Examples:**

*   **“Capture the results!”**

    ```bash
    ipconfig /all > details.txt
    ```
*   **“Append to a file!”**

    ```bash
    echo this is extra stuff >> details.txt
    ```
*   **“Search inside a file!”**

    ```bash
    find /i "secret" < details.txt
    ```
*   **“Chain two commands!”**

    ```bash
    ping 8.8.8.8 & type test.txt
    ```

    Runs `ping`, _then_ `type`.

_(If you only want command B to run if command A was successful, use `&&` instead of `&`.)_

***

### 6. Deleting Files

*   **`del`** or **`erase`** – Erases files. You can specify which file or even multiple files:

    ```bash
    del file1.txt
    erase file2.txt file3.txt
    ```
* **Attributes**\
  Some files are sneaky and marked “hidden” or “read-only.” Use:
  * `/F` to force-deletion
  * `/A:R` to remove read-only files
  * `/A:H` to remove hidden files

_(You can discover which files have these sneaky attributes with `dir /A:R` or `dir /A:H`.)_

***

### 7. Copying & Moving Files

* **`copy sourceFile targetFile`** – Straightforward copy.
  * Add `/V` to verify the copy.
* **`move sourceFile targetFolder`** – Removes the original file and places it in a new location. Also lets you rename if you want.

```bash
copy secrets.txt C:\NewFolder\not-secrets.txt
move secrets.txt C:\AnotherFolder
```

***

### 8. High-Five! You Did It!

You’re now a wizard at:

* Navigating Windows directories (the hotel floors and hallways)
* Creating & deleting directories
* Moving & copying files with style
* Reading, creating, renaming, and erasing files like a pro
* Using input/output redirection & piping to chain commands like you’re conjuring spells!

**Next Stop:** Learning how to gather system info, so you can become an even better hacker, defender, or just an all-around Windows command-line hero. Now go forth and conquer that filesystem—just don’t delete your entire “hotel” by accident!

_(End with a victory dance or a well-earned snack for your brain—your choice!)_
