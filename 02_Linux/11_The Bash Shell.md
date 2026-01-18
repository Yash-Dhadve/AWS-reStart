# The Bash Shell

## Module Objectives

After completing this module, you should be able to:

- Understand the Bash Shell.
- Work with shell variables.
- Display variable values.
- Understand environment variables.
- Use built-in environment variables.
- Create and manage aliases.

---

# Introduction to Bash

## What is Bash?

**Bash** stands for:

```text
Bourne Again Shell
```

It is the default shell in most Linux distributions.

---

## What is a Shell?

A shell is a command interpreter that:

- Accepts user commands
- Interprets commands
- Executes commands
- Provides access to the operating system

---

# Linux Architecture

```text
User
  │
  ▼
Bash Shell
  │
  ▼
Linux Kernel
  │
  ▼
Hardware
```

---

# Features of Bash

## Command Execution

Example:

```bash
ls
pwd
mkdir test
```

---

## Scripting Support

Example:

```bash
#!/bin/bash

echo "Hello Linux"
```

---

## Variables

Store and reuse values.

Example:

```bash
name=Yash
```

---

## Aliases

Create shortcuts for commands.

Example:

```bash
alias ll='ls -l'
```

---

## Environment Variables

Store system-wide settings.

Examples:

```bash
PATH
HOME
USER
```

---

# Variables in Bash

## What is a Variable?

A variable stores data that can be reused later.

---

## Why Use Variables?

Instead of writing:

```bash
/home/yash/Documents
```

multiple times, store it in:

```bash
DOCS=/home/yash/Documents
```

and reuse it.

---

# Variable Syntax

## Assigning a Variable

```bash
variable=value
```

---

## Example

```bash
name=Yash
```

---

## Important Rule

❌ Incorrect

```bash
name = Yash
```

---

✅ Correct

```bash
name=Yash
```

No spaces around `=`.

---

# Variable Examples

## Text Value

```bash
name=Yash
```

---

## Number Value

```bash
age=25
```

---

## File Name

```bash
file=report.txt
```

---

## Path

```bash
dir=/home/yash
```

---

# Variables are Strings

By default, Bash treats variables as:

```text
Strings
```

Even if they contain numbers.

---

## Example

```bash
age=25
```

Still treated as text.

---

# Displaying Variables

## Syntax

```bash
echo $variable
```

---

## Example

```bash
name=Yash

echo $name
```

Output:

```text
Yash
```

---

# Another Example

```bash
city=Pune

echo $city
```

Output:

```text
Pune
```

---

# Viewing All Variables

## Command

```bash
set
```

Displays:

```text
Shell Variables
Functions
Environment Variables
```

---

# Environment Variables

## Definition

Environment variables are variables available system-wide.

They are inherited by:

- Child processes
- Subshells
- Applications

---

# Environment Variable Structure

Same syntax as normal variables:

```bash
KEY=VALUE
```

Example:

```bash
HOME=/home/yash
```

---

# Shell Variable vs Environment Variable

| Feature | Shell Variable | Environment Variable |
|----------|---------------|---------------------|
| Scope | Current Shell | System-wide |
| Available to Child Processes | No | Yes |
| Common Usage | Temporary Data | System Configuration |

---

# Creating a Shell Variable

```bash
name=Yash
```

---

# Creating an Environment Variable

Use:

```bash
export
```

---

## Example

```bash
export name=Yash
```

Now child processes can access it.

---

# Display Environment Variables

## Command

```bash
env
```

or

```bash
printenv
```

---

# Common Environment Variables

---

# $HOME

## Purpose

Stores the user's home directory.

### Example

```bash
echo $HOME
```

Output:

```text
/home/yash
```

---

# $PATH

## Purpose

Stores directories searched for commands.

### Example

```bash
echo $PATH
```

Output:

```text
/usr/local/bin:
/usr/bin:
/bin
```

---

# Why is PATH Important?

When you type:

```bash
ls
```

Linux searches directories listed in:

```bash
$PATH
```

to find the command.

---

# $USER

## Purpose

Displays current username.

### Example

```bash
echo $USER
```

Output:

```text
yash
```

---

# $PWD

## Purpose

Current working directory.

### Example

```bash
echo $PWD
```

Output:

```text
/home/yash/Documents
```

---

# $SHELL

## Purpose

Displays current shell.

### Example

```bash
echo $SHELL
```

Output:

```text
/bin/bash
```

---

# Alias Command

## What is an Alias?

An alias creates a shortcut for a command.

---

## Why Use Aliases?

Instead of typing:

```bash
ls -alh
```

every time, create:

```bash
ll
```

---

# Alias Syntax

```bash
alias shortcut='command'
```

---

## Example

```bash
alias ll='ls -l'
```

Now:

```bash
ll
```

executes:

```bash
ls -l
```

---

# More Alias Examples

## Detailed File Listing

```bash
alias la='ls -la'
```

---

## Clear Screen

```bash
alias c='clear'
```

---

## Update System

```bash
alias update='sudo yum update'
```

---

# View Aliases

## Command

```bash
alias
```

Displays all aliases.

---

# Remove Alias

## Syntax

```bash
unalias alias_name
```

---

## Example

```bash
unalias ll
```

Removes:

```bash
ll
```

---

# Practical Examples

## Variable Example

```bash
name=Yash

echo $name
```

Output:

```text
Yash
```

---

## Environment Variable Example

```bash
echo $HOME
```

Output:

```text
/home/yash
```

---

## Alias Example

```bash
alias ll='ls -l'

ll
```

Equivalent to:

```bash
ls -l
```

---

# Useful Commands Summary

| Command | Purpose |
|----------|----------|
| echo $VAR | Display variable |
| set | Show shell variables |
| env | Show environment variables |
| printenv | Show environment variables |
| export | Create environment variable |
| alias | Create shortcut |
| unalias | Remove shortcut |

---

# Quick Comparison

| Feature | Variable | Environment Variable |
|----------|-----------|----------------------|
| Stores Data | Yes | Yes |
| Current Shell Only | Yes | No |
| Child Processes Access | No | Yes |
| Example | name=Yash | HOME=/home/yash |

---

# Key Takeaways

## Bash

```text
Bourne Again Shell
```

Default Linux shell.

---

## Variables

Store reusable values.

Example:

```bash
name=Yash
```

---

## Display Variables

```bash
echo $name
```

---

## Environment Variables

System-wide variables.

Examples:

```bash
$PATH
$HOME
$USER
```

---

## Aliases

Shortcuts for commands.

Example:

```bash
alias ll='ls -l'
```

---

# Exam / Interview Questions

### Q1. What does Bash stand for?

**Answer:** Bourne Again Shell.

---

### Q2. What is a shell?

**Answer:** A command interpreter that allows users to interact with Linux.

---

### Q3. How do you assign a variable?

**Answer:**

```bash
name=Yash
```

---

### Q4. How do you display a variable?

**Answer:**

```bash
echo $name
```

---

### Q5. What command displays environment variables?

**Answer:**

```bash
env
```

or

```bash
printenv
```

---

### Q6. What does `$HOME` represent?

**Answer:** User's home directory.

---

### Q7. What does `$PATH` represent?

**Answer:** Directories searched for executable commands.

---

### Q8. What command creates an environment variable?

**Answer:**

```bash
export
```

---

### Q9. What is an alias?

**Answer:** A shortcut for a longer command.

---

### Q10. How do you remove an alias?

**Answer:**

```bash
unalias alias_name
```

---

# Memory Tricks

## Important Variables

Remember:

### H-P-U-S

```text
H → HOME
P → PATH
U → USER
S → SHELL
```

---

## Variable Syntax

```bash
name=value
```

Remember:

```text
NO spaces around =
```

---

## Alias

```text
Alias = Command Shortcut
```

---

# One-Line Exam Revision

**Bash (Bourne Again Shell) is the default Linux shell that supports variables, environment variables such as `$HOME` and `$PATH`, and aliases that allow users to create shortcuts for frequently used commands.**

🚀