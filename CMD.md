---

# The Ultimate CMD Command Reference CMD-Cheatsheet

A curated list of the most common and useful commands for the Windows Command Prompt (`cmd.exe`). This guide is intended for beginners and experienced users who need a quick reference.

![Windows Terminal](https://img.shields.io/badge/Platform-Windows-0078D6?style=for-the-badge&logo=windows)
![License](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)

## Table of Contents

1.  [File & Directory Management](#1-file--directory-management)
2.  [System & Information Commands](#2-system--information-commands)
3.  [Networking Commands](#3-networking-commands)
4.  [Text & Output Manipulation](#4-text--output-manipulation)
5.  [Tips & Tricks](#5-tips--tricks)

---

### 1. File & Directory Management

Commands for creating, deleting, and managing files and directories.

| Command | Description | Example Usage |
| :--- | :--- | :--- |
| `dir` | Lists the contents of a directory. | `dir /a` (shows hidden files) |
| `cd` or `chdir` | Changes the current directory. Use `cd..` to go up one level. | `cd C:\Users\YourUser\Documents` |
| `mkdir` or `md` | Creates a new directory. | `md NewFolder` |
| `rmdir` or `rd` | Deletes an empty directory. | `rd OldFolder` |
| `del` or `erase` | Deletes one or more files. | `del report.txt` |
| `copy` | Copies files from one location to another. | `copy source.txt D:\Backup\` |
| `xcopy` | Copies files and directory trees. More powerful than `copy`. | `xcopy C:\Source D:\Destination /E /H` |
| `move` | Moves files or renames directories. | `move oldfile.txt newfile.txt` |
| `ren` or `rename` | Renames a file or directory. | `ren "old name.txt" "new name.txt"` |
| `type` | Displays the contents of a text file. | `type readme.txt` |
| `tree` | Graphically displays the folder structure of a drive or path. | `tree /F` (includes files) |

### 2. System & Information Commands

Commands for managing system processes and retrieving system information.

| Command | Description | Example Usage |
| :--- | :--- | :--- |
| `systeminfo` | Displays detailed configuration information about a computer. | `systeminfo` |
| `tasklist` | Displays a list of currently running processes. | `tasklist` |
| `taskkill` | Terminates a running process by PID or image name. | `taskkill /F /PID 1234` |
| `schtasks` | Schedules commands and programs to run periodically or at a specific time. | `schtasks /create /sc daily /tn "MyTask" /tr "C:\run.bat"` |
| `sfc` | System File Checker. Scans and verifies the integrity of all protected system files. | `sfc /scannow` |
| `chkdsk` | Checks a disk for errors and fixes them. | `chkdsk C: /f` |
| `shutdown` | Shuts down, restarts, or logs off the computer. | `shutdown /r /t 0` (restarts immediately) |
| `cls` | Clears the screen. | `cls` |
| `ver` | Displays the Windows version. | `ver` |
| `whoami` | Displays the current user's username and group information. | `whoami /groups` |
| `driverquery` | Displays a list of installed device drivers. | `driverquery -v` (verbose) |

### 3. Networking Commands

Commands for diagnosing and managing network connections.

| Command | Description | Example Usage |
| :--- | :--- | :--- |
| `ping` | Tests the connection to a specific network host. | `ping google.com` |
| `ipconfig` | Displays all current TCP/IP network configuration values. | `ipconfig /all` |
| `tracert` | Traces the route that a packet takes to a destination. | `tracert google.com` |
| `netstat` | Displays active TCP connections and ports on which the computer is listening. | `netstat -an` |
| `nslookup` | Queries DNS servers to find domain name or IP address mapping. | `nslookup github.com` |
| `getmac` | Displays the MAC address for all network adapters. | `getmac` |

### 4. Text & Output Manipulation

Commands for searching text and redirecting command output.

| Command | Description | Example Usage |
| :--- | :--- | :--- |
| `find` | Searches for a text string in a file. | `type log.txt \| find "Error"` |
| `findstr` | A more powerful search tool (supports regular expressions). | `findstr /i "error" *.log` |
| `sort` | Sorts input and writes results to the screen or a file. | `sort names.txt` |
| `>` | Redirects command output to a file (overwrites). | `dir > file_list.txt` |
| `>>` | Appends command output to a file. | `echo Log entry >> log.txt` |
| `\|` | The "pipe" operator. Sends the output of one command to the input of another. | `tasklist \| find "chrome.exe"` |

### 5. Tips & Tricks

-   **Command History**: Use the `F7` key to see a graphical list of your command history. Use the up/down arrow keys to cycle through previous commands.
-   **Tab Completion**: Start typing a file or directory name and press `Tab` to auto-complete it.
-   **Help**: Use the `/?` switch after any command to get help and see available options (e.g., `dir /?`).
-   **Open CMD in a specific folder**: In File Explorer, type `cmd` in the address bar and press Enter. A Command Prompt window will open in that exact location.

---
