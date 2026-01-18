# Managing Services in Linux

## Module Objectives

After completing this module, you should be able to:

- Understand Linux services.
- Manage services using `systemctl`.
- Monitor service status.
- Enable and disable services at boot.
- Use Linux monitoring commands.
- Understand AWS CloudWatch basics.

---

# Introduction to Linux Services

## What is a Service?

A service is a program that runs in the background and provides functionality to the system.

Examples:

```text
Web Server (httpd)
SSH Server (sshd)
Database Server (mysqld)
Cron Scheduler (crond)
```

Services usually start automatically and continue running without user interaction.

---

# Why Are Services Important?

Services provide:

- Networking
- Remote Administration
- Security
- Web Hosting
- Scheduling Tasks

Examples:

```text
HTTP Service → Website Hosting
SSH Service → Remote Access
Cron Service → Task Scheduling
```

---

# Managing Services

Linux systems commonly use:

```text
systemd
```

The primary command is:

```bash
systemctl
```

---

# systemctl Command

## Purpose

Used to:

- Start services
- Stop services
- Restart services
- Enable services
- Disable services
- Check service status

---

## Syntax

```bash
systemctl <subcommand> <service_name>
```

Example:

```bash
systemctl status httpd
```

---

# Common systemctl Subcommands

| Command | Purpose |
|----------|----------|
| status | View service status |
| start | Start service |
| stop | Stop service |
| restart | Restart service |
| enable | Start service at boot |
| disable | Prevent service from starting at boot |

---

# Checking Service Status

## Syntax

```bash
sudo systemctl status service_name
```

---

## Example

```bash
sudo systemctl status httpd
```

Output may show:

```text
Active: inactive (dead)
```

or

```text
Active: active (running)
```

---

# Starting a Service

## Syntax

```bash
sudo systemctl start service_name
```

---

## Example

```bash
sudo systemctl start httpd
```

Starts the Apache web server.

---

# Stopping a Service

## Syntax

```bash
sudo systemctl stop service_name
```

---

## Example

```bash
sudo systemctl stop httpd
```

Stops Apache.

---

# Restarting a Service

## Syntax

```bash
sudo systemctl restart service_name
```

---

## Example

```bash
sudo systemctl restart httpd
```

---

# Why Restart a Service?

Common reasons:

### Configuration Change

```text
Edited config file
```

---

### Troubleshooting

```text
Service not responding
```

---

### Applying Updates

```text
New settings take effect
```

---

# Enable a Service at Boot

## Syntax

```bash
sudo systemctl enable service_name
```

---

## Example

```bash
sudo systemctl enable httpd
```

---

## Purpose

Starts service automatically when Linux boots.

---

# Disable a Service

## Syntax

```bash
sudo systemctl disable service_name
```

---

## Example

```bash
sudo systemctl disable httpd
```

---

# Example Workflow

Install Apache:

```bash
sudo yum install httpd
```

Check status:

```bash
sudo systemctl status httpd
```

Start service:

```bash
sudo systemctl start httpd
```

Enable service:

```bash
sudo systemctl enable httpd
```

---

# Listing Services

## Show Running Services

```bash
systemctl
```

---

## List All Services

```bash
systemctl list-units --type=service
```

---

## List Active Services

```bash
systemctl list-units --type=service --state=active
```

---

# Service Management Flow

```text
Install Service
       │
       ▼
Check Status
       │
       ▼
Start Service
       │
       ▼
Enable Service
       │
       ▼
Monitor Service
```

---

# Monitoring Linux Systems

Linux provides commands to monitor:

- CPU
- Memory
- Disk
- Hardware
- Processes

---

# System Monitoring Commands

| Command | Purpose |
|----------|----------|
| lscpu | Display CPU information |
| lshw | Display hardware information |
| du | Display file/directory size |
| df | Display disk usage |
| fdisk | View disk partitions |
| vmstat | Virtual memory statistics |
| free | Physical memory usage |
| top | Process monitoring |
| uptime | System uptime |

---

# lscpu Command

## Purpose

Displays CPU details.

### Example

```bash
lscpu
```

Shows:

```text
CPU Model
CPU Cores
Architecture
```

---

# lshw Command

## Purpose

Displays hardware information.

### Example

```bash
sudo lshw
```

Shows:

```text
CPU
RAM
Disk
Network Devices
```

---

# du Command

## Purpose

Displays disk usage of files and directories.

---

## Syntax

```bash
du
```

---

## Human Readable Format

```bash
du -h
```

---

## Example

```bash
du -sh Documents
```

Output:

```text
2.5G Documents
```

---

# df Command

## Purpose

Displays free disk space.

---

## Syntax

```bash
df
```

---

## Human Readable

```bash
df -h
```

---

## Example

```text
Filesystem Size Used Avail Use%
/dev/sda1 50G 20G 30G 40%
```

---

# fdisk Command

## Purpose

View and manage disk partitions.

---

## Example

```bash
sudo fdisk -l
```

Displays:

```text
Partitions
Disk Layout
```

---

# vmstat Command

## Purpose

Displays virtual memory statistics.

---

## Example

```bash
vmstat
```

Shows:

```text
Memory
CPU
Processes
I/O
```

---

# free Command

## Purpose

Displays RAM usage.

---

## Syntax

```bash
free
```

---

## Human Readable

```bash
free -h
```

---

## Example

```text
Total Used Free
```

---

# top Command

## Purpose

Real-time system monitoring.

---

## Example

```bash
top
```

Displays:

```text
CPU Usage
Memory Usage
Running Processes
```

---

# Troubleshooting with top

Example:

```text
Server CPU = 100%
```

Use:

```bash
top
```

to identify which process is consuming resources.

---

# uptime Command

## Purpose

Shows:

- System uptime
- Number of users
- Load averages

---

## Example

```bash
uptime
```

Output:

```text
10 days, 5 users, load average: 0.20
```

---

# AWS CloudWatch

## What is Amazon CloudWatch?

:contentReference[oaicite:0]{index=0} is an AWS monitoring service used to monitor AWS resources and applications.

---

# CloudWatch Monitors

Examples:

- EC2 CPU Usage
- Disk Reads
- Disk Writes
- Network Activity

---

# CloudWatch Alarms

Example:

```text
CPU > 80%
```

CloudWatch can trigger:

- Email notifications
- SMS notifications
- Automated actions

using :contentReference[oaicite:1]{index=1} (Amazon SNS).

---

# Why Restart a Service Instead of the Entire Server?

## Service Restart

```text
Only affected service restarts
```

Advantages:

- Faster
- Less downtime
- Other services continue running

---

## Server Reboot

```text
Everything stops
```

Disadvantages:

- More downtime
- Impacts all users

---

# Checkpoint Questions

## Q1. How can top help during troubleshooting?

### Answer

It identifies processes consuming excessive CPU or memory resources.

---

## Q2. Why restart a service instead of rebooting the server?

### Answer

Restarting only the failed service minimizes downtime and keeps healthy services running.

---

# Useful Commands Summary

| Command | Purpose |
|----------|----------|
| systemctl status | Check service status |
| systemctl start | Start service |
| systemctl stop | Stop service |
| systemctl restart | Restart service |
| systemctl enable | Start at boot |
| systemctl disable | Disable at boot |
| du | Directory size |
| df | Disk space |
| free | Memory usage |
| top | Resource monitoring |
| uptime | System uptime |

---

# Key Takeaways

## Service Management

Use:

```bash
systemctl
```

to manage Linux services.

---

## Common Tasks

```bash
status
start
stop
restart
enable
disable
```

---

## Monitoring

Use:

```bash
top
df
du
free
uptime
```

to monitor system resources.

---

## Cloud Monitoring

AWS uses:

```text
Amazon CloudWatch
```

to monitor cloud resources.

---

# Exam / Interview Questions

### Q1. Which command manages Linux services?

**Answer:**

```bash
systemctl
```

---

### Q2. Which command checks service status?

**Answer:**

```bash
systemctl status service_name
```

---

### Q3. Which command starts a service?

**Answer:**

```bash
systemctl start service_name
```

---

### Q4. Which command enables a service at boot?

**Answer:**

```bash
systemctl enable service_name
```

---

### Q5. Which command shows disk free space?

**Answer:**

```bash
df
```

---

### Q6. Which command shows directory size?

**Answer:**

```bash
du
```

---

### Q7. Which command shows memory usage?

**Answer:**

```bash
free
```

---

### Q8. Which command displays CPU information?

**Answer:**

```bash
lscpu
```

---

### Q9. Which command shows real-time process activity?

**Answer:**

```bash
top
```

---

### Q10. What AWS service monitors EC2 performance?

**Answer:** Amazon CloudWatch.

---

# Memory Tricks

## Service Commands

```text
S → Status
S → Start
S → Stop
R → Restart
E → Enable
D → Disable
```

---

## Monitoring Commands

Remember:

```text
D → df (Disk Free)
D → du (Disk Usage)
F → free (Memory)
T → top (Processes)
U → uptime
```

---

# One-Line Exam Revision

**Linux services are managed using `systemctl`, system performance is monitored using commands such as `top`, `df`, `du`, `free`, and `uptime`, and AWS resources can be monitored through Amazon CloudWatch.**

🚀