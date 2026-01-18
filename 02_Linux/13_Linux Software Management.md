# Software Management in Linux

## Module Objectives

After completing this module, you should be able to:

- Understand software package management.
- Learn how Linux installs software.
- Understand package managers and repositories.
- Differentiate Red Hat and Debian package management methods.
- Install software from source code.
- Use package download utilities such as `wget` and `curl`.

---

# Introduction to Software Management

## What is Software Management?

Software management is the process of:

- Installing software
- Updating software
- Removing software
- Tracking installed software

Linux performs these tasks through:

```text
Package Managers
```

---

# What is a Package?

A package is a bundled file that contains everything needed to install software.

---

## Package Contents

A package typically contains:

```text
Precompiled Code
Documentation
Configuration Files
Installation Instructions
```

---

# Package Structure

```text
Software Package
       │
       ├── Program Files
       ├── Libraries
       ├── Documentation
       └── Installation Instructions
```

---

# What is a Package Manager?

A package manager is a tool used to manage software packages.

---

## Responsibilities

Package managers can:

### Install

```text
Add software
```

---

### Update

```text
Upgrade software
```

---

### Inventory

```text
Track installed software
```

---

### Uninstall

```text
Remove software
```

---

# Software Lifecycle

```text
Install
   │
   ▼
Update
   │
   ▼
Inventory
   │
   ▼
Remove
```

Package managers manage the entire lifecycle.

---

# Package Repositories

## What is a Repository?

A repository is a storage location containing software packages.

---

## Types

### Remote Repository

Located on internet servers.

Example:

```text
AWS Repository
Ubuntu Repository
```

---

### Local Repository

Stored within an organization.

Example:

```text
Company Software Repository
```

---

# Linux Package Management Methods

Linux distributions use different package managers.

---

# 1. Red Hat Method

Used by:

- Amazon Linux 2
- Red Hat Enterprise Linux (RHEL)
- CentOS

---

## Package Format

```text
.rpm
```

---

## Package Manager

```text
RPM
```

(Red Hat Package Manager)

---

## Front-End Tool

```text
YUM
```

(Yellowdog Updater Modified)

---

# RPM

## Purpose

Manages:

- Installation
- Updates
- Removal

of RPM packages.

---

## Example RPM Package

```text
apache.rpm
```

---

# YUM

## Purpose

Provides an easier interface for RPM.

---

## Features

### Dependency Resolution

Automatically installs required packages.

---

### Software Updates

Simplifies updates.

---

### Repository Access

Downloads packages from repositories.

---

# Common YUM Commands

## Install Package

```bash
sudo yum install httpd
```

---

## Update Package

```bash
sudo yum update httpd
```

---

## Update Entire System

```bash
sudo yum update
```

---

## Remove Package

```bash
sudo yum remove httpd
```

---

## Search Package

```bash
yum search apache
```

---

## Package Information

```bash
yum info httpd
```

---

# 2. Debian Method

Used by:

- Debian
- Ubuntu
- Linux Mint

---

## Package Format

```text
.deb
```

---

## Package Manager

```text
dpkg
```

---

## Front-End Tool

```text
APT
```

(Advanced Package Tool)

---

# dpkg

## Purpose

Manages `.deb` packages.

---

## Example Package

```text
apache.deb
```

---

# APT

Provides a higher-level interface.

---

## Common APT Commands

### Install

```bash
sudo apt install apache2
```

---

### Update Package List

```bash
sudo apt update
```

---

### Upgrade Packages

```bash
sudo apt upgrade
```

---

### Remove Package

```bash
sudo apt remove apache2
```

---

# Red Hat vs Debian

| Feature | Red Hat Method | Debian Method |
|----------|---------------|---------------|
| Package Extension | .rpm | .deb |
| Package Manager | RPM | dpkg |
| Front-End Tool | YUM | APT |
| Common OS | Amazon Linux, CentOS, RHEL | Debian, Ubuntu |

---

# Installing Software from Source Code

## Alternative Method

Software can also be installed from:

```text
Source Code
```

---

# What is Source Code?

Human-readable program code.

Example:

```c
printf("Hello World");
```

---

# Why Install from Source?

Used when:

- Package is unavailable
- Latest version is needed
- Custom compilation is required

---

# Source Installation Process

```text
Download Source Code
        │
        ▼
Extract Files
        │
        ▼
Compile Source
        │
        ▼
Install Program
```

---

# Step 1: Download Source Code

Usually provided as:

```text
.tar.gz
```

archive file.

---

## Example

```text
software.tar.gz
```

---

# Step 2: Extract Archive

Use:

```bash
tar
```

---

## Example

```bash
tar -xvf software.tar.gz
```

---

# Step 3: Compile Source Code

Use:

```text
GCC
```

(GNU Compiler Collection)

---

# GCC Compiler

## Purpose

Converts:

```text
Human-readable Code
```

into

```text
Machine-readable Code
```

---

# Languages Supported

- C
- C++
- Objective-C
- Go

---

## Example

```bash
gcc program.c -o program
```

---

# Step 4: Install Software

After compilation:

```bash
sudo make install
```

(Depending on package instructions)

---

# File Download Utilities

Linux provides tools to download files.

---

# wget

## Purpose

Downloads files from servers.

---

## Syntax

```bash
wget URL
```

---

## Example

```bash
wget https://example.com/file.tar.gz
```

---

## Advantage

Automatically resumes interrupted downloads.

---

# curl

## Purpose

Transfers data between systems.

---

## Syntax

```bash
curl URL
```

---

## Example

```bash
curl https://example.com
```

---

# wget vs curl

| Feature | wget | curl |
|----------|------|------|
| Download Files | Yes | Yes |
| Resume Downloads | Yes | Limited |
| API Requests | Limited | Excellent |
| Common Use | File Download | Data Transfer |

---

# Checkpoint Questions

## Q1. How is software installed by a package manager provided?

### Answer

As a:

```text
Software Package
```

---

## Q2. What is another way to install software besides using a package manager?

### Answer

Install from:

```text
Source Code
```

---

## Q3. Which utility automatically resumes interrupted downloads?

### Answer

```bash
wget
```

---

# Useful Commands Summary

| Command | Purpose |
|----------|----------|
| yum install | Install package |
| yum update | Update package |
| yum remove | Remove package |
| apt install | Install package |
| apt update | Refresh repository info |
| apt upgrade | Upgrade packages |
| tar | Extract archives |
| gcc | Compile source code |
| wget | Download files |
| curl | Transfer data |

---

# Key Takeaways

## Package Managers

Used to:

- Install
- Update
- Inventory
- Remove

software.

---

## Package Contents

Contain:

- Program files
- Documentation
- Installation instructions

---

## Red Hat Systems

Use:

```text
RPM + YUM
```

---

## Debian Systems

Use:

```text
dpkg + APT
```

---

## Source Installation

Requires:

```text
Download
Extract
Compile
Install
```

---

## GCC

Compiles source code into executable programs.

---

## Download Utilities

```bash
wget
curl
```

are commonly used for downloading files.

---

# Exam / Interview Questions

### Q1. What is a package manager?

**Answer:** A tool used to install, update, inventory, and remove software.

---

### Q2. What package format does Red Hat use?

**Answer:**

```text
.rpm
```

---

### Q3. What package format does Debian use?

**Answer:**

```text
.deb
```

---

### Q4. Which package manager is used in Amazon Linux?

**Answer:**

```text
YUM
```

---

### Q5. What does RPM stand for?

**Answer:** Red Hat Package Manager.

---

### Q6. What does APT stand for?

**Answer:** Advanced Package Tool.

---

### Q7. Which compiler is commonly used to compile source code?

**Answer:**

```text
GCC
```

(GNU Compiler Collection)

---

### Q8. What command extracts a tar archive?

**Answer:**

```bash
tar -xvf file.tar.gz
```

---

### Q9. Which utility automatically resumes interrupted downloads?

**Answer:**

```bash
wget
```

---

### Q10. What are the four main software management tasks?

**Answer:**

```text
Install
Update
Inventory
Remove
```

---

# Memory Tricks

## Red Hat

```text
RPM + YUM
```

Remember:

```text
R → RPM
Y → YUM
```

---

## Debian

```text
dpkg + APT
```

Remember:

```text
D → dpkg
A → APT
```

---

## Software Lifecycle

```text
I → Install
U → Update
I → Inventory
R → Remove
```

(IUIR)

---

# One-Line Exam Revision

**Linux software management is performed through package managers such as RPM/YUM on Red Hat-based systems and dpkg/APT on Debian-based systems, while software can also be installed from source code using tools like GCC, tar, wget, and curl.**

🚀