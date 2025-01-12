# Working with Directories and Files

Below is a concise overview of the key concepts from the lesson on working with directories and files in Windows:

***

### 1. Directories (Folders)

* **Definition**: A directory is a container (folder) in the Windows filesystem. Directories can be nested within one another, creating a hierarchical structure.
* **Navigation**:
  * `cd` (or `chdir`) changes the current directory.
  * `dir` lists the contents of a directory.
  * `tree` provides a tree-like view of directories (use `tree /F` to also list files).
* **Creating Directories**:
  * `md new-folder` or `mkdir new-folder` (both work the same way).
* **Deleting Directories**:
  * `rd folderName` or `rmdir folderName` removes an empty folder.
  * `rd /S folderName` removes a directory **and all its contents** (prompts for confirmation).
* **Moving Directories**:
  * `move sourceDirectory destinationDirectory` moves a directory and everything inside it.
  * `xcopy` and `robocopy` are more advanced alternatives that can handle complex copying scenarios, including preserving file attributes, copying across networks, etc.

***

### 2. Files

* **Listing & Viewing File Contents**:
  * `dir` lists files in the current directory.
  * `more filename` or `type filename` displays the contents of text files. `more` shows text page by page, while `type` streams the whole file at once.
* **Creating & Modifying Files**:
  * `echo someText > file.txt` creates or overwrites a file with the given text.
  * `echo moreText >> file.txt` appends text to the file instead of overwriting.
  * `fsutil file createNew fileName size` creates a file of a specific size (in bytes).
  * `ren oldName newName` (or `rename oldName newName`) renames a file.
* **Input/Output Redirection**:
  * `>` redirects the output of a command to a file (overwrites).
  * `>>` appends the output to a file.
  * `<` takes a file’s contents as input to a command.
  * `|` (pipe) sends the output of one command to another as input.
  * `&` runs multiple commands in sequence (e.g., `cmdA & cmdB` runs both commands regardless of success).
  * `&&` runs a second command only if the first command succeeds; `||` runs a second command only if the first fails.
* **Deleting Files**:
  * `del filename` or `erase filename` removes a file.
  * You can specify multiple files with wildcards (e.g., `del file-*.txt`) or attributes (e.g., `del /A:R` for read-only files).
* **Copying & Moving Files**:
  * `copy sourceFile destinationFile` copies a file.
  * `copy /V` validates that files were copied correctly.
  * `move sourceFile destinationPath` moves a file (and can rename it).
  * `xcopy` and `robocopy` can be used for more advanced copying needs, including recursive directory copying and preserving attributes.

***

### 3. Advanced Copy Tools

* **xcopy**:
  * Ideal for copying directories and files, can remove the Read-only attribute (`/K` keeps attributes, `/E` copies subdirectories including empty ones).
* **robocopy**:
  * The modern, more robust alternative to `xcopy`.
  * Can handle large directory trees, preserve attributes (timestamps, ACLs, etc.), and even transfer files across networks.
  * Common switches include `/MIR` (mirror source and destination) and `/A-:SH` (remove system/hidden attributes after copying).
  * By default, requires sufficient privileges to copy system or locked files.

***

### 4. Key Takeaways

1. **Directory Management**:
   * Navigate with `cd`, view with `dir` or `tree`, create with `md/mkdir`, delete with `rd/rmdir`.
2. **File Management**:
   * View content with `more` or `type`.
   * Create/modify with `echo`, `fsutil`, or redirection operators.
   * Rename with `ren/rename`.
   * Delete files with `del/erase`.
3. **Copy & Move**:
   * Basic commands: `copy`, `move`.
   * Advanced commands: `xcopy`, `robocopy`.
4. **I/O Redirection & Piping**:
   * `>`, `>>` for output redirection, `<` for input redirection, `|` for piping output to another command, `&` and `&&` for sequential commands.

By mastering these fundamental built-in tools for working with directories and files, both administrators and hackers can efficiently navigate Windows, automate tasks, and access or manipulate crucial data with minimal visibility.



