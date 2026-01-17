# Managing File Permissions in Linux

## Module Objectives

After completing this module, you should be able to:

- View file and directory permissions.
- Understand Linux permission types.
- Change permissions using `chmod`.
- Compare Absolute Mode and Symbolic Mode.
- Change file ownership using `chown`.
- Apply the Principle of Least Privilege.

---

# Introduction to File Permissions

## Why Are File Permissions Important?

File permissions control:

- Who can access a file.
- Who can modify a file.
- Who can execute a file.

Proper permissions help:

- Protect sensitive data
- Prevent unauthorized access
- Improve system security

---

# Linux Security Model

Every file and directory has:

```text
Owner
Group
Others
```

Each can have different permissions.

---

# Permission Categories

## 1. Owner (u)

The user who owns the file.

---

## 2. Group (g)

Users belonging to the file's group.

---

## 3. Others (o)

Everyone else on the system.

---

# Permission Types

Linux uses three basic permissions.

| Permission | Symbol | Value |
|------------|---------|--------|
| Read | r | 4 |
| Write | w | 2 |
| Execute | x | 1 |

---

# Read Permission (r)

## Files

Allows viewing file contents.

Example:

```bash
cat file.txt
```

---

## Directories

Allows listing contents.

Example:

```bash
ls directory
```

---

# Write Permission (w)

## Files

Allows modifying file contents.

Example:

```bash
vim file.txt
```

---

## Directories

Allows:

- Create files
- Delete files
- Rename files

---

# Execute Permission (x)

## Files

Allows executing programs/scripts.

Example:

```bash
./script.sh
```

---

## Directories

Allows entering the directory.

Example:

```bash
cd directory
```

---

# Viewing Permissions

## ls -l Command

### Syntax

```bash
ls -l
```

---

### Example

```bash
-rwxrw-r-- 1 yash developers 200 Jun 10 file.txt
```

---

# Understanding Permission String

```text
-rwxrw-r--
```

Breakdown:

```text
-      File Type
rwx    Owner
rw-    Group
r--    Others
```

---

# Permission Layout

```text
-rwx rw- r--
│    │    │
│    │    └── Others
│    └────── Group
└────────── Owner
```

---

# File Types

| Symbol | Meaning |
|----------|----------|
| - | Regular File |
| d | Directory |
| l | Symbolic Link |

---

# Permission Meaning

### rwx

```text
Read
Write
Execute
```

---

### rw-

```text
Read
Write
No Execute
```

---

### r--

```text
Read Only
```

---

# chmod Command

## Purpose

Changes file or directory permissions.

### Syntax

```bash
chmod permissions filename
```

---

# Permission Modes

Linux supports two permission modes:

1. Absolute Mode (Numeric)
2. Symbolic Mode

---

# 1. Absolute Mode

## Definition

Uses numbers to represent permissions.

Most commonly used method.

---

# Numeric Values

| Permission | Value |
|------------|--------|
| Read | 4 |
| Write | 2 |
| Execute | 1 |

---

# Permission Calculations

## Read + Write

```text
4 + 2 = 6
```

---

## Read + Execute

```text
4 + 1 = 5
```

---

## Read + Write + Execute

```text
4 + 2 + 1 = 7
```

---

# Permission Table

| Number | Permission |
|----------|------------|
| 0 | --- |
| 1 | --x |
| 2 | -w- |
| 3 | -wx |
| 4 | r-- |
| 5 | r-x |
| 6 | rw- |
| 7 | rwx |

---

# Example: chmod 764

## Command

```bash
chmod 764 file.txt
```

---

## Breakdown

```text
7 = rwx (Owner)
6 = rw- (Group)
4 = r-- (Others)
```

Result:

```text
rwxrw-r--
```

---

# Common Absolute Permissions

## 777

```text
rwxrwxrwx
```

Everyone has full access.

⚠ Not recommended.

---

## 755

```text
rwxr-xr-x
```

Common for directories.

---

## 644

```text
rw-r--r--
```

Common for files.

---

## 600

```text
rw-------
```

Private file.

---

# 2. Symbolic Mode

## Definition

Uses letters and symbols to add or remove permissions.

---

# User Symbols

| Symbol | Meaning |
|----------|---------|
| u | User/Owner |
| g | Group |
| o | Others |
| a | All |

---

# Operators

| Operator | Meaning |
|-----------|---------|
| + | Add Permission |
| - | Remove Permission |
| = | Set Permission |

---

# Examples

## Add Write Permission to Group

```bash
chmod g+w file.txt
```

---

## Remove Execute Permission

```bash
chmod o-x file.txt
```

---

## Add Execute Permission

```bash
chmod u+x script.sh
```

---

## Give Read Permission to All

```bash
chmod a+r file.txt
```

---

# Absolute vs Symbolic Mode

| Feature | Absolute Mode | Symbolic Mode |
|----------|--------------|--------------|
| Uses Numbers | Yes | No |
| Uses Letters | No | Yes |
| Fast for Full Permission Sets | Yes | No |
| Good for Small Changes | No | Yes |
| Most Common | Yes | Less Common |

---

# File Ownership

Every file has:

```text
Owner
Group
```

---

# chown Command

## Purpose

Changes file ownership.

---

## Syntax

```bash
chown owner filename
```

---

## Example

```bash
chown yash file.txt
```

---

# Change Owner and Group

```bash
chown yash:developers file.txt
```

---

# Example

Before:

```text
root root file.txt
```

After:

```text
yash developers file.txt
```

---

# Permission Risks

## Incorrect Permissions Can Cause:

### Unauthorized Access

Sensitive data exposed.

---

### Data Modification

Users can change important files.

---

### Accidental Deletion

Critical files may be removed.

---

### Security Breaches

Attackers gain access.

---

# Principle of Least Privilege

## Definition

Give users only the permissions required to perform their tasks.

---

## Good Example

```text
Read Only Access
```

when modification is not required.

---

## Bad Example

```text
777
```

for sensitive files.

---

# Common Examples

## Private SSH Key

```bash
chmod 600 id_rsa
```

---

## Shell Script

```bash
chmod 755 backup.sh
```

---

## Shared File

```bash
chmod 664 report.txt
```

---

# Useful Commands Summary

| Command | Purpose |
|----------|----------|
| ls -l | View permissions |
| chmod | Change permissions |
| chown | Change ownership |
| id | View user/group IDs |

---

# Quick Comparison

| Command | Function |
|----------|-----------|
| ls -l | View permissions |
| chmod 755 file | Set permissions |
| chmod g+w file | Add group write |
| chown user file | Change owner |
| chown user:group file | Change owner & group |

---

# Key Takeaways

## File Permissions

Linux controls access using:

```text
Owner
Group
Others
```

---

## Permission Types

```text
r = Read
w = Write
x = Execute
```

---

## chmod

Changes permissions.

Supports:

- Absolute Mode
- Symbolic Mode

---

## Absolute Mode

Uses numbers.

Example:

```bash
chmod 764 file.txt
```

---

## Symbolic Mode

Uses letters.

Example:

```bash
chmod g+w file.txt
```

---

## chown

Changes file ownership.

---

## Security

Follow the Principle of Least Privilege.

---

# Exam / Interview Questions

### Q1. Which command displays file permissions?

**Answer:**

```bash
ls -l
```

---

### Q2. Which command changes permissions?

**Answer:**

```bash
chmod
```

---

### Q3. Which command changes file ownership?

**Answer:**

```bash
chown
```

---

### Q4. What does permission value 7 represent?

**Answer:**

```text
rwx
```

(Read + Write + Execute)

---

### Q5. What does permission value 6 represent?

**Answer:**

```text
rw-
```

(Read + Write)

---

### Q6. What does permission value 4 represent?

**Answer:**

```text
r--
```

(Read only)

---

### Q7. What does chmod 764 mean?

**Answer:**

```text
Owner  = rwx
Group  = rw-
Others = r--
```

---

### Q8. What does `chmod g+w file.txt` do?

**Answer:** Adds write permission for the group.

---

### Q9. Which permission mode is most commonly used?

**Answer:** Absolute (Numeric) Mode.

---

### Q10. What security principle should be followed?

**Answer:** Principle of Least Privilege.

---

# Memory Tricks

## Permission Values

```text
Read    = 4
Write   = 2
Execute = 1
```

Remember:

### R-W-X

```text
4-2-1
```

---

## Ownership

```text
u = User
g = Group
o = Others
```

---

## Commands

```text
chmod = Change Mode
chown = Change Owner
```

---

# One-Line Exam Revision

**Linux file permissions are managed using `chmod` (absolute or symbolic mode) and `chown`, with access controlled through Owner, Group, and Others permissions based on Read (4), Write (2), and Execute (1) rights.**

🚀