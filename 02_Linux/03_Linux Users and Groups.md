# Linux Users and Groups

## Module Objectives

After completing this module, you should be able to:

- Understand Linux user accounts.
- Understand Linux groups and their purpose.
- Manage users and passwords.
- Understand root user privileges.
- Use `su` and `sudo` commands.
- Understand how Linux user management relates to AWS IAM.

---

# Introduction to Linux Users

## What is a User Account?

A Linux user account represents a person, service, or application that can log in and use the system.

Each user has:

- Username
- User ID (UID)
- Password
- Home Directory
- Default Shell

---

# Why Use User Accounts?

### Security

Separate access for different users.

---

### Accountability

Track user activities.

---

### Resource Control

Manage permissions and access.

---

# Linux User Structure

```text
User Account
│
├── Username
├── UID (User ID)
├── Password
├── Home Directory
└── Shell
```

---

# User IDs (UID)

## Definition

A UID (User ID) is a unique numeric identifier assigned to each user.

### Example

```text
yash : UID 1001
admin : UID 1002
```

---

# Types of Users

## 1. Root User

### Definition

The root user is the superuser of Linux.

### Characteristics

- Full control of the system.
- Can access all files.
- Can modify all settings.
- Can manage all users.

---

### Root Prompt

```bash
#
```

Example:

```bash
[root@server ~]#
```

---

## 2. Regular Users

### Definition

Normal user accounts with limited permissions.

### Example

```bash
[yash@server ~]$
```

---

## 3. System Users

Used by services and applications.

Examples:

```text
apache
mysql
nginx
```

---

# Linux Groups

## Definition

A Linux Group is a collection of users.

Groups help administrators manage permissions more efficiently.

---

# Why Use Groups?

Instead of assigning permissions individually:

```text
User1
User2
User3
```

Create one group:

```text
developers
```

and assign permissions once.

---

# Group Structure

```text
Group
│
├── User1
├── User2
├── User3
└── User4
```

---

# Benefits of Groups

### Easier Administration

Manage many users at once.

---

### Better Security

Centralized permission control.

---

### Reduced Workload

No need to configure each user separately.

---

# User Management Commands

---

# 1. useradd

## Purpose

Creates a new user account.

### Syntax

```bash
useradd username
```

### Example

```bash
sudo useradd yash
```

---

# Verify User

```bash
id yash
```

---

# 2. passwd

## Purpose

Sets or resets a user's password.

### Syntax

```bash
passwd username
```

### Example

```bash
sudo passwd yash
```

---

# Example Output

```text
New password:
Retype new password:
```

---

# 3. id

## Purpose

Displays user and group information.

### Syntax

```bash
id username
```

### Example

```bash
id yash
```

Output:

```text
uid=1001(yash)
gid=1001(yash)
groups=1001(yash)
```

---

# Root User

## Definition

The root account has unrestricted administrative privileges.

---

## Capabilities

### User Management

```bash
useradd
userdel
passwd
```

---

### File Management

```bash
chmod
chown
rm
```

---

### System Administration

```bash
systemctl
reboot
shutdown
```

---

# Warning

Be careful when using root because mistakes can affect the entire system.

---

# Switching Users with su

## Definition

The `su` command allows switching to another user account.

---

## Syntax

```bash
su username
```

### Example

```bash
su adminuser
```

---

## Switch to Root

```bash
su root
```

or

```bash
su -
```

---

## Requirement

You must know the target user's password.

---

# Using sudo

## Definition

The `sudo` command executes a command with temporary administrative privileges.

---

## Syntax

```bash
sudo command
```

### Example

```bash
sudo useradd user20
```

---

# How sudo Works

Instead of switching to root:

```bash
sudo command
```

grants temporary root permissions.

---

# Benefits of sudo

### More Secure

Users do not need the root password.

---

### Better Accountability

Every sudo action is logged.

---

### Least Privilege Principle

Users receive permissions only when needed.

---

# sudo vs su

| Feature | sudo | su |
|----------|------|----|
| Requires Current User Password | Yes | No |
| Requires Target User Password | No | Yes |
| Temporary Privilege | Yes | No |
| Full User Switch | No | Yes |
| More Secure | Yes | Less Secure |

---

# Example: Adding a User

## Method 1 - Using sudo

```bash
sudo useradd user20
```

Requirements:

- Current user password
- User must be in sudoers

---

## Method 2 - Using su

```bash
su adminuser
useradd user20
```

Requirements:

- Must know adminuser password

---

# Why sudo is Safer

### Using su

```text
student01 must know admin password
```

---

### Using sudo

```text
student01 only uses own password
```

No password sharing required.

---

# sudo Logs

Linux records all sudo activity.

---

## Log Files

### General Messages

```text
/var/log/messages
```

---

### Security Logs

```text
/var/log/secure
```

---

# Benefits of sudo Logging

### Auditing

Track who executed commands.

---

### Security Monitoring

Identify suspicious activity.

---

### Compliance

Maintain activity records.

---

# AWS Identity and Access Management (IAM)

## Definition

IAM (Identity and Access Management) is an AWS service used to manage users and permissions.

---

# IAM Functions

### Create Users

Example:

```text
Admin
Developer
Tester
```

---

### Create Groups

Example:

```text
Developers
Administrators
Support Team
```

---

### Assign Permissions

Control access to AWS resources.

---

# Linux Users vs AWS IAM Users

| Linux | AWS |
|---------|---------|
| User Account | IAM User |
| Group | IAM Group |
| Permissions | IAM Policies |
| Root User | AWS Root Account |

---

# Common User Management Commands

| Command | Purpose |
|----------|----------|
| useradd | Create user |
| passwd | Set password |
| id | Show user details |
| su | Switch user |
| sudo | Execute with admin privileges |
| whoami | Display current user |

---

# Checkpoint Questions

## Q1. Which command adds a user account?

### Answer

```bash
useradd
```

---

## Q2. Which command resets a password?

### Answer

```bash
passwd
```

---

## Q3. Why are groups useful?

### Answer

Groups allow administrators to manage permissions for multiple users as a single unit.

---

## Q4. Which command gives root permissions in the current environment?

### Answer

```bash
su root
```

or

```bash
su -
```

---

# Quick Comparison

| Term | Meaning |
|---------|----------|
| User | Individual account |
| Group | Collection of users |
| UID | User ID |
| Root | Superuser |
| su | Switch user |
| sudo | Temporary admin privilege |
| IAM | AWS identity management service |

---

# Key Takeaways

## Linux Users

- Represent individuals or services on the system.
- Identified by usernames and UIDs.

---

## Linux Groups

- Collections of users.
- Simplify permission management.

---

## Root User

- Has full system control.
- Can modify anything.

---

## su Command

- Switches to another user.
- Requires target user password.

---

## sudo Command

- Runs commands with temporary root privileges.
- Uses current user's password.
- More secure than su.

---

## IAM

- AWS service for managing users and permissions.
- Similar concept to Linux users and groups.

---

# Exam / Interview Questions

### Q1. What is a Linux user account?

**Answer:** An account representing a person, service, or application on the Linux system.

---

### Q2. What is the purpose of Linux groups?

**Answer:** To manage permissions for multiple users collectively.

---

### Q3. What is the root user?

**Answer:** The superuser with unrestricted access to the system.

---

### Q4. Which command creates a user?

**Answer:**

```bash
useradd
```

---

### Q5. Which command changes a password?

**Answer:**

```bash
passwd
```

---

### Q6. What is the difference between su and sudo?

**Answer:** `su` switches users and requires the target user's password, while `sudo` runs a command with temporary administrative privileges using the current user's password.

---

### Q7. Which log file records sudo activity?

**Answer:**

```text
/var/log/secure
```

---

### Q8. Why is sudo considered safer?

**Answer:** It avoids password sharing and logs administrative actions.

---

### Q9. What does IAM stand for?

**Answer:** Identity and Access Management.

---

### Q10. Which AWS service manages users and permissions?

**Answer:** AWS IAM.

---

# Memory Tricks

## User Management Commands

Remember:

### U-P-I

```text
U → useradd
P → passwd
I → id
```

---

## Admin Commands

Remember:

### S-S

```text
su   → Switch User
sudo → Super User Do
```

---

## Security Principle

```text
sudo = Safer
su = Switch
```

---

# One-Line Exam Revision

**Linux users and groups provide identity and permission management, the root user has full system access, `su` switches users, `sudo` grants temporary administrative privileges, and AWS IAM provides similar user and access control functionality in AWS.**

🚀