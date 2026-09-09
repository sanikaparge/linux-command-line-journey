# 🐧 Linux Command Line Journey

> A structured hands-on journey to learn Linux from fundamentals to DevOps-level administration and automation.

![Linux](https://img.shields.io/badge/Linux-Command%20Line-black?logo=linux)
![Ubuntu](https://img.shields.io/badge/Ubuntu-26.04-orange?logo=ubuntu)
![DevOps](https://img.shields.io/badge/Focus-DevOps-blue)
![Git](https://img.shields.io/badge/Version%20Control-Git-red?logo=git)

---

## 📚 About This Repository

This repository documents my learning journey with **Linux Command Line** and Linux administration concepts required for **DevOps, Cloud Computing, System Administration, and Software Engineering**.

The goal is not only to memorize commands but to understand:

* Why Linux is used in DevOps
* How the Linux operating system works
* How files and directories are managed
* How permissions and users work
* How processes and services are managed
* How networking works
* How applications are installed and managed
* How servers are accessed remotely
* How shell scripts automate tasks
* How Linux is used in real-world DevOps environments

---

# 🗺️ Linux Learning Roadmap

```text
Linux Fundamentals
       ↓
Linux Architecture
       ↓
File System
       ↓
File & Directory Management
       ↓
Text Processing & Searching
       ↓
Permissions
       ↓
Users & Groups
       ↓
Processes
       ↓
Services
       ↓
Package Management
       ↓
Networking
       ↓
Storage
       ↓
SSH
       ↓
Environment Variables
       ↓
Shell Scripting
       ↓
Cron Jobs
       ↓
Logs
       ↓
DevOps Linux Practices
       ↓
Automation & Troubleshooting
```

---

# 1. 🐧 Introduction to Linux

## What is Linux?

Linux is an open-source operating system based on the Linux kernel.

It is widely used in:

* Cloud computing
* DevOps
* Web servers
* Databases
* Networking
* Containers
* Kubernetes
* CI/CD systems
* Automation
* Cybersecurity
* Embedded systems

Popular Linux distributions include:

* Ubuntu
* Debian
* Fedora
* Red Hat Enterprise Linux
* Rocky Linux
* AlmaLinux
* Amazon Linux
* Arch Linux

---

## Why Linux is Important for DevOps

Most cloud servers and DevOps infrastructure run on Linux.

Linux provides:

* Stability
* Security
* Automation
* Powerful command-line tools
* Remote administration
* Process management
* Networking tools
* Scripting capabilities
* Container support

A DevOps engineer should be comfortable working from a Linux terminal.

---

# 2. 🏗️ Linux Architecture

The major components of a Linux system are:

```text
+---------------------------+
|       Applications        |
+---------------------------+
|          Shell            |
+---------------------------+
|         Utilities         |
+---------------------------+
|          Kernel           |
+---------------------------+
|         Hardware          |
+---------------------------+
```

## Hardware

Physical components such as:

* CPU
* RAM
* Disk
* Network interface
* USB devices

## Kernel

The kernel is the core component of Linux.

It manages:

* CPU
* Memory
* Processes
* Devices
* Networking
* File systems

## Shell

The shell provides an interface between the user and the operating system.

Common shells:

* Bash
* Zsh
* Fish
* Sh

Check your shell:

```bash
echo $SHELL
```

Check Bash version:

```bash
bash --version
```

---

# 3. 🖥️ Linux Command Line

The Linux terminal allows administrators and developers to interact with the operating system.

Example:

```bash
ls
```

General command structure:

```text
command + options + arguments
```

Example:

```bash
ls -la /home
```

Where:

* `ls` → command
* `-la` → options
* `/home` → argument

---

# 4. 📂 Linux File System

Linux uses a hierarchical file system.

The root directory is:

```text
/
```

Important directories:

```text
/
├── bin
├── boot
├── dev
├── etc
├── home
├── lib
├── media
├── mnt
├── opt
├── proc
├── root
├── run
├── sbin
├── tmp
├── usr
└── var
```

## Important Directories

### `/`

Root of the entire Linux file system.

### `/home`

Contains normal users' home directories.

Example:

```text
/home/ubuntu
```

### `/root`

Home directory of the root user.

### `/etc`

Contains system configuration files.

Examples:

```text
/etc/passwd
/etc/hosts
/etc/ssh/
/etc/systemd/
```

### `/var`

Contains frequently changing data.

Examples:

```text
/var/log
/var/cache
/var/lib
```

### `/tmp`

Temporary files.

### `/usr`

Contains many user applications, libraries, and utilities.

### `/opt`

Commonly used for optional or third-party software.

### `/dev`

Contains device files.

### `/proc`

Virtual file system containing information about processes and the kernel.

---

# 5. 📍 Navigation Commands

## `pwd`

Displays the current working directory.

```bash
pwd
```

Example:

```text
/home/ubuntu
```

---

## `ls`

Lists files and directories.

```bash
ls
```

Detailed listing:

```bash
ls -l
```

Show hidden files:

```bash
ls -a
```

Detailed listing including hidden files:

```bash
ls -la
```

Human-readable file sizes:

```bash
ls -lh
```

---

## `cd`

Changes directory.

```bash
cd /etc
```

Go to home directory:

```bash
cd ~
```

Go one directory back:

```bash
cd ..
```

Go to previous directory:

```bash
cd -
```

---

# 6. 📁 File and Directory Management

## Create a directory

```bash
mkdir projects
```

Create nested directories:

```bash
mkdir -p project/src/app
```

---

## Create a file

```bash
touch file.txt
```

---

## Copy files

```bash
cp file.txt backup.txt
```

Copy a directory:

```bash
cp -r project backup-project
```

---

## Move or rename

```bash
mv file.txt newfile.txt
```

Move file:

```bash
mv file.txt /tmp/
```

---

## Delete a file

```bash
rm file.txt
```

Delete a directory:

```bash
rm -r project
```

Force deletion:

```bash
rm -rf project
```

> ⚠️ `rm -rf` is powerful. Always verify the path before running it.

---

# 7. 📄 Viewing Files

## `cat`

```bash
cat file.txt
```

Display multiple files:

```bash
cat file1.txt file2.txt
```

---

## `less`

```bash
less largefile.log
```

Useful for reading large files.

---

## `head`

Show first lines:

```bash
head file.txt
```

Show first 20 lines:

```bash
head -n 20 file.txt
```

---

## `tail`

Show last lines:

```bash
tail file.txt
```

Monitor a log continuously:

```bash
tail -f application.log
```

This is extremely useful for DevOps troubleshooting.

---

# 8. 🔎 Searching Files and Text

## `find`

Search for files:

```bash
find /home -name "test.txt"
```

Find directories:

```bash
find /home -type d -name "project"
```

Find files by extension:

```bash
find . -name "*.log"
```

---

## `grep`

Search text inside files:

```bash
grep "error" application.log
```

Case-insensitive search:

```bash
grep -i "error" application.log
```

Recursive search:

```bash
grep -r "database" .
```

Show line numbers:

```bash
grep -n "error" application.log
```

---

# 9. ✂️ Text Processing Commands

Important Linux text-processing tools:

```bash
cut
sort
uniq
wc
tr
awk
sed
```

## `wc`

Count lines:

```bash
wc -l file.txt
```

Count words:

```bash
wc -w file.txt
```

---

## `sort`

```bash
sort names.txt
```

---

## `uniq`

Remove consecutive duplicate lines:

```bash
uniq names.txt
```

---

## `cut`

Extract columns:

```bash
cut -d ":" -f 1 /etc/passwd
```

---

## `sed`

Replace text:

```bash
sed 's/old/new/g' file.txt
```

---

## `awk`

Process structured text:

```bash
awk '{print $1}' file.txt
```

These commands are heavily used in Linux administration and automation.

---

# 10. 🔐 Linux File Permissions

Linux permissions control who can access files and directories.

Three permission categories:

```text
User
Group
Others
```

Three basic permissions:

```text
r = read
w = write
x = execute
```

Example:

```text
-rwxr-xr--
```

Meaning:

```text
Owner  → rwx
Group  → r-x
Others → r--
```

---

## Check permissions

```bash
ls -l
```

---

## `chmod`

Change permissions.

Example:

```bash
chmod 755 script.sh
```

Permission meaning:

```text
7 = rwx
5 = r-x
5 = r-x
```

Another example:

```bash
chmod 644 file.txt
```

---

## Symbolic permissions

```bash
chmod u+x script.sh
```

Remove write permission:

```bash
chmod g-w file.txt
```

---

# 11. 👤 Users and Groups

Linux supports multiple users.

Check current user:

```bash
whoami
```

User information:

```bash
id
```

List logged-in users:

```bash
who
```

---

## Create a user

```bash
sudo useradd username
```

Create with home directory:

```bash
sudo useradd -m username
```

Set password:

```bash
sudo passwd username
```

---

## Create a group

```bash
sudo groupadd developers
```

Add user to group:

```bash
sudo usermod -aG developers username
```

---

## Important files

```text
/etc/passwd
/etc/shadow
/etc/group
```

---

# 12. 👑 Root and sudo

Root is the administrative user in Linux.

Check current user:

```bash
whoami
```

Run a command with administrative privileges:

```bash
sudo command
```

Example:

```bash
sudo apt update
```

Switch to root:

```bash
sudo -i
```

Exit:

```bash
exit
```

---

# 13. ⚙️ Process Management

A process is a running instance of a program.

View processes:

```bash
ps
```

View all processes:

```bash
ps aux
```

Real-time process monitoring:

```bash
top
```

If installed:

```bash
htop
```

---

## Find a process

```bash
ps aux | grep nginx
```

---

## Kill a process

```bash
kill PID
```

Force kill:

```bash
kill -9 PID
```

Terminate by name:

```bash
pkill nginx
```

---

# 14. 🔄 Background and Foreground Processes

Run command in background:

```bash
command &
```

View jobs:

```bash
jobs
```

Move job to foreground:

```bash
fg
```

Move job to background:

```bash
bg
```

---

# 15. 🧩 Linux Services

Modern Ubuntu systems commonly use `systemd` to manage services.

Check service status:

```bash
sudo systemctl status nginx
```

Start:

```bash
sudo systemctl start nginx
```

Stop:

```bash
sudo systemctl stop nginx
```

Restart:

```bash
sudo systemctl restart nginx
```

Enable at boot:

```bash
sudo systemctl enable nginx
```

Disable:

```bash
sudo systemctl disable nginx
```

---

# 16. 📦 Package Management

Ubuntu uses the APT package manager.

Update package information:

```bash
sudo apt update
```

Upgrade packages:

```bash
sudo apt upgrade
```

Install software:

```bash
sudo apt install nginx
```

Remove software:

```bash
sudo apt remove nginx
```

Search packages:

```bash
apt search nginx
```

Show package information:

```bash
apt show nginx
```

---

# 17. 🌐 Linux Networking

Networking is extremely important for DevOps.

Check IP addresses:

```bash
ip addr
```

Check routing:

```bash
ip route
```

Check hostname:

```bash
hostname
```

---

## `ping`

Test connectivity:

```bash
ping google.com
```

---

## `curl`

Make HTTP requests:

```bash
curl https://example.com
```

Check HTTP headers:

```bash
curl -I https://example.com
```

---

## `wget`

Download files:

```bash
wget https://example.com/file.zip
```

---

## Check listening ports

```bash
ss -tuln
```

Find a particular port:

```bash
ss -tuln | grep 80
```

---

## DNS

```bash
nslookup google.com
```

If available:

```bash
dig google.com
```

---

# 18. 🔥 Firewall

Ubuntu commonly uses UFW.

Check status:

```bash
sudo ufw status
```

Enable:

```bash
sudo ufw enable
```

Allow SSH:

```bash
sudo ufw allow 22
```

Allow HTTP:

```bash
sudo ufw allow 80
```

Allow HTTPS:

```bash
sudo ufw allow 443
```

> On AWS EC2, remember that network access is also controlled by the EC2 Security Group.

---

# 19. 💾 Disk and Storage Management

Check disk usage:

```bash
df -h
```

Check directory size:

```bash
du -sh /var/log
```

Check block devices:

```bash
lsblk
```

Find large directories:

```bash
du -h --max-depth=1 /
```

---

# 20. 🗜️ Compression and Archives

Create tar archive:

```bash
tar -cvf backup.tar project/
```

Create compressed archive:

```bash
tar -czvf backup.tar.gz project/
```

Extract:

```bash
tar -xzvf backup.tar.gz
```

List archive contents:

```bash
tar -tzvf backup.tar.gz
```

---

# 21. 🌱 Environment Variables

List environment variables:

```bash
env
```

Print a variable:

```bash
echo $HOME
```

Create a variable:

```bash
APP_ENV=production
```

Export variable:

```bash
export APP_ENV=production
```

Check:

```bash
echo $APP_ENV
```

Common variables:

```text
HOME
PATH
USER
SHELL
PWD
```

---

# 22. 🔑 SSH — Secure Shell

SSH is one of the most important technologies for Linux and DevOps.

It allows remote access to Linux servers.

Basic syntax:

```bash
ssh username@server-ip
```

AWS example:

```bash
ssh -i key.pem ubuntu@SERVER_IP
```

---

## Generate SSH key

```bash
ssh-keygen -t ed25519
```

Files:

```text
~/.ssh/id_ed25519
~/.ssh/id_ed25519.pub
```

Private key:

```text
id_ed25519
```

Public key:

```text
id_ed25519.pub
```

Never share your private key.

---

# 23. 📤 SCP — Secure Copy

Copy local file to remote server:

```bash
scp file.txt user@server:/home/user/
```

Copy directory:

```bash
scp -r project/ user@server:/home/user/
```

Copy remote file to local:

```bash
scp user@server:/home/user/file.txt .
```

---

# 24. 🔄 Environment and PATH

Display PATH:

```bash
echo $PATH
```

Add a directory temporarily:

```bash
export PATH=$PATH:/custom/path
```

Find command location:

```bash
which python
```

or:

```bash
which git
```

---

# 25. 📝 Vim and Nano

## Nano

Open file:

```bash
nano file.txt
```

Save:

```text
Ctrl + O
```

Exit:

```text
Ctrl + X
```

---

## Vim

Open file:

```bash
vim file.txt
```

Basic commands:

```text
i      → Insert mode
Esc    → Command mode
:w     → Save
:q     → Quit
:wq    → Save and quit
:q!    → Quit without saving
```

---

# 26. 🔀 Pipes and Redirection

Linux commands can be combined using pipes.

Example:

```bash
ps aux | grep nginx
```

The output of the first command becomes input to the second command.

---

## Output redirection

```bash
ls > files.txt
```

Append:

```bash
ls >> files.txt
```

Input redirection:

```bash
command < file.txt
```

Error redirection:

```bash
command 2> error.log
```

Both output and errors:

```bash
command > output.log 2>&1
```

---

# 27. 🔗 Command Chaining

Run commands sequentially:

```bash
command1 ; command2
```

Run second command only if first succeeds:

```bash
command1 && command2
```

Run second command only if first fails:

```bash
command1 || command2
```

Example:

```bash
mkdir project && cd project
```

---

# 28. 🐚 Bash Shell Scripting

Shell scripting is used to automate repetitive tasks.

Basic script:

```bash
#!/bin/bash

echo "Hello DevOps"
```

Save as:

```text
hello.sh
```

Make executable:

```bash
chmod +x hello.sh
```

Run:

```bash
./hello.sh
```

---

# 29. 📌 Shell Variables

```bash
#!/bin/bash

NAME="Linux"

echo "Learning $NAME"
```

---

# 30. 🔢 User Input

```bash
#!/bin/bash

echo "Enter your name:"
read NAME

echo "Hello $NAME"
```

---

# 31. 🔀 Conditional Statements

```bash
#!/bin/bash

if [ "$1" == "dev" ]
then
    echo "Development environment"
else
    echo "Other environment"
fi
```

---

# 32. 🔁 Loops

## For loop

```bash
for i in 1 2 3 4 5
do
    echo $i
done
```

## While loop

```bash
COUNT=1

while [ $COUNT -le 5 ]
do
    echo $COUNT
    COUNT=$((COUNT+1))
done
```

---

# 33. 🧩 Functions

```bash
#!/bin/bash

greet() {
    echo "Hello DevOps"
}

greet
```

---

# 34. 📥 Command-Line Arguments

Script:

```bash
#!/bin/bash

echo "First argument: $1"
echo "Second argument: $2"
```

Run:

```bash
./script.sh DevOps Linux
```

---

# 35. ⏰ Cron Jobs

Cron is used to schedule recurring tasks.

View cron jobs:

```bash
crontab -l
```

Edit cron jobs:

```bash
crontab -e
```

Example:

```text
0 2 * * * /home/ubuntu/backup.sh
```

This runs the script every day at 2:00 AM.

---

# 36. 📜 Linux Logs

Important log directory:

```text
/var/log
```

View logs:

```bash
ls /var/log
```

Common logs include:

```text
/var/log/syslog
/var/log/auth.log
```

View recent logs:

```bash
tail -f /var/log/syslog
```

For systemd services:

```bash
journalctl
```

View service logs:

```bash
journalctl -u nginx
```

Follow logs:

```bash
journalctl -u nginx -f
```

---

# 37. 🧪 System Information

Kernel information:

```bash
uname -a
```

Hostname:

```bash
hostname
```

CPU information:

```bash
lscpu
```

Memory:

```bash
free -h
```

Disk:

```bash
df -h
```

Uptime:

```bash
uptime
```

Operating system:

```bash
cat /etc/os-release
```

---

# 38. 🔍 Troubleshooting Commands

Check CPU:

```bash
top
```

Check memory:

```bash
free -h
```

Check disk:

```bash
df -h
```

Check processes:

```bash
ps aux
```

Check ports:

```bash
ss -tuln
```

Check connectivity:

```bash
ping SERVER_IP
```

Check HTTP:

```bash
curl -I http://SERVER_IP
```

Check service:

```bash
systemctl status SERVICE
```

Check logs:

```bash
journalctl -u SERVICE
```

---

# 39. 🐧 Linux + Web Server Practice

Install Nginx:

```bash
sudo apt update
sudo apt install nginx -y
```

Check status:

```bash
sudo systemctl status nginx
```

Start:

```bash
sudo systemctl start nginx
```

Enable at boot:

```bash
sudo systemctl enable nginx
```

Test locally:

```bash
curl http://localhost
```

Check port:

```bash
ss -tuln | grep 80
```

---

# 40. ☁️ Linux on AWS EC2

Linux is heavily used with AWS EC2.

Typical architecture:

```text
Developer
    |
    | SSH
    ↓
AWS EC2
Ubuntu Linux
    |
    ├── Application
    ├── Nginx
    ├── Git
    ├── Docker
    └── Monitoring
```

Important EC2 Linux tasks:

* Connect using SSH
* Install packages
* Configure users
* Manage services
* Configure firewall
* Deploy applications
* Check logs
* Monitor resources
* Automate tasks

---

# 41. 🔧 Linux Commands Commonly Used in DevOps

| Command      | DevOps Usage           |
| ------------ | ---------------------- |
| `ssh`        | Remote server access   |
| `scp`        | File transfer          |
| `git`        | Source code management |
| `systemctl`  | Service management     |
| `journalctl` | Log management         |
| `grep`       | Search logs            |
| `awk`        | Data processing        |
| `sed`        | Text manipulation      |
| `curl`       | API/HTTP testing       |
| `wget`       | Download files         |
| `ps`         | Process monitoring     |
| `top`        | Resource monitoring    |
| `df`         | Disk monitoring        |
| `du`         | Directory size         |
| `chmod`      | Permissions            |
| `chown`      | Ownership              |
| `cron`       | Scheduling             |
| `bash`       | Automation             |

---

# 42. 🔄 Linux + Git Workflow

A typical DevOps workflow:

```text
Developer
    ↓
Git
    ↓
GitHub
    ↓
Linux Server
    ↓
Application Deployment
```

Common commands:

```bash
git clone REPOSITORY_URL
git status
git add .
git commit -m "message"
git push
git pull
```

---

# 43. 🧪 Practical Exercises

## Exercise 1 — File Management

Create:

```text
devops/
├── linux/
├── scripts/
└── logs/
```

Commands:

```bash
mkdir -p devops/{linux,scripts,logs}
```

---

## Exercise 2 — Permissions

Create a script:

```bash
touch script.sh
chmod +x script.sh
```

Verify:

```bash
ls -l script.sh
```

---

## Exercise 3 — Process Management

Start a process:

```bash
sleep 500 &
```

Find it:

```bash
ps aux | grep sleep
```

Terminate it:

```bash
kill PID
```

---

## Exercise 4 — Networking

Check:

```bash
ip addr
ip route
ss -tuln
```

Test:

```bash
ping google.com
curl https://example.com
```

---

## Exercise 5 — Disk Monitoring

Run:

```bash
df -h
du -sh ~
lsblk
```

---

## Exercise 6 — Log Monitoring

Run:

```bash
sudo tail -f /var/log/syslog
```

Open another terminal and perform system activity.

Observe the logs.

---

## Exercise 7 — Service Management

Install Nginx:

```bash
sudo apt install nginx -y
```

Then:

```bash
sudo systemctl status nginx
sudo systemctl restart nginx
sudo systemctl enable nginx
```

---

## Exercise 8 — Shell Script

Create:

```bash
nano system-info.sh
```

Add:

```bash
#!/bin/bash

echo "===== System Information ====="

echo "Hostname:"
hostname

echo "User:"
whoami

echo "Kernel:"
uname -r

echo "Memory:"
free -h

echo "Disk:"
df -h
```

Run:

```bash
chmod +x system-info.sh
./system-info.sh
```

---

# 44. 🚀 DevOps Mini Projects

## Project 1 — Server Health Check

Create a Bash script that checks:

* CPU usage
* Memory usage
* Disk usage
* Running services
* Server uptime

---

## Project 2 — Automated Backup

Create a script that:

1. Takes a directory
2. Creates a `.tar.gz` backup
3. Stores it in a backup directory
4. Adds the date to the filename

Example:

```text
backup-2026-09-09.tar.gz
```

---

## Project 3 — Log Monitoring

Create a script that:

* Reads application logs
* Searches for `ERROR`
* Counts errors
* Displays the latest errors

Useful commands:

```bash
grep
wc
tail
awk
```

---

## Project 4 — Nginx Deployment

Practice:

```text
EC2 Ubuntu
    ↓
Install Nginx
    ↓
Configure Nginx
    ↓
Deploy HTML
    ↓
Open port 80
    ↓
Access from browser
```

---

# 45. 🧠 Linux Interview Questions

## Beginner

1. What is Linux?
2. What is the Linux kernel?
3. What is a shell?
4. What is Bash?
5. What is the root directory?
6. What is the difference between `/` and `/root`?
7. What is the purpose of `/etc`?
8. What is `/var/log`?
9. What does `pwd` do?
10. What does `ls -la` do?

## Intermediate

11. What is a Linux process?
12. What is the difference between a process and a service?
13. What is `systemd`?
14. What is `systemctl`?
15. What is `sudo`?
16. What are Linux permissions?
17. Explain `chmod 755`.
18. What is the difference between `chmod` and `chown`?
19. What is SSH?
20. What is the difference between SSH and SCP?

## DevOps

21. Why is Linux widely used in DevOps?
22. How do you troubleshoot a server with high CPU?
23. How do you check memory usage?
24. How do you check disk usage?
25. How do you find which process is using a port?
26. How do you check whether a service is running?
27. How do you monitor logs?
28. How do you automate tasks in Linux?
29. What is a cron job?
30. How is Bash scripting useful in DevOps?

---

# 46. 📋 Quick Command Cheat Sheet

```bash
# Navigation
pwd
ls
ls -la
cd
cd ..
cd ~

# Files
touch
cat
less
head
tail
cp
mv
rm

# Directories
mkdir
rmdir
find

# Search
grep
find

# Permissions
chmod
chown
chgrp

# Users
whoami
id
who
useradd
usermod
passwd

# Processes
ps
top
htop
kill
pkill
jobs
fg
bg

# Services
systemctl
journalctl

# Packages
apt

# Networking
ip
ping
curl
wget
ss
nslookup
dig

# Storage
df
du
lsblk

# Compression
tar
gzip
zip
unzip

# Remote access
ssh
scp

# Shell
bash
echo
export
read

# Text processing
grep
awk
sed
cut
sort
uniq
wc

# Scheduling
cron
crontab

# System information
uname
hostname
free
uptime
lscpu
```

---

# 47. 🎯 Learning Goals

After completing this journey, I should be able to:

* [ ] Understand Linux architecture
* [ ] Navigate the Linux file system
* [ ] Create and manage files/directories
* [ ] Search files and text
* [ ] Work with Linux permissions
* [ ] Manage users and groups
* [ ] Manage processes
* [ ] Manage system services
* [ ] Install and manage packages
* [ ] Troubleshoot networking
* [ ] Monitor disk and memory
* [ ] Work with Linux logs
* [ ] Connect to servers using SSH
* [ ] Transfer files using SCP
* [ ] Configure environment variables
* [ ] Write Bash scripts
* [ ] Schedule tasks with cron
* [ ] Deploy applications on Linux
* [ ] Use Linux in AWS environments
* [ ] Apply Linux skills to DevOps workflows

---

# 48. 🏆 Final DevOps Linux Checklist

```text
Linux Fundamentals             ✅
Linux File System               ✅
Basic Commands                  ✅
File Management                 ✅
Text Processing                 ✅
Permissions                     ✅
Users & Groups                  ✅
Process Management              ✅
Service Management              ✅
Package Management              ✅
Networking                      ✅
Storage                         ✅
SSH                             ✅
SCP                             ✅
Environment Variables           ✅
Bash Scripting                  ✅
Cron Jobs                       ✅
Log Management                  ✅
Troubleshooting                 ✅
AWS EC2 Linux                   ✅
Git + Linux                     ✅
DevOps Automation               ✅
```

---

# 📌 Environment Used

This learning journey is practiced using:

```text
Operating System : Ubuntu Linux
Environment      : AWS EC2
Shell            : Bash
Version Control  : Git
Focus            : Linux + DevOps
```

Check environment:

```bash
cat /etc/os-release
git --version
bash --version
```

---

# 🌱 Learning Philosophy

> **Don't just memorize Linux commands. Understand what the command does, why it is used, and how it solves a real-world problem.**

The objective of this repository is to continuously document practical Linux knowledge and build a strong foundation for:

**Linux → Git → Docker → Jenkins → AWS → Kubernetes → Terraform → CI/CD → DevOps**

---

## ⭐ Repository

GitHub Repository:

**linux-command-line-journey**

---

## 👩‍💻 Author

**Sanika Parge**

Learning and practicing:

```text
Linux
DevOps
Cloud Computing
AWS
Automation
```

---

⭐ If this repository helps you learn Linux, consider giving it a star!

