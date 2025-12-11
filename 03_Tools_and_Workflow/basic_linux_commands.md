# Basic Linux Commands

## 1. Navigate the Filesystem

### 1.1 Definition

Filesystem represents the directory and folder structure of the operating system.

### 1.2 Key Commands

1. **ls**: Lists items in the current directory.
2. **ls /**: Shows the root filesystem.
3. **ls /home**: Shows system users.
4. **ls -l**: Long listing format.
5. **ll**: Alias for long listing.
6. **pwd**: Prints the current working directory.
7. **cd**: Changes directory.
8. **~**: Shortcut to the home directory.
9. **clear / Ctrl + L**: Clears the terminal.

### 1.3 File Types

* **d**: Directory
* **-**: File
* **l**: Link

### 1.4 Color Indicators

* Blue: Directory
* White: File
* Green: Executable

### 1.5 Root Folder

The root folder `/` is the top-level directory containing the entire filesystem.

## 2. Basic File Editing

### 2.1 Commands

1. **touch**: Creates an empty file or updates timestamps.
2. **cat**: Displays file contents or concatenates files.
3. **nano**: Basic terminal text editor.

### 2.2 Concepts

* **Buffer**: Temporary memory area used when editing files.
* **Ctrl + O**: Save file in nano.
* **which**: Shows full path of an executable.

## 3. Moving and Renaming Files

### 3.1 Commands

1. **cp**: Copies files or directories.
2. **diff**: Compares files line-by-line.
3. **rm**: Deletes files.
4. **rm -r**: Removes directories recursively.
5. **mv**: Moves or renames files.
6. **mkdir**: Creates a directory.

### 3.2 Wildcards and Paths

* `*`: Matches any number of characters.
* `.`: Current directory.
* `..`: Parent directory.

## 4. Bash Configuration File

### 4.1 Concepts

1. **Bash**: Shell and scripting language.
2. **Prompt**: Text showing the shell is ready for input.
3. **jobs**: Shows background jobs.
4. **ls -a**: Shows all files, including hidden.
5. **#**: Indicates comment.
6. **alias**: Creates command shortcuts.
7. **.bashrc**: Configuration file executed at shell startup.

## 5. Understanding Permissions

### 5.1 Basics

* **r**: Read
* **w**: Write
* **x**: Execute

### 5.2 Structure

Example: `-rwxr-xr--`

* First character: Type
* Next three: Owner
* Next three: Group
* Last three: Others

### 5.3 chmod Examples

* `chmod u+x file`
* `chmod g-w file`
* `chmod o=r file`

## 6. Checking Resource Usage

### 6.1 Commands

1. **free -m**: Shows memory usage.
2. **df**: Shows disk space.
3. **df -i**: Shows inode usage.
4. **htop**: Interactive system monitor.
5. **uptime**: Shows system runtime and load.

## 7. Package Management (Debian-Based)

### 7.1 Commands

1. **apt update**: Updates package list.
2. **apt search**: Searches packages.
3. **apt install**: Installs packages.
4. **apt remove**: Removes packages.
5. **apt autoremove**: Removes unused dependencies.
6. **apt upgrade**: Standard upgrade.
7. **apt dist-upgrade**: Handles dependency changes.
8. **sudo reboot**: Reboots system.

## 8. Managing systemd Units

### 8.1 Commands

1. **systemctl status**: Shows service status.
2. **systemctl disable**: Disables service.
3. **sudo systemctl stop**: Stops service.
4. **sudo systemctl enable**: Enables service.
5. **systemctl restart**: Restarts service.

## 9. Viewing Logs

### 9.1 Commands

1. **head**: First lines of a file.
2. **tail**: Last lines of a file.
3. **journalctl**: System logs.
4. **journalctl -f**: Live logs.
5. **journalctl -u service**: Service logs.

## 10. Managing Users

### 10.1 Concepts

* `/etc`: System configuration directory.
* `/etc/shadow`: Encrypted password storage.
* **group**: Collection of users.
* **adm**: Group for reading system logs.
* **ansible**: Automation tool.

### 10.2 Commands

1. **sudo adduser**: Creates a user.
2. **logout**: Ends the session.
3. **sudo su -**: Switches to root.
4. **sudo userdel -r**: Deletes user.
5. **sudo groupadd**: Creates a group.
6. **groups**: Shows group membership.
7. **sudo gpasswd**: Manages group membership.
8. **sudo groupdel**: Deletes a group.

## 11. Bash History

### 11.1 Commands

1. **↑**: Navigate history.
2. **history**: Shows history.
3. **!number**: Re-runs a command.

## 12. Output Redirection

### 12.1 Commands

1. **less**: Paginated view.
2. **more**: Forward-only pagination.
3. **>**: Redirect output (overwrite).
4. **>>**: Redirect output (append).
5. **grep**: Search text.
6. **sort**: Sort lines.
7. **uniq**: Remove duplicates.
8. **wc**: Count lines, words, characters.

## 13. Streams

### 13.1 Concepts

* **echo**: Outputs text.
* **stdin**: Standard input.
* **stdout**: Standard output.
* **stderr**: Standard error.

## 14. Variables

### 14.1 Syntax

VAR="value"

echo $VAR

### 14.2 Additional Notes

* No spaces around =.
* Use `export` to persist in child processes.
* Example:
  FILE="log.txt"
  echo "Processing $FILE"
  COUNT=$(wc -l < "$FILE")
  echo $COUNT

## 15. The find Command

### 15.1 Options

1. **-name**: Search by name.
2. **-type**: Search by type.
3. **-mtime**: Search by modification time.

### 15.2 Examples

* find /home/user -name "file.txt"
* find /home/user -type f -name "*.txt"
* find /var/log -type f -mtime -7
