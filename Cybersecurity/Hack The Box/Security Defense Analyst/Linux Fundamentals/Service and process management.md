Let’s dive into **service and process management** in a fun, ADHD-friendly way! Imagine you’re controlling a bunch of workers (services and processes) who do all the important tasks in the background, and you’re the boss who checks on them, starts them, stops them, and even gives them a break when needed. Each command you run is like giving orders to those workers.

### Step 1: **Starting Services** (Your workers begin their tasks)
Think of starting a service as giving your worker (in this case, SSH) the green light to begin working.

Command:
```bash
systemctl start ssh
```
What you’re doing: You’re telling the SSH worker to start doing its job.

**Quick practice tip:** Start the SSH service by running the command. You won't see anything happen, but don’t worry—it’s working!

---

### Step 2: **Check if the Service is Running** (Are your workers doing their jobs?)
Now, let’s check if the SSH worker is running smoothly and hasn’t run into any problems.

Command:
```bash
systemctl status ssh
```
What you’re doing: This command checks on your worker to make sure they’re doing their job correctly. If there’s an error, you’ll see it here!

**Quick practice tip:** After starting the service, check its status. If it's active (running), you’re good!

---

### Step 3: **Enable Service on Startup** (Make sure the workers clock in automatically)
You want your SSH worker to automatically start whenever the system boots up, so you enable it.

Command:
```bash
systemctl enable ssh
```
What you’re doing: This tells the system, “Hey, make sure the SSH worker starts every time I reboot the system.”

**Quick practice tip:** Run this command once, and SSH will always start on boot without you having to manually start it each time.

---

### Step 4: **List All Active Services** (Check on all your workers)
Want to see what all your background workers are doing? You can list them all and see which ones are active.

Command:
```bash
systemctl list-units --type=service
```
What you’re doing: You’re pulling up the roster to see which workers (services) are running.

**Quick practice tip:** Run this command and scroll through the list to see everything that’s running. You’ll recognize things like Apache, SSH, and more.

---

### Step 5: **Check Logs for Errors** (Looking at worker reports)
If something goes wrong, you need to check what happened in the logs.

Command:
```bash
journalctl -u ssh.service --no-pager
```
What you’re doing: You’re reading the report of the SSH worker to see if it’s been behaving or if any issues have come up.

**Quick practice tip:** Try restarting SSH (`systemctl restart ssh`) and then run this command to check the log for any new entries.

---

### Step 6: **Check for Running Processes** (Who’s on the clock?)
Sometimes you want to see exactly which worker (process) is active.

Command:
```bash
ps -aux | grep ssh
```
What you’re doing: You’re looking for all the processes related to SSH. It’s like checking the clock-in sheet to see who’s working.

**Quick practice tip:** Run this command to see all SSH-related processes. You’ll see details like the process ID (PID) and how long they’ve been running.

---

### Step 7: **Kill a Process** (Firing a worker)
If a worker (process) is misbehaving or frozen, you may need to fire them by killing the process.

Command:
```bash
kill 9 <PID>
```
What you’re doing: You’re forcefully stopping a misbehaving worker by using their process ID (PID). The signal `9` ensures it’s terminated.

**Quick practice tip:** Find a process with `ps -aux`, note the PID, and use the kill command. Be careful, only kill what you know is safe!

---

### Step 8: **Put a Process in the Background** (Workers doing their job in the background)
Sometimes you want a process to keep working without you watching it. You can send it to the background.

Command:
```bash
ping -c 10 www.hackthebox.eu &
```
What you’re doing: The `&` puts the worker (ping) in the background so it keeps working while you do other things.

**Quick practice tip:** Try this with the ping command. It’ll run in the background, and you can keep working on other tasks.

---

### Step 9: **Check Background Processes** (Who’s working in the background?)
You can check all the workers who are working in the background.

Command:
```bash
jobs
```
What you’re doing: This command shows you all the processes you’ve sent to the background.

**Quick practice tip:** After sending something to the background, run this command to see it listed.

It looks like your `ping` command, even when executed with `&` to send it to the background, isn't behaving as you expect—it seems to still show output in your terminal. This is due to how `ping` works by default, and the behavior of background jobs. Here are a few ways to deal with it:

### 1. **Redirect Output to Suppress Terminal Output**

To properly send the `ping` process to the background **without printing to the terminal**, you need to redirect both **standard output (`stdout`)** and **standard error (`stderr`)** to `/dev/null` so it doesn't display:

```bash
ping -c 10 www.hackthebox.eu > /dev/null 2>&1 &
```

- **`> /dev/null`**: Redirects standard output to the "bit bucket" so nothing gets printed.
- **`2>&1`**: Redirects standard error (`2`) to the same place as standard output (`1`).
- **`&`**: Sends the command to the background.

This should ensure that `ping` runs in the background and you won’t see any further output in your terminal.

### 2. **Using `disown` to Fully Detach the Job**

If you want the background process to continue even after logging out, use `disown`:

```bash
ping -c 10 www.hackthebox.eu > /dev/null 2>&1 &
disown
```

- **`disown`**: Removes the job from the shell’s job table, which means the process will continue running, even if you close the terminal.

### 3. **Explanation for Current Behavior**

What’s happening is that the `ping` command is:
1. Running in the background, but it still **keeps its standard output tied to the terminal**.
2. This causes the terminal to display the output of `ping` even though you technically put it in the background (`&`).
3. Since the output keeps appearing in the terminal, it makes it look like the command isn’t truly in the background.

Using **output redirection** as described in the first solution will prevent `ping` from writing to the terminal, allowing you to use the shell as intended.

### Example Summary Command:

```bash
ping -c 10 www.hackthebox.eu > /dev/null 2>&1 &
```

This way, the command runs quietly in the background, letting you do other things in your terminal without any interruption. You can then use `jobs` to list any background processes, and `fg` to bring them back if needed.

Let me know if you need further assistance with this! 😊

---

### Step 10: **Bring a Process to the Foreground** (Calling a worker back for an update)
If you want a background worker to come back so you can interact with it, use this command.

Command:
```bash
fg <job_id>
```
What you’re doing: You’re bringing the background process back to the front so you can interact with it again.

**Quick practice tip:** After sending a process to the background, use the `jobs` command to find its job ID and bring it back with `fg`.

---

### Step 11: **Execute Multiple Commands** (Giving multiple orders)
Sometimes you want to run several commands one after the other. You can chain them together with semicolons.

Command:
```bash
echo '1'; echo '2'; echo '3'
```
What you’re doing: You’re running multiple commands in sequence. No matter if one fails, the others will still run.

**Quick practice tip:** Play with chaining different commands together using `;`, `&&`, or `|` to see how they work in different scenarios.

---

### **Bonus Tip:** Signals (Giving different types of orders)
Sometimes you need to give a specific order, like restarting a worker without stopping everything.

Command:
```bash
kill -l
```
This shows all the possible signals you can send to a worker (process). You’ll most often use `SIGTERM` (15), `SIGKILL` (9), and `SIGSTOP` (19).

---

By practicing these commands, you’re mastering service and process management like a boss managing a team! You can start, stop, check, and even kill tasks as needed, giving you full control over how your Linux machine runs its background tasks. Keep practicing these, and you'll quickly become efficient in managing services and processes!


1. Systemctl has an option to list particular units defined as "--type=<type>". Piping your systemctl command to grep will help!
 Use the "systemctl" command to list all units of services and submit the unit name with the description "Load AppArmor profiles managed internally by snapd" as the answer.