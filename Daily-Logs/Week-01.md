# Week 1 – Daily Logs

## Day 1 – 16 November 2026 (Monday)

### Today's Focus
GitHub setup, Kali Linux environment and Linux fundamentals.

### What I worked on

1. Created my GitHub repository named `cloud-security-journey` to maintain all my learning notes and practical work.
2. Set up the repository structure for different topics like Linux, Networking, AWS, IAM and GRC.
3. Prepared my Kali Linux environment using VMware.
4. Started learning basic Linux commands and how to work with the terminal.
5. Practised basic commands for navigating directories and managing files.
6. Learned about Linux, shells, terminals and file paths.

### Commands Practised

- `pwd`
- `ls`
- `cd`
- `mkdir`
- `touch`
- `cp`
- `mv`
- `rm`
- `whoami`
- `uname`

### What I Learned

- Basic understanding of Linux and its importance in cybersecurity.
- Difference between a terminal and a shell.
- How to navigate through directories.
- How to create, copy, move and delete files.
- How to maintain and organise my work using GitHub.

### Challenges

- Had to prepare my Kali Linux environment in VMware.
- Needed some time to get comfortable with the Linux terminal and commands.

### Pending Work

- Complete Linux commands documentation.
- Update the main repository README.
# Week 1 – Daily Logs

## Day 2 – 17 November 2026 (Tuesday)

### Today's Focus

Linux users, groups, file ownership and permissions.

### What I worked on

1. Learned how Linux manages users and groups and how user accounts are stored in the system.
2. Explored `/etc/passwd` and `/etc/group` to understand user information, UIDs, GIDs and group memberships.
3. Checked my own Kali Linux account and identified its primary and supplementary groups.
4. Used `ls -l` and `stat` to examine file permissions, ownership, inodes and timestamps.
5. Compared the permissions of `/etc/passwd` and `/etc/shadow` and understood why sensitive files have restricted access.
6. Practised changing file permissions using `chmod` with both numeric and symbolic methods.
7. Used `chown` and `chgrp` to change file ownership and group ownership.
8. Learned how `umask` works and experimented with different values to understand default permissions.
9. Created a separate `permission-lab` directory and performed practical exercises on files and directories.
10. Tested different permission configurations, including 777, 755, 644, 600 and 700.

### Commands Practised

- `whoami`
- `id`
- `groups`
- `cat /etc/passwd`
- `cat /etc/group`
- `grep`
- `ls -l`
- `ls -ld`
- `stat`
- `chmod`
- `chown`
- `chgrp`
- `umask`
- `mkdir`
- `touch`
- `echo`
- `cat`

### What I Learned

- How Linux identifies users using UID and groups using GID.
- Difference between primary and supplementary groups.
- How `/etc/passwd` and `/etc/shadow` are used.
- How to read Linux file permission strings.
- Difference between numeric and symbolic permissions.
- How to change file ownership and group ownership.
- How umask controls default permissions for newly created files and directories.
- Why unrestricted permissions can create security risks.
- Importance of the principle of least privilege.

### Challenges

- Initially found it difficult to understand numeric permissions and how their values are calculated.
- Needed some practice to understand the difference between `chmod`, `chown` and `chgrp`.
- Experimented with different umask values to understand how they affect newly created files and directories.

### Practical Work

Created a separate `permission-lab` directory and performed experiments with different file permissions and ownership settings.

Also tested how restrictive permissions help protect sensitive files from unauthorized access.

### Overall Progress

Day 2 was mainly focused on understanding Linux access control. I now have a better understanding of how Linux manages users, groups, ownership and permissions.

The practical exercises helped me understand why proper permission management is important for securing Linux systems, especially when working with servers and cloud environments.

**Status: Day 2 – Completed**

Day 1 was mainly about setting up my learning environment and getting started with Linux. I now have my GitHub repository ready and a working Kali Linux environment for upcoming practical exercises.

**Status: Day 1 – Mostly Completed**
