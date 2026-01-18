# Bash Shell Scripts

## Module Objectives

After completing this module, you should be able to:

- Understand Bash shell scripts.
- Create and execute shell scripts.
- Use variables and arguments.
- Implement conditional statements.
- Use loops in scripts.
- Control loops using `break` and `continue`.
- Automate Linux administration tasks.

---

# Introduction to Shell Scripts

## What is a Script?

A script is a file containing a sequence of commands that are executed automatically.

Instead of typing multiple commands manually:

```bash
date
pwd
ls
```

You can place them in a file and execute them together.

---

# Why Use Shell Scripts?

Shell scripts help:

- Automate repetitive tasks
- Save time
- Reduce errors
- Improve productivity
- Manage Linux systems efficiently

---

# Common Uses of Shell Scripts

## System Administration

```bash
Backup files
```

---

## Monitoring

```bash
CPU monitoring
Disk monitoring
```

---

## Automation

```bash
User creation
Log cleanup
```

---

## Scheduling

```bash
Cron jobs
```

---

# Basic Structure of a Bash Script

## Example

```bash
#!/bin/bash

echo "Hello Linux"
```

---

# Shebang Line

## Syntax

```bash
#!/bin/bash
```

---

## Purpose

Tells Linux:

```text
Run this script using Bash
```

---

# Script Anatomy

```bash
#!/bin/bash

# Comment

echo "Hello World"
```

---

# Comments

## Single Line Comment

```bash
# This is a comment
```

---

## Purpose

Used for:

- Documentation
- Explanation
- Readability

---

# Creating a Script

## Step 1

Create file:

```bash
vim hello.sh
```

---

## Step 2

Add content:

```bash
#!/bin/bash

echo "Hello World"
```

---

## Step 3

Save file.

---

## Step 4

Give execute permission:

```bash
chmod +x hello.sh
```

---

## Step 5

Run script:

```bash
./hello.sh
```

Output:

```text
Hello World
```

---

# Variables in Scripts

## Definition

Variables store values.

---

## Example

```bash
#!/bin/bash

name=Yash

echo $name
```

Output:

```text
Yash
```

---

# User Input

## read Command

Allows user input.

---

### Example

```bash
#!/bin/bash

echo "Enter your name:"
read name

echo "Hello $name"
```

---

# Command-Line Arguments

## What are Arguments?

Arguments are values passed when executing a script.

---

## Example

```bash
./script.sh 10 20
```

Here:

```text
10 = First Argument
20 = Second Argument
```

---

# Positional Parameters

| Parameter | Meaning |
|------------|----------|
| $0 | Script Name |
| $1 | First Argument |
| $2 | Second Argument |
| $3 | Third Argument |
| $# | Number of Arguments |
| $* | All Arguments |

---

# Example: Addition Script

```bash
#!/bin/bash

sum=$(($1+$2))

echo $sum
```

---

## Execution

```bash
./add.sh 3 8
```

Output:

```text
11
```

---

# Explanation

```text
$1 = 3
$2 = 8

sum = 11
```

---

# Conditional Statements

## Purpose

Allow scripts to make decisions.

---

# if Statement

## Syntax

```bash
if [ condition ]
then
    commands
fi
```

---

# Example

```bash
#!/bin/bash

num=10

if [ $num -gt 5 ]
then
    echo "Greater"
fi
```

Output:

```text
Greater
```

---

# Comparison Operators

| Operator | Meaning |
|-----------|----------|
| -eq | Equal |
| -ne | Not Equal |
| -gt | Greater Than |
| -lt | Less Than |
| -ge | Greater Than or Equal |
| -le | Less Than or Equal |

---

# Examples

## Equal

```bash
[ $a -eq $b ]
```

---

## Greater Than

```bash
[ $a -gt $b ]
```

---

## Less Than

```bash
[ $a -lt $b ]
```

---

# if-else Statement

## Syntax

```bash
if [ condition ]
then
    commands
else
    commands
fi
```

---

## Example

```bash
#!/bin/bash

age=18

if [ $age -ge 18 ]
then
    echo "Adult"
else
    echo "Minor"
fi
```

---

# Loops

## Purpose

Repeat commands multiple times.

---

# while Loop

## Syntax

```bash
while [ condition ]
do
    commands
done
```

---

## Example

```bash
#!/bin/bash

counter=1

while [ $counter -le 5 ]
do
    echo $counter
    ((counter++))
done
```

Output:

```text
1
2
3
4
5
```

---

# for Loop

## Syntax

```bash
for variable in values
do
    commands
done
```

---

## Example

```bash
#!/bin/bash

for i in 1 2 3 4 5
do
    echo $i
done
```

Output:

```text
1
2
3
4
5
```

---

# Loop Control Statements

Used to control loop execution.

---

# break Statement

## Purpose

Immediately exits the loop.

---

## Example

```bash
#!/bin/bash

counter=1

while [ $counter -le 10 ]
do
    echo $counter

    if [ $counter -eq 5 ]
    then
        break
    fi

    ((counter++))
done

echo "Loop Exited"
```

Output:

```text
1
2
3
4
5
Loop Exited
```

---

# How break Works

```text
Condition Met
      │
      ▼
break
      │
      ▼
Exit Loop
```

---

# continue Statement

## Purpose

Skips the current iteration and continues with the next iteration.

---

## Example

```bash
#!/bin/bash

for i in 1 2 3 4 5
do
    if [ $i -eq 3 ]
    then
        continue
    fi

    echo $i
done
```

Output:

```text
1
2
4
5
```

---

# Script Execution Permissions

Linux requires execute permission.

---

## Check Permissions

```bash
ls -l script.sh
```

---

## Grant Permission

```bash
chmod +x script.sh
```

---

## Execute Script

```bash
./script.sh
```

---

# Script Template

## Recommended Structure

```bash
#!/bin/bash

# Script Name:
# Author:
# Purpose:
# Date:

# Variables

# Logic

# Output
```

---

# Security Considerations

## Important

Before running scripts:

- Verify script contents
- Remove unnecessary commands
- Avoid dangerous operations

---

# Example

Review before running:

```bash
rm -rf /
```

Never execute unknown scripts blindly.

---

# Testing Scripts

## Why Test?

To ensure:

- Correct functionality
- Expected output
- No unintended effects

---

# Testing Process

```text
Write Script
     │
     ▼
Review Code
     │
     ▼
Test Script
     │
     ▼
Deploy Script
```

---

# Common Bash Commands in Scripts

| Command | Purpose |
|----------|----------|
| echo | Display text |
| read | Accept input |
| if | Conditional logic |
| while | Loop |
| for | Loop |
| break | Exit loop |
| continue | Skip iteration |
| chmod | Set permissions |

---

# Useful Examples

## Print Message

```bash
echo "Hello"
```

---

## Read Input

```bash
read name
```

---

## Compare Numbers

```bash
if [ $a -gt $b ]
```

---

## Loop 5 Times

```bash
for i in 1 2 3 4 5
```

---

# Key Takeaways

## Shell Scripts

Automate multiple commands.

---

## Shebang

```bash
#!/bin/bash
```

Specifies Bash interpreter.

---

## Arguments

```bash
$1
$2
$3
```

Represent user-supplied values.

---

## Conditions

```bash
if
else
```

Control script logic.

---

## Loops

```bash
while
for
```

Repeat tasks.

---

## Loop Control

```bash
break
continue
```

Manage loop execution.

---

## Security

Always inspect scripts before running.

---

## Testing

Verify scripts function correctly.

---

# Exam / Interview Questions

### Q1. What is a shell script?

**Answer:** A file containing Linux commands executed automatically.

---

### Q2. What is the purpose of `#!/bin/bash`?

**Answer:** Specifies that the script should run using the Bash shell.

---

### Q3. Which command gives execute permission?

**Answer:**

```bash
chmod +x script.sh
```

---

### Q4. What does `$1` represent?

**Answer:** First command-line argument.

---

### Q5. What does `$0` represent?

**Answer:** Script name.

---

### Q6. Which statement is used for decision making?

**Answer:**

```bash
if
```

---

### Q7. Which operator means "greater than"?

**Answer:**

```bash
-gt
```

---

### Q8. Which loop repeats while a condition is true?

**Answer:**

```bash
while
```

---

### Q9. What does `break` do?

**Answer:** Immediately exits a loop.

---

### Q10. What does `continue` do?

**Answer:** Skips the current iteration and continues with the next.

---

# Memory Tricks

## Script Structure

Remember:

```text
S → Shebang
C → Comments
L → Logic
O → Output
```

---

## Arguments

```text
$0 = Script
$1 = First Input
$2 = Second Input
```

---

## Loops

```text
while = Repeat while true
for   = Repeat through list
```

---

## Loop Control

```text
break    = Exit Loop
continue = Skip Iteration
```

---

# One-Line Exam Revision

**Bash shell scripts automate Linux tasks using commands, variables, arguments, conditions (`if`), loops (`for`, `while`), and control statements (`break`, `continue`), enabling efficient system administration and automation.**

🚀