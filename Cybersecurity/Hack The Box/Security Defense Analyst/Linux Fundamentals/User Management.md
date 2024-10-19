User management is an essential part of Linux administration. Sometimes we need to create new users or add other users to specific groups. Another possibility is to execute commands as a different user. After all, it is not too rare that users of only one specific group have the permissions to view or edit specific files or directories. This, in turn, allows us to collect more information locally on the machine, which can be very important. Let us take a look at the following example of how to execute code as a different user.

#### Execution as a user

  User Management

```shell-session
kcecil1@htb[/htb]$ cat /etc/shadow

cat: /etc/shadow: Permission denied
```

#### Execution as root

  User Management

```shell-session
kcecil1@htb[/htb]$ sudo cat /etc/shadow

root:<SNIP>:18395:0:99999:7:::
daemon:*:17737:0:99999:7:::
bin:*:17737:0:99999:7:::
<SNIP>
```

Here is a list that will help us to better understand and deal with user management.

|**Command**|**Description**|
|---|---|
|`sudo`|Execute command as a different user.|
|`su`|The `su` utility requests appropriate user credentials via PAM and switches to that user ID (the default user is the superuser). A shell is then executed.|
|`useradd`|Creates a new user or update default new user information.|
|`userdel`|Deletes a user account and related files.|
|`usermod`|Modifies a user account.|
|`addgroup`|Adds a group to the system.|
|`delgroup`|Removes a group from the system.|
|`passwd`|Changes user password.|

User management is essential in any operating system, and the best way to become familiar with it is to try out the individual commands in conjunction with their various options.

1. Which option needs to be set to create a home directory for a new user using "useradd" command?
## Question 1

### "Which option needs to be set to create a home directory for a new user using "useradd" command?"

Students need to either consult the man page of `useradd` or use the `--help` flag to find out that the `-m` (short version of `--create-home`) flag is used to create the user's home directory:

Code: shell

```shell
useradd --help | grep 'home directory'
```

  User Management

```shell-session
┌─[eu-academy-2]─[10.10.14.46]─[htb-ac413848@pwnbox-base]─[~]
└──╼ [★]$ useradd --help | grep 'home directory'

  <SNIP>
  -m, --create-home     create the user's home directory
  -M, --no-create-home  do not create the user's home directory
```

2. Which option needs to be set to lock a user account using the "usermod" command? (long version of the option)
[us-academy-4]─[10.10.15.23]─[htb-ac-1239954@htb-6ghswslk9x]─[~]
└──╼ [★]$ usermod --help | grep 'lock'
  -L, --lock                    lock the user account
  -U, --unlock                  unlock the user account

--lock is the answer


3. Which option needs to be set to execute a command as a different user using the "su" command? (long version of the option)

us-academy-4]─[10.10.15.23]─[htb-ac-1239954@htb-6ghswslk9x]─[~]
└──╼ [★]$ su --help | grep 'command'
 -c, --command <command>         pass a single command to the shell with -c
 --session-command <command>     pass a single command to the shell with -c


--command is the answer i guess
