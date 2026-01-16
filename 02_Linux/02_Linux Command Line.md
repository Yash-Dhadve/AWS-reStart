# Linux Command Line

## Module Objectives

After completing this module, you should be able to:

- Describe the Linux login workflow.
- Understand the Linux command prompt.
- Explain Linux command syntax.
- Perform basic command-line operations.
- Understand standard input, output, and error streams.
- Use common Linux commands.

---

# Introduction to Linux Command Line

## What is the Command Line?

The Linux Command Line Interface (CLI) is a text-based interface used to interact with the Linux operating system.

Instead of clicking icons, users enter commands.

### Example

```bash
ls
pwd
mkdir myfolder
```

---

# Linux Login Workflow

When a user logs into Linux, three main steps occur.

## Step 1: Authentication

The user provides:

- Username
- Password

### Example

```text
Username: yash
Password: ********
```

---

## Step 2: Load User Profile

Linux loads user-specific settings from profile files.

Examples:

```bash
~/.bash_profile
~/.profile
~/.bashrc
```

These files configure:

- Environment variables
- Aliases
- Shell settings

---

## Step 3: Display Command Prompt

After authentication and profile loading:

- User enters the shell.
- Command prompt appears.
- Current location is usually the user's home directory.

### Example

```bash
[yash@hostname ~]$
```

---

# Linux Login Workflow Diagram

```text
User Login
    │
    ▼
Authentication
(Username + Password)
    │
    ▼
Load Profile Files
(.bashrc, .profile)
    │
    ▼
Display Command Prompt
(Home Directory)
```

---

# Linux Command Prompt

## Definition

A command prompt is where users enter Linux commands.

### Example

```bash
[user@hostname ~]$
```

---

## Prompt Components

### Username

```text
user
```

---

### Hostname

```text
hostname
```

---

### Current Directory

```text
~
```

(~ represents the home directory)

---

### Prompt Symbol

Regular User:

```bash
$
```

Root User:

```bash
#
```

---

# Linux Command Syntax

Most Linux commands follow a common format.

## Syntax

```bash
command [options] [arguments]
```

---

## Components

### Command

The action to perform.

Example:

```bash
ls
```

---

### Option

Modifies command behavior.

Example:

```bash
ls -l
```

`-l` = Long listing format

---

### Argument

Target object for the command.

Example:

```bash
ls /home
```

`/home` is the argument.

---

# Example Commands

## List Files

```bash
ls
```

---

## Long Listing

```bash
ls -l
```

---

## List Specific Directory

```bash
ls /home
```

---

## Combined Example

```bash
ls -la /home
```

Where:

```text
ls      = command
-la     = options
/home   = argument
```

---

# Command Auto Completion

## Tab Key

Linux provides automatic command completion.

### Example

Type:

```bash
his
```

Press:

```text
TAB
```

Linux completes:

```bash
history
```

---

# Benefits of Tab Completion

- Faster typing
- Fewer mistakes
- Easier command discovery

---

# Useful Linux Commands

---

# 1. history

## Purpose

Displays previously executed commands.

### Syntax

```bash
history
```

### Example Output

```text
1 ls
2 pwd
3 mkdir test
4 history
```

---

# 2. whoami

## Purpose

Displays current logged-in user.

### Syntax

```bash
whoami
```

### Example

```bash
$ whoami
yash
```

---

# 3. hostname

## Purpose

Displays system hostname.

### Syntax

```bash
hostname
```

### Example

```bash
$ hostname
server01
```

---

# 4. id

## Purpose

Displays user and group information.

### Syntax

```bash
id
```

### Example

```bash
$ id
uid=1000(yash)
gid=1000(yash)
groups=1000(yash)
```

---

# Information Displayed by id Command

### User ID (UID)

```text
uid=1000
```

Unique user identifier.

---

### Group ID (GID)

```text
gid=1000
```

Primary group identifier.

---

### Group Memberships

```text
groups=1000
```

Lists groups the user belongs to.

---

# Standard Streams

Linux uses standard communication channels called streams.

---

# What are Standard Streams?

Streams transfer data between:

- User
- Commands
- Applications
- Devices

---

# Three Standard Streams

| Stream | Number | Description |
|----------|---------|-------------|
| stdin | 0 | Standard Input |
| stdout | 1 | Standard Output |
| stderr | 2 | Standard Error |

---

# 1. Standard Input (stdin)

## Stream Number

```text
0
```

---

## Purpose

Receives input from:

- Keyboard
- File
- Another command

---

### Example

```bash
cat
```

User types text through keyboard.

---

# 2. Standard Output (stdout)

## Stream Number

```text
1
```

---

## Purpose

Displays normal command output.

### Example

```bash
echo "Hello"
```

Output:

```text
Hello
```

---

# 3. Standard Error (stderr)

## Stream Number

```text
2
```

---

## Purpose

Displays error messages.

### Example

```bash
ls unknownfile
```

Output:

```text
ls: cannot access 'unknownfile'
```

---

# Standard Streams Diagram

```text
Keyboard
    │
    ▼
 stdin (0)
    │
    ▼
 Command
    │
 ┌──┴──┐
 ▼     ▼
stdout stderr
  (1)   (2)
```

---

# Input/Output Redirection Basics

## Redirect Output

```bash
ls > files.txt
```

Stores output in a file.

---

## Redirect Errors

```bash
ls missingfile 2> error.log
```

Stores errors in a file.

---

## Redirect Both

```bash
command > output.txt 2> error.txt
```

---

# User Home Directory

## Definition

Each user has a personal home directory.

### Examples

```text
/home/yash
/home/ec2-user
/home/student
```

---

## Shortcut

```bash
~
```

Represents the home directory.

### Example

```bash
cd ~
```

---

# Quick Comparison

| Command | Purpose |
|----------|----------|
| history | Show command history |
| whoami | Show current user |
| hostname | Show system hostname |
| id | Show user and group IDs |
| man | Show command documentation |

---

# Key Takeaways

## Linux Login Workflow

1. Authentication
2. Load Profile Files
3. Display Command Prompt

---

## Command Syntax

```bash
command [options] [arguments]
```

---

## Tab Completion

- Press `Tab`
- Automatically completes commands

---

## Useful Commands

```bash
history
whoami
hostname
id
```

---

## Standard Streams

```text
stdin  = 0
stdout = 1
stderr = 2
```

---

## User Home Directory

Represented by:

```bash
~
```

---

# Exam / Interview Questions

### Q1. What are the three steps in the Linux login workflow?

**Answer:**

1. Authentication
2. Load profile files
3. Display command prompt

---

### Q2. What is the Linux command syntax?

**Answer:**

```bash
command [options] [arguments]
```

---

### Q3. What command displays the current user?

**Answer:**

```bash
whoami
```

---

### Q4. What command displays the hostname?

**Answer:**

```bash
hostname
```

---

### Q5. What command displays user and group IDs?

**Answer:**

```bash
id
```

---

### Q6. What does the Tab key do?

**Answer:** Automatically completes commands and filenames.

---

### Q7. What is stdin?

**Answer:** Standard Input stream (0).

---

### Q8. What is stdout?

**Answer:** Standard Output stream (1).

---

### Q9. What is stderr?

**Answer:** Standard Error stream (2).

---

### Q10. What symbol represents the user's home directory?

**Answer:**

```bash
~
```

---

# Memory Trick

## Linux Login Workflow

Remember:

### A-P-C

```text
A → Authenticate
P → Profile Loaded
C → Command Prompt
```

---

## Standard Streams

Remember:

### I-O-E

```text
0 → Input (stdin)
1 → Output (stdout)
2 → Error (stderr)
```

---

## Useful User Commands

Remember:

### WHIH

```text
W → whoami
H → hostname
I → id
H → history
```

---

# One-Line Exam Revision

**The Linux login workflow consists of authentication, loading user profile files, and displaying a command prompt, while standard streams (stdin, stdout, stderr) manage input, output, and error communication for Linux commands.**

🚀