# Linux Fundamentals and Basic Commands

## 1. Introduction to Linux

Linux is an open-source operating system. It is mostly used in servers, cloud computing, networking and cybersecurity.

One thing I found interesting about Linux is that we can control almost everything using commands through the terminal instead of depending on the graphical interface.

Some commonly used Linux distributions are:

- Kali Linux – Mainly used for cybersecurity and penetration testing.
- Ubuntu – Used for general purposes and cloud servers.
- Debian – Known for its stability.
- Fedora – Used by developers and Linux enthusiasts.
- Red Hat Linux – Commonly used in companies and enterprise servers.

### Why do we need Linux in cybersecurity?

Linux is important in cybersecurity because:

- Many servers and cloud machines run on Linux.
- We can manage users and their permissions.
- It provides different tools for networking and security testing.
- We can check system activities and running processes.
- It is useful for monitoring logs and investigating security issues.

## 2. Terminal and Shell

I initially thought both terminal and shell were the same, but they are actually different.

**Terminal:** It is the application where we type commands and see their output.

**Shell:** It is the program that takes our commands, understands them and executes them.

Some commonly used shells are Bash, Zsh and Fish.

Example:

```bash
whoami
```

This command displays the username of the person currently logged into the system.

## 3. Understanding File Paths

A path is basically the location of a file or folder in Linux.

There are two types of paths.

### Absolute Path

It gives the complete location of a file starting from the root directory `/`.

Example:

```bash
/home/kali/Documents/file.txt
```

We can use this path from anywhere in the system.

### Relative Path

It specifies the location based on our current directory.

Example:

```bash
Documents/file.txt
```

If I am currently inside `/home/kali`, this path points to the same file.

Some important symbols:

| Symbol | Use |
|---|---|
| / | Root directory |
| ~ | Home directory |
| . | Current directory |
| .. | Parent directory |

## 4. Basic Linux Commands

I practised some basic commands in Kali Linux. These commands are useful for navigating the system and managing files.

### A. Navigation Commands

**1. pwd**

Used to know which directory I am currently working in.

```bash
pwd
```

**2. ls**

Displays the files and folders present in the current directory.

```bash
ls
```

Some useful options:

```bash
ls -l
ls -a
ls -lh
```

- `-l` shows detailed information.
- `-a` also shows hidden files.
- `-lh` displays file sizes in a readable format.

**3. cd**

Used to move from one directory to another.

```bash
cd Documents
```

To go back to the home directory:

```bash
cd ~
```

To move one directory backwards:

```bash
cd ..
```

### B. File and Folder Commands

**4. touch**

Used to create an empty file.

```bash
touch notes.txt
```

**5. mkdir**

Used to create a new directory.

```bash
mkdir projects
```

We can also create multiple folders inside each other using:

```bash
mkdir -p projects/linux/labs
```

**6. cp**

Used to copy files.

```bash
cp notes.txt backup.txt
```

To copy a complete directory:

```bash
cp -r projects backup_projects
```

**7. mv**

Used to move or rename files.

To rename a file:

```bash
mv notes.txt linux_notes.txt
```

To move a file into another folder:

```bash
mv linux_notes.txt Documents/
```

**8. rm**

Used to delete files.

```bash
rm notes.txt
```

To remove a directory:

```bash
rm -r projects
```

We should be careful while using this command because deleted files may not be recoverable. Especially `rm -rf` should not be used without checking the path.

### C. System Information Commands

**9. whoami**

Displays the current logged-in username.

```bash
whoami
```

**10. uname**

Displays information about the operating system and kernel.

```bash
uname -a
```

**11. date**

Displays the current date and time.

```bash
date
```

**12. uptime**

Shows how long the system has been running.

```bash
uptime
```

It also displays the system load averages.

### D. Permission Commands

**13. chmod**

Used to change permissions of files and directories.

Example:

```bash
chmod 644 file.txt
```

This gives read and write permission to the owner, while the group and other users can only read the file.

**14. chown**

Used to change the owner and group of a file.

Example:

```bash
sudo chown root:root file.txt
```

This changes the owner and group of the file to root.

**15. umask**

Used to check the default permission mask of the system.

```bash
umask
```

For example, if the umask value is `022`, newly created files usually get `644` permissions and directories get `755` permissions.

## 5. Linux File Permissions

This is one of the important topics I learned because permissions decide who can access or modify files in Linux.

There are three basic permissions:

| Permission | Symbol | Value | Meaning |
|---|---|---|---|
| Read | r | 4 | Read the contents |
| Write | w | 2 | Modify the contents |
| Execute | x | 1 | Execute a file |

Linux permissions are divided into three categories:

1. Owner – The user who owns the file.
2. Group – Users who belong to the assigned group.
3. Others – All remaining users.

For example:

```text
-rwxr-xr--
```

Here the permissions are divided like this:

| Category | Permission | Value |
|---|---|---|
| Owner | rwx | 7 |
| Group | r-x | 5 |
| Others | r-- | 4 |

So the numerical permission is `754`.

### Some commonly used permission values

| Value | Meaning |
|---|---|
| 777 | Everyone has read, write and execute permissions |
| 755 | Owner has all permissions, others can read and execute |
| 700 | Only owner has all permissions |
| 644 | Owner can read and write, others can only read |
| 600 | Only owner can read and write |
| 400 | Only owner can read |

### Example

```bash
chmod 600 confidential.txt
```

After executing this command, only the owner will have read and write access to the file.

### Difference between chmod and chown

I understood that both commands are used for file security, but their purposes are different.

| chmod | chown |
|---|---|
| Changes file permissions | Changes file ownership |
| Controls read, write and execute access | Changes owner and group |
| Example: `chmod 644 file.txt` | Example: `chown root:root file.txt` |

## 6. Practical Work in Kali Linux

I created a separate folder to practise file handling and permissions.

First, I created a directory and entered it.

```bash
mkdir ~/linux-practice
cd ~/linux-practice
```

Then I created two files.

```bash
touch confidential.txt
touch public.txt
```

To check their permissions:

```bash
ls -l
```

Next, I changed their permissions.

```bash
chmod 600 confidential.txt
chmod 644 public.txt
```

I checked the permissions again using:

```bash
ls -l
```

I also practised changing ownership.

```bash
sudo chown root:root confidential.txt
```

To verify the changes:

```bash
ls -l
```

Finally, I tried some other permission values.

```bash
chmod 755 public.txt
chmod 700 confidential.txt
```

I also checked the default permission mask:

```bash
umask
```

## 7. What I Understood from This Practice

Some important things I learned from this practice:

1. We should not give unnecessary permissions to users.
2. Using root access for every operation is not a good security practice.
3. Confidential files should have restricted access.
4. Giving `777` permissions can create security problems because anyone can modify the file.
5. We should regularly check file ownership and permissions.

These concepts are useful when managing Linux servers, especially in cloud environments where different users and applications access the same system.

## 8. Conclusion

Through this practice, I learned the basics of Linux and how to work with its terminal.

I also practised commands for navigating directories, creating and managing files, checking system information and changing file permissions.

I understood how Linux handles users, groups and file access. These basics will help me in the upcoming topics related to Linux administration, cloud computing, AWS IAM and Cloud Security.
