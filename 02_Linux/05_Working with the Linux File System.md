# Working with the Linux File System

## Module Objectives

After completing this module, you should be able to:

- Understand the Linux file system.
- Navigate files and directories.
- Create, copy, move, and delete files.
- Create and remove directories.
- Understand absolute and relative paths.
- Use common Linux file management commands.

---

# Introduction to the Linux File System

## What is a File System?

A file system is a method of:

- Naming data
- Organizing data
- Storing data
- Retrieving data

from a storage device.

---

## File System Structure

```text
Hard Disk
    │
    ▼
File System
    │
    ├── Directories
    │      │
    │      ├── Files
    │      ├── Files
    │      └── Files
    │
    └── More Directories
```

---

# Everything in Linux is a File

One of the most important Linux concepts is:

> Everything in Linux is treated as a file.

Examples:

```text
Text files
Directories
Devices
Programs
Configuration files
```

---

# Files and Directories

## File

A file stores information.

Examples:

```text
notes.txt
script.sh
photo.jpg
```

---

## Directory

A directory is a special type of file used to organize other files.

Examples:

```text
Documents
Downloads
Projects
```

---

# Linux File System Characteristics

## Case Sensitive

Linux treats uppercase and lowercase letters differently.

### Example

```text
file.txt
File.txt
FILE.txt
```

These are three different files.

---

# Important Linux Directories

## Root Directory

Represented by:

```text
/
```

The top-level directory of Linux.

---

# Common Linux Directories

## /

Root directory.

---

## /home

Stores user home directories.

### Example

```text
/home/yash
/home/student
```

---

## /mnt

Used for mounting storage devices.

### Example

```text
/mnt/usb
```

---

## /etc

Stores system configuration files.

---

## /bin

Contains essential commands and programs.

---

## /var

Stores logs and variable data.

---

## /tmp

Stores temporary files.

---

# Linux Directory Structure

```text
/
├── bin
├── etc
├── home
│   ├── yash
│   └── student
├── mnt
├── tmp
└── var
```

---

# Viewing Files and Directories

# 1. ls Command

## Purpose

Lists files and directories.

### Syntax

```bash
ls
```

---

### Example

```bash
$ ls
Documents
notes.txt
Downloads
```

---

# Long Listing Format

### Syntax

```bash
ls -l
```

### Example

```bash
$ ls -l
-rw-r--r-- notes.txt
drwxr-xr-x Documents
```

---

# Understanding Output

### File

```text
-rw-r--r--
```

Starts with:

```text
-
```

---

### Directory

```text
drwxr-xr-x
```

Starts with:

```text
d
```

---

# Viewing File Contents

# 2. cat Command

## Purpose

Displays file contents.

### Syntax

```bash
cat filename
```

### Example

```bash
cat notes.txt
```

Output:

```text
Linux is awesome.
```

---

# Creating Files

# 3. touch Command

## Purpose

Creates an empty file.

### Syntax

```bash
touch filename
```

### Example

```bash
touch notes.txt
```

---

# Copying Files

# 4. cp Command

## Purpose

Copies files.

### Syntax

```bash
cp source destination
```

### Example

```bash
cp notes.txt backup.txt
```

---

# Copy Directory

```bash
cp -r project backup_project
```

---

# Moving Files

# 5. mv Command

## Purpose

Moves or renames files.

### Syntax

```bash
mv source destination
```

---

### Move File

```bash
mv notes.txt Documents/
```

---

### Rename File

```bash
mv notes.txt linux_notes.txt
```

---

# Deleting Files

# 6. rm Command

## Purpose

Deletes files.

### Syntax

```bash
rm filename
```

### Example

```bash
rm notes.txt
```

---

# Warning

Deleted files are usually not recoverable.

---

# Creating Directories

# 7. mkdir Command

## Purpose

Creates directories.

### Syntax

```bash
mkdir directory_name
```

### Example

```bash
mkdir Projects
```

---

# Create Multiple Directories

```bash
mkdir dir1 dir2 dir3
```

---

# Deleting Directories

# 8. rmdir Command

## Purpose

Removes empty directories.

### Syntax

```bash
rmdir directory_name
```

### Example

```bash
rmdir Projects
```

---

# Remove Non-Empty Directory

```bash
rm -r directory_name
```

Example:

```bash
rm -r Projects
```

---

# Navigating Directories

# 9. pwd Command

## Purpose

Displays current directory.

### Syntax

```bash
pwd
```

### Example

```bash
$ pwd
/home/yash
```

---

# 10. cd Command

## Purpose

Changes current directory.

### Syntax

```bash
cd directory
```

### Example

```bash
cd Documents
```

---

# Go to Home Directory

```bash
cd ~
```

---

# Go Up One Directory

```bash
cd ..
```

---

# Current Directory

```bash
.
```

---

# Parent Directory

```bash
..
```

---

# File Management Workflow

## Create File

```bash
touch file1.txt
```

---

## View File

```bash
cat file1.txt
```

---

## Copy File

```bash
cp file1.txt backup.txt
```

---

## Rename File

```bash
mv file1.txt notes.txt
```

---

## Delete File

```bash
rm notes.txt
```

---

# Absolute Paths

## Definition

An absolute path starts from the root directory (`/`).

---

## Example

```text
/home/yash/Documents/file.txt
```

---

## Characteristics

- Starts with `/`
- Complete path
- Works from anywhere

---

# Relative Paths

## Definition

A relative path starts from the current working directory.

---

## Example

Current directory:

```text
/home/yash
```

File:

```text
Documents/file.txt
```

---

## Characteristics

- Does not start with `/`
- Depends on current location

---

# Absolute vs Relative Path

## Example

File location:

```text
/home/yash/Documents/report.txt
```

---

### Absolute Path

```text
/home/yash/Documents/report.txt
```

---

### Relative Path

```text
Documents/report.txt
```

(when current directory is `/home/yash`)

---

# Path Comparison

| Type | Example |
|---------|----------|
| Absolute Path | /home/yash/file.txt |
| Relative Path | file.txt |
| Current Directory | . |
| Parent Directory | .. |

---

# Useful Commands Summary

| Command | Purpose |
|----------|----------|
| pwd | Show current directory |
| ls | List files |
| ls -l | Detailed listing |
| cat | Display file contents |
| touch | Create file |
| cp | Copy file |
| mv | Move/Rename file |
| rm | Delete file |
| mkdir | Create directory |
| rmdir | Remove empty directory |
| cd | Change directory |

---

# Quick Comparison

| Object | Description |
|-----------|------------|
| File | Stores data |
| Directory | Stores files and directories |
| Absolute Path | Starts from root |
| Relative Path | Starts from current location |

---

# Key Takeaways

## Linux File System

- Organizes files and directories.
- Everything in Linux is treated as a file.

---

## Important Directories

```text
/
/home
/mnt
/etc
/var
/tmp
```

---

## Linux is Case Sensitive

```text
file.txt ≠ File.txt
```

---

## Common File Commands

```bash
ls
cat
cp
mv
rm
mkdir
```

---

## Paths

### Absolute

```text
/home/yash/file.txt
```

### Relative

```text
file.txt
```

---

# Exam / Interview Questions

### Q1. What is a Linux file system?

**Answer:** A method of organizing, storing, and retrieving data on storage devices.

---

### Q2. What does "Everything in Linux is a file" mean?

**Answer:** Linux treats files, directories, devices, and many system resources as files.

---

### Q3. Which command lists files and directories?

**Answer:**

```bash
ls
```

---

### Q4. Which command displays file contents?

**Answer:**

```bash
cat
```

---

### Q5. Which command copies files?

**Answer:**

```bash
cp
```

---

### Q6. Which command moves or renames files?

**Answer:**

```bash
mv
```

---

### Q7. Which command removes files?

**Answer:**

```bash
rm
```

---

### Q8. Which command creates directories?

**Answer:**

```bash
mkdir
```

---

### Q9. What is an absolute path?

**Answer:** A path that starts from the root directory (`/`).

---

### Q10. What is a relative path?

**Answer:** A path that starts from the current directory.

---

# Memory Tricks

## File Commands

Remember:

### T-C-M-R

```text
T → touch
C → cp
M → mv
R → rm
```

---

## Directory Commands

Remember:

### M-C-P

```text
M → mkdir
C → cd
P → pwd
```

---

## Path Types

Remember:

### A-R

```text
A → Absolute (starts with /)
R → Relative (current location)
```

---

# One-Line Exam Revision

**The Linux file system organizes data into files and directories, provides commands such as `ls`, `cat`, `cp`, `mv`, `rm`, and `mkdir` for file management, and supports both absolute and relative paths for navigation.**

🚀
