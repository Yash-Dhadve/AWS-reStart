# Introduction to Linux

## Module Objectives

After completing this module, you should be able to:

- Understand what Linux is.
- Explain the role of the Linux Kernel.
- Understand applications and shells in Linux.
- Identify different shell types.
- Use the `man` command for help and documentation.
- Understand Linux distributions.

---

# What is Linux?

## Definition

Linux is a free and open-source operating system that is similar to Unix.

### Features

- Free to use
- Open source
- Secure
- Stable
- Multiuser
- Multitasking
- Highly customizable

---

# Linux Architecture

```text
+-----------------------+
|      Applications     |
+-----------------------+
|         Shell         |
+-----------------------+
|        Kernel         |
+-----------------------+
|       Hardware        |
+-----------------------+
```

### Components

1. Applications
2. Shell
3. Kernel
4. Hardware

---

# Linux Kernel

## Definition

The kernel is the core component of the Linux operating system.

It acts as a bridge between:

- Software
- Hardware

---

# Functions of the Linux Kernel

The Linux Kernel manages:

### 1. Processes

Controls execution of running programs.

Example:

```bash
firefox
chrome
python
```

---

### 2. Memory Management

Allocates and manages RAM.

Responsibilities:

- Memory allocation
- Memory release
- Virtual memory

---

### 3. File System Access

Manages:

- Files
- Directories
- Storage devices

---

### 4. Device Management

Controls I/O devices such as:

- Keyboard
- Mouse
- Printer
- USB devices
- Hard disks

---

### 5. Resource Allocation

Distributes system resources among users and applications.

Resources include:

- CPU
- Memory
- Storage
- Network

---

# Kernel Management Overview

```text
Kernel
│
├── Processes
├── Memory
├── Devices
├── File System
└── Resource Allocation
```

---

# Applications

## Definition

Applications are software programs that help users perform specific tasks.

---

## Examples of Applications

### Word Processor

Example:

```text
LibreOffice Writer
Microsoft Word
```

---

### Web Browser

Example:

```text
Firefox
Chrome
```

---

### Email Client

Example:

```text
Thunderbird
Outlook
```

---

### Media Player

Example:

```text
VLC Media Player
```

---

# Linux User Interfaces

Linux provides two ways to interact with the system.

---

## 1. CLI (Command Line Interface)

Users interact through commands.

Example:

```bash
ls
pwd
mkdir
```

### Advantages

- Fast
- Powerful
- Resource efficient

---

## 2. GUI (Graphical User Interface)

Users interact through:

- Windows
- Icons
- Menus
- Buttons

Examples:

```text
Ubuntu Desktop
Linux Mint
Fedora Workstation
```

---

# What is a Shell?

## Definition

A Shell is a command interpreter that allows users to interact with the Linux operating system.

The shell:

- Accepts commands
- Interprets commands
- Executes commands

---

# Functions of a Shell

### Provides Command Prompt

Example:

```bash
$
```

or

```bash
#
```

---

### Executes Commands

Example:

```bash
ls
```

---

### Runs Scripts

Example:

```bash
bash backup.sh
```

---

# Shell Types

Different Linux/Unix systems support multiple shell types.

---

## 1. sh

### Name

Bourne Shell

### Description

Original Unix shell.

Example:

```bash
sh script.sh
```

---

## 2. bash

### Name

Bourne Again Shell

### Description

Default shell in most Linux distributions.

### Features

- Command history
- Auto-completion
- Scripting support

Example:

```bash
bash script.sh
```

---

## 3. ksh

### Name

Korn Shell

### Description

Common shell in Unix systems.

Example:

```bash
ksh script.sh
```

---

# Default Linux Shell

## Bash Shell

### Important Point

Bash is the default shell for most Linux distributions.

### Why Learn Bash?

- Most commonly used
- Powerful scripting features
- Industry standard

---

# Linux Commands Help System

## man Command

### Definition

The `man` command displays Linux manual pages.

### Syntax

```bash
man <command>
```

### Example

```bash
man ls
```

Displays documentation for the `ls` command.

---

# Benefits of man Command

### Learn Command Syntax

Example:

```bash
man cp
```

---

### View Available Options

Example:

```bash
man grep
```

---

### Understand Command Usage

Example:

```bash
man mkdir
```

---

# Navigation Inside man Pages

## Scroll One Line

### Up Arrow

Move up one line.

### Down Arrow

Move down one line.

---

## Scroll One Page

### Page Up

Move up one page.

### Page Down

Move down one page.

---

## Space Bar

Move down one page.

---

# Search Within man Pages

### Syntax

```bash
/searchString
```

### Example

```bash
/option
```

Searches for the word "option".

---

# Exit man Pages

### Command

```bash
q
```

Press:

```text
q
```

to quit manual pages.

---

# Linux Distribution

## Definition

A Linux Distribution (Distro) is a packaged version of Linux developed by a company or community.

It combines:

- Linux Kernel
- System Tools
- Applications
- Package Manager

to provide a complete operating system.

---

# Distribution Structure

```text
Linux Distribution
│
├── Linux Kernel
├── Shell
├── System Utilities
├── Applications
└── Package Manager
```

---

# Examples of Linux Distributions

## Ubuntu

Beginner-friendly Linux distribution.

---

## Debian

Stable and reliable distribution.

---

## Fedora

Latest Linux technologies.

---

## Red Hat Enterprise Linux (RHEL)

Enterprise Linux distribution.

---

## CentOS Stream

Community-supported enterprise Linux.

---

## Linux Mint

User-friendly desktop Linux.

---

# Linux Distribution Benefits

### Ready to Use

Includes essential software.

---

### Easy Installation

User-friendly installation process.

---

### Software Management

Package managers simplify installation.

---

### Security Updates

Regular updates and patches.

---

# Checkpoint Questions

## Q1. What is a Linux Distribution?

### Answer

A packaged version of Linux that combines:

- Linux Kernel
- Applications
- Tools

to provide a complete operating system.

---

## Q2. True or False

### Bash is the default shell for most Linux distributions.

**Answer:** True

---

## Q3. Which command provides help for Linux commands?

**Answer:**

```bash
man
```

---

# Quick Comparison

| Component | Purpose |
|------------|---------|
| Kernel | Core of Linux |
| Shell | Command interpreter |
| Application | User software |
| CLI | Command-based interface |
| GUI | Graphical interface |
| Distribution | Complete Linux package |
| man | Command documentation |

---

# Key Takeaways

## Linux

- Free and open-source operating system.
- Similar to Unix.
- Highly customizable.

---

## Linux Kernel

Manages:

- Processes
- Memory
- Devices
- File systems
- Resource allocation

---

## Linux Distribution

Combines:

- Kernel
- Applications
- Tools

to create a complete operating system.

---

## Shell

- Interface between user and Linux.
- Executes commands.

---

## Bash

- Default Linux shell.
- Most important shell to learn.

---

## man Command

Used to:

- Learn command syntax
- View options
- Read documentation

---

# Exam / Interview Questions

### Q1. What is Linux?

**Answer:** A free and open-source operating system similar to Unix.

---

### Q2. What is the Linux Kernel?

**Answer:** The core component of Linux that manages hardware and system resources.

---

### Q3. What are the main functions of the Kernel?

**Answer:**

- Process Management
- Memory Management
- Device Management
- File System Management
- Resource Allocation

---

### Q4. What is a Shell?

**Answer:** A command interpreter that allows users to interact with Linux.

---

### Q5. Which shell is the default Linux shell?

**Answer:** Bash Shell.

---

### Q6. What does Bash stand for?

**Answer:** Bourne Again Shell.

---

### Q7. What is a Linux Distribution?

**Answer:** A complete operating system package built around the Linux Kernel.

---

### Q8. Name three Linux distributions.

**Answer:**

- Ubuntu
- Debian
- Red Hat Enterprise Linux (RHEL)

---

### Q9. What is the purpose of the `man` command?

**Answer:** To display documentation and help pages for Linux commands.

---

### Q10. How do you exit a man page?

**Answer:**

```bash
q
```

---

# Memory Trick

## Kernel Responsibilities

Remember:

### PMDFR

```text
P → Processes
M → Memory
D → Devices
F → File System
R → Resource Allocation
```

---

## Linux Architecture

Remember:

### A-S-K-H

```text
Applications
Shell
Kernel
Hardware
```

---

# One-Line Exam Revision

**Linux is a free, open-source Unix-like operating system where the Kernel manages system resources, the Bash Shell provides command-line interaction, and Linux distributions combine the Kernel with tools and applications to form a complete operating system.**

🚀