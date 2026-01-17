# Working with Commands in Linux

## Module Objectives

After completing this module, you should be able to:

- Understand special characters used in Bash.
- Use wildcards effectively.
- Understand input/output redirection.
- Use pipes (`|`) to chain commands.
- Perform text searching using `grep`.
- Manipulate text using `sed`, `sort`, and `awk`.

---

# Introduction

The Bash shell provides powerful tools to:

- Search data
- Manipulate text
- Redirect output
- Chain commands together
- Work efficiently with files and processes

These features are heavily used in:

- Linux Administration
- AWS EC2 Management
- DevOps
- Shell Scripting

---

# Bash Special Characters

## What are Special Characters?

Special characters (metacharacters) have special meanings in Bash.

They control:

- Command execution
- Redirection
- Searching
- Wildcards
- Piping

---

# Quotation Marks

## Purpose

Normally Bash separates words using spaces.

### Example

```bash
mkdir My Folder
```

Bash interprets:

```text
My
Folder
```

as two arguments.

---

## Using Quotes

```bash
mkdir "My Folder"
```

Creates:

```text
My Folder
```

as a single directory.

---

# Types of Quotes

## Double Quotes

```bash
" "
```

Allow variables to expand.

Example:

```bash
name="Yash"
echo "Hello $name"
```

Output:

```text
Hello Yash
```

---

## Single Quotes

```bash
' '
```

Treat everything literally.

Example:

```bash
echo '$HOME'
```

Output:

```text
$HOME
```

---

# Metacharacters

## Definition

Special symbols used to control command behavior.

---

# Common Metacharacters

| Symbol | Purpose |
|----------|----------|
| `|` | Pipe |
| `>` | Redirect output |
| `>>` | Append output |
| `<` | Redirect input |
| `;` | Multiple commands |
| `*` | Wildcard |
| `?` | Single-character wildcard |

---

# Wildcards

## Definition

Wildcards match unknown characters in filenames and searches.

---

# Asterisk (*)

## Purpose

Matches zero or more characters.

### Example

```bash
ls *.txt
```

Matches:

```text
notes.txt
report.txt
file.txt
```

---

# Question Mark (?)

## Purpose

Matches exactly one character.

### Example

```bash
ls file?.txt
```

Matches:

```text
file1.txt
file2.txt
fileA.txt
```

Does NOT match:

```text
file10.txt
```

---

# Character Range []

## Purpose

Match specific characters.

### Example

```bash
ls file[1-5].txt
```

Matches:

```text
file1.txt
file2.txt
file3.txt
file4.txt
file5.txt
```

---

# Standard Input and Output

Linux commands communicate through standard streams.

| Stream | Number | Description |
|----------|---------|-------------|
| stdin | 0 | Standard Input |
| stdout | 1 | Standard Output |
| stderr | 2 | Standard Error |

---

# Standard I/O

## Standard Input

Usually:

```text
Keyboard
```

---

## Standard Output

Usually:

```text
Monitor/Terminal
```

---

## Standard Error

Usually:

```text
Terminal/Error Logs
```

---

# Output Redirection

## Redirect Output (>)

Stores command output in a file.

### Syntax

```bash
command > file
```

---

### Example

```bash
ls > files.txt
```

Output goes to:

```text
files.txt
```

---

# Append Output (>>)

Adds output to an existing file.

### Syntax

```bash
command >> file
```

---

### Example

```bash
date >> logfile.txt
```

---

# Input Redirection (<)

Uses file contents as input.

### Syntax

```bash
command < file
```

---

### Example

```bash
sort < names.txt
```

---

# Redirect Errors

## Syntax

```bash
command 2> error.log
```

---

### Example

```bash
ls missingfile 2> error.log
```

Stores errors in:

```text
error.log
```

---

# Redirect Output and Errors

### Syntax

```bash
command > output.txt 2> error.txt
```

---

# Pipes (|)

## Definition

A pipe sends the output of one command directly to another command.

---

## Syntax

```bash
command1 | command2
```

---

# Example

```bash
ls | grep txt
```

---

## How it Works

```text
ls output
      │
      ▼
grep txt
```

---

## Benefits

- No temporary files required.
- Faster processing.
- Combine multiple commands.

---

# grep Command

## Purpose

Searches for text patterns.

---

## Syntax

```bash
grep pattern file
```

---

## Example

```bash
grep Linux notes.txt
```

---

# grep with Pipe

```bash
ls -l | grep txt
```

Shows only `.txt` files.

---

## Ignore Case

```bash
grep -i linux notes.txt
```

Matches:

```text
Linux
LINUX
linux
```

---

## Show Line Numbers

```bash
grep -n error logfile.txt
```

---

# sort Command

## Purpose

Sorts lines of text.

---

## Syntax

```bash
sort file
```

---

## Example

File:

```text
Orange
Apple
Banana
```

Command:

```bash
sort fruits.txt
```

Output:

```text
Apple
Banana
Orange
```

---

## Reverse Sort

```bash
sort -r fruits.txt
```

---

# sed Command

## Purpose

Stream Editor for searching and replacing text.

---

## Syntax

```bash
sed 's/old/new/' file
```

---

## Example

```bash
sed 's/Linux/AWS/' notes.txt
```

---

### Before

```text
Linux is great.
```

### After

```text
AWS is great.
```

---

## Replace All Occurrences

```bash
sed 's/Linux/AWS/g' notes.txt
```

---

# awk Command

## Purpose

Pattern scanning and text processing tool.

---

## Syntax

```bash
awk '{print $1}' file
```

---

## Example File

```text
John 25
Sarah 30
Mike 35
```

Command:

```bash
awk '{print $1}' users.txt
```

Output:

```text
John
Sarah
Mike
```

---

## Print Specific Column

```bash
awk '{print $2}'
```

Output:

```text
25
30
35
```

---

# Command Chaining

## Semicolon (;)

Runs multiple commands sequentially.

### Example

```bash
pwd ; ls ; date
```

---

# Pipe vs Redirection

| Feature | Pipe (|) | Redirection (>) |
|-----------|----------|---------------|
| Sends Output To | Another Command | File |
| Temporary Storage | No | Yes |
| Common Use | Command Chaining | Save Output |

---

# Real-World Examples

## Search Running Processes

```bash
ps -ef | grep apache
```

---

## Find Error Messages

```bash
cat logfile.txt | grep ERROR
```

---

## Sort Usernames

```bash
sort users.txt
```

---

## Replace Text

```bash
sed 's/http/https/g' config.txt
```

---

## Display First Column

```bash
awk '{print $1}' users.txt
```

---

# Useful Commands Summary

| Command | Purpose |
|----------|----------|
| grep | Search text |
| sort | Sort text |
| sed | Search & replace |
| awk | Process columns |
| | | Pipe output |
| > | Redirect output |
| >> | Append output |
| < | Redirect input |

---

# Key Takeaways

## Quotes

```bash
" "
```

Treat text with spaces as one argument.

---

## Wildcards

```bash
*
?
[]
```

Match unknown characters.

---

## Pipes

```bash
|
```

Send output of one command to another.

---

## Redirection

```bash
>
>>
<
```

Control input and output.

---

## Text Processing Commands

### grep

Search text.

### sort

Sort text.

### sed

Replace text.

### awk

Process columns and patterns.

---

# Exam / Interview Questions

### Q1. What is the purpose of quotation marks in Bash?

**Answer:** To treat text containing spaces as a single argument.

---

### Q2. What does `*` represent?

**Answer:** Zero or more characters.

---

### Q3. What does `?` represent?

**Answer:** Exactly one character.

---

### Q4. What does the pipe (`|`) operator do?

**Answer:** Sends output from one command to another command.

---

### Q5. Which command searches text patterns?

**Answer:**

```bash
grep
```

---

### Q6. Which command sorts text?

**Answer:**

```bash
sort
```

---

### Q7. Which command replaces text?

**Answer:**

```bash
sed
```

---

### Q8. Which command processes columns of text?

**Answer:**

```bash
awk
```

---

### Q9. What does `>` do?

**Answer:** Redirects output to a file.

---

### Q10. What does `>>` do?

**Answer:** Appends output to a file.

---

# Memory Tricks

## Text Processing Tools

Remember:

### G-S-A

```text
G → grep
S → sed
A → awk
```

---

## Redirection

```text
>  = Overwrite
>> = Append
<  = Input
```

---

## Wildcards

```text
* = Many
? = One
```

---

# One-Line Exam Revision

**Bash uses special characters, wildcards, pipes, and redirection to control command execution, while commands such as `grep`, `sort`, `sed`, and `awk` provide powerful text searching and manipulation capabilities.**

🚀