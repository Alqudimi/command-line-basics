---

# The Modern PowerShell Command Reference | PS-Cheatsheet

A comprehensive guide to essential PowerShell cmdlets (pronounced "command-lets"). This cheatsheet is designed for system administrators, developers, and power users transitioning from `CMD` or `bash`, or those who need a quick reference for modern Windows automation.

![PowerShell Core](https://img.shields.io/badge/PowerShell-7+-5391FE?style=for-the-badge&logo=powershell)
![Cross-Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20Linux%20%7C%20macOS-blue?style=for-the-badge)
![License](https.img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)

## Why PowerShell?

PowerShell is not just a shell; it's a powerful automation framework built on the .NET runtime. Unlike traditional shells that pipe text, PowerShell pipes **objects**, allowing for more robust and structured scripting.

## Table of Contents

1.  [File & Directory Management](#1-file--directory-management)
2.  [System & Process Management](#2-system--process-management)
3.  [Networking Cmdlets](#3-networking-cmdlets)
4.  [Object & Text Manipulation](#4-object--text-manipulation)
5.  [Helpful Aliases for Beginners](#5-helpful-aliases-for-beginners)

---

### 1. File & Directory Management

Cmdlets for interacting with the file system. Notice the consistent `Verb-Noun` naming convention.

| Cmdlet | Description | Example Usage |
| :--- | :--- | :--- |
| `Get-ChildItem` | Gets the items (files and folders) in a directory. Alias: `ls`, `gci`, `dir`. | `Get-ChildItem -Path C:\ -Recurse -Filter "*.log"` |
| `Set-Location` | Sets the current working directory. Alias: `cd`, `sl`. | `Set-Location C:\Windows` |
| `Get-Location` | Gets the current working directory. Alias: `pwd`, `gl`. | `Get-Location` |
| `New-Item` | Creates a new item (file or directory). | `New-Item -Path "C:\Temp\NewFile.txt" -ItemType File` |
| `Remove-Item` | Deletes items. Use `-Recurse` for non-empty folders. Alias: `rm`, `del`. | `Remove-Item -Path "C:\Junk" -Recurse -Force` |
| `Copy-Item` | Copies an item from one location to another. Alias: `cp`, `copy`. | `Copy-Item -Path "report.docx" -Destination "D:\Backup"` |
| `Move-Item` | Moves an item from one location to another. Alias: `mv`, `move`. | `Move-Item -Path "C:\Temp\file.txt" -Destination "C:\Archive"` |
| `Rename-Item` | Renames an item. Alias: `ren`. | `Rename-Item -Path "old-name.txt" -NewName "new-name.txt"` |
| `Get-Content` | Gets the content of a file. Alias: `cat`, `gc`, `type`. | `Get-Content -Path "log.txt" -Tail 10` |
| `Set-Content` | Writes or replaces the content of a file. Alias: `sc`. | `"Hello, World!" \| Set-Content -Path "hello.txt"` |
| `Add-Content` | Appends content to a file. Alias: `ac`. | `"New log entry" \| Add-Content -Path "app.log"` |

### 2. System & Process Management

Cmdlets for inspecting and managing the operating system and running processes.

| Cmdlet | Description | Example Usage |
| :--- | :--- | :--- |
| `Get-Process` | Gets the processes that are running on the local computer. Alias: `ps`, `gps`. | `Get-Process -Name "chrome"` |
| `Stop-Process` | Stops one or more running processes. Alias: `kill`, `spps`. | `Stop-Process -Name "notepad" -Force` |
| `Get-Service` | Gets the services on a local or remote computer. | `Get-Service -Name "WinRM"` |
| `Start-Service` | Starts one or more stopped services. | `Start-Service -Name "spooler"` |
| `Stop-Service` | Stops one or more running services. | `Stop-Service -Name "spooler"` |
| `Restart-Computer` | Restarts the operating system on local and remote computers. | `Restart-Computer -Force` |
| `Stop-Computer` | Stops (shuts down) local and remote computers. | `Stop-Computer -Confirm` |
| `Get-WmiObject` / `Get-CimInstance` | Gets instances of WMI/CIM classes (for system info). `Get-CimInstance` is modern. | `Get-CimInstance -ClassName Win32_OperatingSystem` |
| `Get-History` | Gets a list of the commands entered during the current session. Alias: `h`, `history`. | `Get-History` |

### 3. Networking Cmdlets

Cmdlets for network diagnostics and configuration.

| Cmdlet | Description | Example Usage |
| :--- | :--- | :--- |
| `Test-Connection` | Sends ICMP echo request packets ("pings") to one or more computers. Alias: `ping`. | `Test-Connection -ComputerName "google.com" -Count 2` |
| `Get-NetIPAddress` | Gets IP address configuration. | `Get-NetIPAddress -AddressFamily IPv4` |
| `Resolve-DnsName` | Performs a DNS query for the specified name. Alias: `nslookup`. | `Resolve-DnsName -Name "github.com"` |
| `Invoke-WebRequest` | Gets content from a web page on the Internet. Alias: `iwr`, `wget`, `curl`. | `Invoke-WebRequest -Uri "https://api.github.com/users/microsoft"` |
| `Invoke-RestMethod` | Sends an HTTP/HTTPS request and converts the response from JSON/XML. | `Invoke-RestMethod -Uri "https://api.open-meteo.com/v1/forecast?latitude=52.52&longitude=13.41"` |

### 4. Object & Text Manipulation

The core strength of PowerShell: filtering, sorting, and manipulating objects in the pipeline.

| Cmdlet | Description | Example Usage |
| :--- | :--- | :--- |
| `Where-Object` | Filters objects from the pipeline based on a condition. Alias: `where`, `?`. | `Get-Process \| Where-Object { $_.CPU -gt 100 }` |
| `Sort-Object` | Sorts objects by property values. Alias: `sort`. | `Get-Process \| Sort-Object -Property "WorkingSet" -Descending` |
| `Select-Object` | Selects specified properties of an object. Alias: `select`. | `Get-Process \| Select-Object -Property Name, Id, CPU -First 5` |
| `ForEach-Object` | Performs an operation against each object in the pipeline. Alias: `foreach`, `%`. | `Get-Service \| ForEach-Object { $_.DisplayName.ToUpper() }` |
| `Measure-Object` | Calculates numeric properties of objects (count, sum, average, etc.). Alias: `measure`. | `Get-ChildItem \| Measure-Object -Property Length -Sum` |
| `ConvertTo-Json` | Converts an object to a JSON-formatted string. | `Get-Process \| Select-Object Name, Id \| ConvertTo-Json` |
| `ConvertFrom-Json` | Converts a JSON-formatted string to a custom object. | `'{ "user": "test" }' \| ConvertFrom-Json` |

### 5. Helpful Aliases for Beginners

PowerShell includes built-in aliases to make the transition from other shells easier.

| Common Alias | PowerShell Cmdlet | Original Shell |
| :--- | :--- | :--- |
| `ls`, `dir` | `Get-ChildItem` | Linux / CMD |
| `cd`, `chdir` | `Set-Location` | Linux / CMD |
| `pwd` | `Get-Location` | Linux |
| `cat`, `type` | `Get-Content` | Linux / CMD |
| `rm`, `del`, `erase` | `Remove-Item` | Linux / CMD |
| `cp`, `copy` | `Copy-Item` | Linux / CMD |
| `mv`, `move`, `ren` | `Move-Item`, `Rename-Item` | Linux / CMD |
| `ps` | `Get-Process` | Linux |
| `kill` | `Stop-Process` | Linux |
| `clear`, `cls` | `Clear-Host` | Linux / CMD |
| `curl`, `wget` | `Invoke-WebRequest` | Linux |

---
