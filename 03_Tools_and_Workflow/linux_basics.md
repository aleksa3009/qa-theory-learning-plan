# Linux Basics

## 1. Definition & Purpose

Linux is an open-source, Unix-like operating system used on servers, development environments, and cloud platforms.

### Key Characteristics

* Multiuser: multiple users can use the system simultaneously.
* Multitasking: runs multiple processes at once.
* Hierarchical file system: tree structure starting from `/`.
* Command-line oriented: essential for administration and automation.

### Why QA Engineers Should Know Linux

* Most CI/CD, staging, and production environments run on Linux.
* Tools like Selenium Grid, Jenkins, Docker, API test tools rely on shell usage.
* Easier log inspection, troubleshooting, permissions handling, and process monitoring.

## 2. Linux Terminal (Shell)

* Terminal: text interface for interacting with the OS.
* Shells: Bash, Zsh, Sh.
* Command format: `command [options] [arguments]`
* Example: `ls -l /home/user`

## 3. File System Basics

* `/` – root directory.
* `/home/username` – user home.
* `/bin` – essential binaries.
* `/usr` – user programs.
* `/etc` – configuration.
* `/var/log` – logs.
* `/tmp` – temporary files.

### Paths

* Absolute: `/home/user/docs`
* Relative: `docs/report.txt`

## 4. Navigation Commands

| Command | Purpose                 | Example              |
| ------- | ----------------------- | -------------------- |
| pwd     | Print working directory | `pwd` → `/home/user` |
| ls      | List files              | `ls -l`, `ls -a`     |
| cd      | Change directory        | `cd /etc`, `cd ..`   |
| mkdir   | Create directory        | `mkdir test-folder`  |
| rmdir   | Remove empty directory  | `rmdir old-folder`   |
| tree    | Directory structure     | `tree /home/user`    |

## 5. File Operations

| Command  | Purpose           | Example               |
| -------- | ----------------- | --------------------- |
| touch    | Create empty file | `touch test.txt`      |
| cp       | Copy files        | `cp src.txt dest.txt` |
| mv       | Move/rename       | `mv old.txt new.txt`  |
| rm       | Delete file       | `rm file.txt`         |
| cat      | Show file         | `cat file.txt`        |
| less     | Paginated view    | `less file.txt`       |
| head     | First lines       | `head -n 10 file.txt` |
| tail     | Last lines        | `tail -n 10 file.txt` |
| nano/vim | Edit files        | `nano file.txt`       |

## 6. Permissions & Ownership

* Permissions: read (r), write (w), execute (x).
* Categories: user, group, others.

### View Permissions

```
ls -l
-rw-r--r-- 1 user group 123 file.txt
```

### Modify Permissions

```
chmod 755 script.sh
```

### Change Owner

```
chown user:group file.txt
```

## 7. Searching & Filtering

| Command | Purpose           | Example                        |
| ------- | ----------------- | ------------------------------ |
| grep    | Search text       | `grep "error" /var/log/syslog` |
| find    | Locate files      | `find /home -name "*.log"`     |
| locate  | Fast file lookup  | `locate report.txt`            |
| wc      | Count lines/words | `wc -l file.txt`               |
| sort    | Sort lines        | `sort file.txt`                |
| uniq    | Remove duplicates | `uniq file.txt`                |
| tail -f | Follow logs       | `tail -f /var/log/syslog`      |

## 8. Process Management

| Command  | Purpose               | Example          |
| -------- | --------------------- | ---------------- |
| ps       | List processes        | `ps aux`         |
| top/htop | Live system usage     | `top`            |
| kill     | Kill by PID           | `kill 1234`      |
| killall  | Kill by name          | `killall chrome` |
| jobs     | List background jobs  | `jobs`           |
| bg/fg    | Background/foreground | `bg %1`          |

## 9. Networking & System Info

| Command | Purpose            | Example                    |
| ------- | ------------------ | -------------------------- |
| ping    | Test connectivity  | `ping google.com`          |
| curl    | HTTP request       | `curl https://example.com` |
| ip a    | Network interfaces | `ip a`                     |
| df      | Disk usage         | `df -h`                    |
| du      | Directory size     | `du -sh folder/`           |
| uname   | System info        | `uname -a`                 |
| whoami  | Current user       | `whoami`                   |

## 10. Package Management

### Debian/Ubuntu

```
sudo apt update
sudo apt install tree
```

### RedHat/CentOS

```
sudo yum install nano
```

## 11. Environment Variables

* Show variable:

```
echo $PATH
```

* Set temporary variable:

```
export VAR=value
```

* Make permanent: add to `.bashrc`.