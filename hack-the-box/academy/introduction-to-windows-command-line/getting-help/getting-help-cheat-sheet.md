# Getting Help Cheat Sheet

#### **Command Prompt Help & Tips Cheat Sheet**

**Getting Help in Command Prompt**

1. **General Help Command**
   *   Use `help` to display a list of built-in commands with brief descriptions.

       ```cmd
       C:\> help
       ```
   *   Example Output:

       ```
       ASSOC          Displays or modifies file extension associations.
       ATTRIB         Displays or changes file attributes.
       CHKDSK         Checks a disk and displays a status report.
       ...
       ```
2. **Command-Specific Help**
   *   Use `help <command>` for detailed information about a specific command.

       ```cmd
       C:\> help time
       ```
   * If unsupported, the system may suggest alternatives (e.g., `command /?`).

**Why Use the Help Utility?**

* **Offline Availability**: Works without Internet access, providing vital command usage details.
* **Efficiency**: Quickly find command syntax and parameters without external resources.

***

**Additional Help Resources**

* **Microsoft Documentation**: Comprehensive listing of commands and their uses.
* **SS64**: Quick reference for command-line tools across multiple platforms.

***

**Essential Command Prompt Tips & Tricks**

1. **Clearing the Screen**
   *   Use `cls` to clear the current terminal window.

       ```cmd
       C:\> cls
       ```
2. **Command History**
   *   **View Command History**:

       ```cmd
       C:\> doskey /history
       ```
   * **Navigate Through History**:
     * `↑` Scroll up through previous commands.
     * `↓` Scroll down to recent commands.
   * **Function Keys for History**:
     * `F3`: Repeats the last command.
     * `F5`: Cycles through commands.
     * `F7`: Opens an interactive list of commands.
     * `F9`: Re-executes a specific command by history number.
3. **Export Command History**
   *   Save history to a file using `doskey`:

       ```cmd
       C:\> doskey /history > history.txt
       ```
4. **Exit a Running Process**
   *   Interrupt a process using `Ctrl+C`. Example:

       ```cmd
       C:\> ping 8.8.8.8
       (Press Ctrl+C to stop)
       ```

***

**Useful Keys & Commands Overview**

| **Key/Command**   | **Description**                                       |
| ----------------- | ----------------------------------------------------- |
| `doskey /history` | Displays session command history.                     |
| `Ctrl+C`          | Stops an active process.                              |
| `Page Up`         | Moves to the first command in history.                |
| `Page Down`       | Moves to the last command in history.                 |
| `F3`              | Repeats the last command.                             |
| `F5`              | Cycles through previous commands.                     |
| `F7`              | Opens a list of previous commands.                    |
| `F9`              | Executes a command by its number in the history list. |

***

**Final Notes**

* Command Prompt does not persist history between sessions. Use `doskey` to save commands if needed.
* Regularly practice navigating and using help functions to improve efficiency in restrictive environments.
