### 1. File and Directory Management Commands
These are the basic commands you will use frequently to interact with the file system.

| Command | Function | Example Usage |
|---|---|---|
| `ls` | Lists files and directories in the current path. | `ls -l` (to show more details) |
| `cd` | Changes the current directory (navigates between folders). | `cd /home/user/Documents` |
| `pwd` | Prints the working directory (shows your current location). | `pwd` |
| `mkdir` | Creates a new directory. | `mkdir new_folder` |
| `rmdir` | Deletes an empty directory. | `rmdir old_folder` |
| `touch` | Creates a new, empty file. | `touch new_file.txt` |
| `rm` | Deletes files or directories. | `rm file.txt` or `rm -r folder` (to delete a folder and its contents) |
| `cp` | Copies files or directories. | `cp source.txt destination_folder/` |
| `mv` | Moves or renames files or directories. | `mv old_name.txt new_name.txt` |
| `cat` | Displays the contents of a text file on the screen. | `cat file.txt` |
| `find` | Searches for files or directories based on specific criteria. | `find /home -name "*.txt"` |

### 2. System and User Management Commands
These commands are used to get information about the system and manage users and permissions.

| Command | Function | Example Usage |
|---|---|---|
| `sudo` | Executes a command with superuser (root) privileges. | `sudo apt-get update` |
| `whoami` | Displays the current username. | `whoami` |
| `ps` | Shows the currently running processes. | `ps aux` |
| `kill` | Forcibly stops a specific process using its Process ID (PID). | `kill 1234` |
| `top` | Displays live, updated information about processes and system resource usage. | `top` |
| `chmod` | Changes the access permissions of a file or directory. | `chmod 755 script.sh` |
| `chown` | Changes the owner of a file or directory. | `sudo chown user:group file.txt` |
| `history` | Shows a list of recently used commands. | `history` |
| `clear` | Clears the terminal screen. | `clear` |
| `reboot` | Restarts the system. | `sudo reboot` |
| `shutdown` | Shuts down the system. | `sudo shutdown -h now` |

### 3. Networking Commands
These commands help you check and manage your network connection.

| Command | Function | Example Usage |
|---|---|---|
| `ping` | Checks the connection to another device on the network. | `ping google.com` |
| `ifconfig` / `ip addr` | Displays information about network interfaces and IP addresses. | `ip addr show` |
| `wget` / `curl` | Downloads files from the internet via the command line. | `wget https://example.com/file.zip` |
| `ssh` | Connects to another machine remotely and securely. | `ssh user@hostname` |

### 4. Text Processing and Search Commands
Powerful commands for searching within files and processing text.

| Command | Function | Example Usage |
|---|---|---|
| `grep` | Searches for a specific text pattern within a file or another command's output. | `grep "error" logfile.txt` |
| `head` | Displays the first few lines of a file. | `head -n 20 file.txt` |
| `tail` | Displays the last few lines of a file (useful for monitoring log files). | `tail -f /var/log/syslog` |
| `sort` | Sorts the lines of a text file. | `sort names.txt` |

