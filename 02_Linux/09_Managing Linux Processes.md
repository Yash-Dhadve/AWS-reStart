# Managing Processes in Linux

## Module Objectives

After completing this module, you should be able to:

- Understand Linux processes.
- View running processes.
- Monitor system resource usage.
- Manage foreground and background jobs.
- Schedule tasks using `at` and `cron`.
- Understand Linux daemons and services.

---

# Introduction to Processes

## What is a Process?

A process is a running instance of a program.

Examples:

```text
Firefox
Apache Web Server
MySQL Database
Python Script
```

Whenever a program executes, Linux creates a process.

---

# Types of Processes

## 1. User Processes

Started by users.

Examples:

```bash
vim
nano
python
```

---

## 2. Services

Programs running in the background.

Examples:

```text
Web Server
Database Server
SSH Server
```

---

## 3. Daemons

Background processes that provide system services.

Examples:

```text
sshd
crond
httpd
```

---

# Process Identification

Each process has:

```text
PID (Process ID)
```

Example:

```text
PID = 1234
```

Linux uses the PID to manage processes.

---

# Viewing Running Processes

# 1. ps Command

## Purpose

Displays running processes.

---

## Syntax

```bash
ps
```

---

## Full Process Listing

```bash
ps -ef
```

---

## Example Output

```text
UID   PID   PPID CMD
root  101      1 sshd
yash  500    101 bash
```

---

# ps -ef | grep

## Purpose

Search for a specific process.

### Syntax

```bash
ps -ef | grep process_name
```

---

### Example

```bash
ps -ef | grep apache
```

---

## Why is it Useful?

Allows administrators to verify whether:

- Application is running
- Service is active
- Process exists

---

# Process Tree

# 2. pstree Command

## Purpose

Displays processes in a tree structure.

---

## Syntax

```bash
pstree
```

---

## Example

```text
systemd
├── sshd
├── crond
└── httpd
```

---

# Benefits

- Shows parent-child relationships.
- Easier process visualization.

---

# Monitoring Processes

# 3. top Command

## Purpose

Displays real-time process information.

---

## Syntax

```bash
top
```

---

## Information Displayed

- CPU usage
- Memory usage
- Running processes
- Load average

---

# Example Output

```text
PID USER CPU MEM COMMAND
100 root 15% 10% httpd
200 yash 20% 5% python
```

---

# Common top Options

## Help

```bash
top -h
```

Displays help.

---

## Version

```bash
top -v
```

Displays version information.

---

## Batch Mode

```bash
top -b
```

Runs top in batch mode.

Useful for:

```text
Scripts
Logging
Output Redirection
```

---

# Why Use top?

### Monitor CPU Usage

Identify resource-heavy processes.

---

### Monitor Memory Usage

Detect memory leaks.

---

### Troubleshooting

Find unresponsive applications.

---

# Stopping Processes

## Why Stop a Process?

Sometimes processes become:

- Unresponsive
- Stuck
- Resource hungry

---

## Example

A web server:

```text
Using 100% CPU
Not serving webpages
```

May require manual termination.

---

# kill Command

## Purpose

Terminates a process.

### Syntax

```bash
kill PID
```

---

### Example

```bash
kill 1234
```

---

# Force Kill

```bash
kill -9 PID
```

Example:

```bash
kill -9 1234
```

---

# Jobs in Linux

## What is a Job?

A job is a process started and managed by a user.

Each job has:

```text
Job Number
```

---

# jobs Command

## Purpose

Lists current jobs.

### Syntax

```bash
jobs
```

---

### Example

```bash
jobs
```

Output:

```text
[1] Running vim
[2] Stopped python
```

---

# Foreground Jobs

## Definition

Processes that occupy the terminal until completion.

Example:

```bash
vim notes.txt
```

Terminal unavailable until exit.

---

# Background Jobs

## Definition

Processes that continue running while terminal remains usable.

---

# Suspend a Job

Press:

```text
CTRL + Z
```

---

# Move Job to Background

## Syntax

```bash
bg %jobnumber
```

---

### Example

```bash
bg %1
```

---

# Move Job to Foreground

## Syntax

```bash
fg %jobnumber
```

---

### Example

```bash
fg %1
```

---

# Jobs Workflow

```text
Run Program
      │
      ▼
Foreground Job
      │
CTRL+Z
      ▼
Stopped Job
      │
bg
      ▼
Background Job
      │
fg
      ▼
Foreground Job
```

---

# Scheduling Tasks

Linux provides tools for automatic task execution.

---

# at Command

## Purpose

Runs a command one time in the future.

---

## Example

```bash
at 5:00 PM
```

Then enter:

```bash
backup.sh
```

---

## Use Cases

- One-time backup
- Single reminder
- Temporary task

---

# cron Command

## Purpose

Runs tasks repeatedly according to a schedule.

---

# What is crontab?

**crontab = Cron Table**

Stores scheduled commands.

---

# crontab Command

## Syntax

```bash
crontab -e
```

Edit cron jobs.

---

## List Cron Jobs

```bash
crontab -l
```

---

## Remove Cron Jobs

```bash
crontab -r
```

---

# Cron Format

```text
MIN HOUR DOM MON DOW CMD
```

---

# Cron Fields

| Field | Meaning |
|---------|----------|
| MIN | Minute (0-59) |
| HOUR | Hour (0-23) |
| DOM | Day of Month (1-31) |
| MON | Month (1-12) |
| DOW | Day of Week (0-6) |
| CMD | Command |

---

# Example Cron Job

Run backup every day at 2 AM.

```text
0 2 * * * /home/yash/backup.sh
```

---

# Cron Workflow

```text
Crontab File
      │
      ▼
Cron Daemon
      │
Checks Every Minute
      │
      ▼
Runs Scheduled Tasks
```

---

# Common Uses of Cron

### Scheduled Backups

```bash
backup.sh
```

---

### Log Rotation

```bash
rotate_logs.sh
```

---

### Cleanup Scripts

```bash
cleanup.sh
```

---

### Monitoring Scripts

```bash
monitor.sh
```

---

# at vs cron

| Feature | at | cron |
|----------|----|------|
| One-Time Task | Yes | No |
| Repeated Task | No | Yes |
| Scheduling | Single Run | Recurring |
| Best For | Temporary Jobs | Automation |

---

# Useful Commands Summary

| Command | Purpose |
|----------|----------|
| ps | Show processes |
| ps -ef | Full process list |
| pstree | Process hierarchy |
| top | Real-time monitoring |
| jobs | Show jobs |
| bg | Background job |
| fg | Foreground job |
| kill | Stop process |
| at | Schedule one-time task |
| cron | Schedule recurring task |
| crontab | Manage cron jobs |

---

# Checkpoint Questions

## Q1. Why might you stop a process?

### Answer

Because it may become:

- Unresponsive
- Stuck
- Excessive CPU consumer

---

## Q2. Why is `ps -ef | grep process_name` useful?

### Answer

To verify whether a process, service, or application is running.

---

## Q3. Difference between `at` and `cron`?

### Answer

```text
at   = One-time task
cron = Repeated task
```

---

# Key Takeaways

## Linux Runs

- Daemons
- Services
- Programs

---

## Process Viewing

```bash
ps
pstree
```

---

## Monitoring

```bash
top
```

---

## Job Management

```bash
jobs
bg
fg
```

---

## Scheduling

```bash
at
cron
```

---

## Cron Uses

- Backups
- Cleanup
- Monitoring
- Log Rotation

---

# Exam / Interview Questions

### Q1. What is a process?

**Answer:** A running instance of a program.

---

### Q2. Which command displays running processes?

**Answer:**

```bash
ps
```

---

### Q3. Which command displays processes in a tree format?

**Answer:**

```bash
pstree
```

---

### Q4. Which command provides real-time monitoring?

**Answer:**

```bash
top
```

---

### Q5. What does `top -b` do?

**Answer:** Runs top in batch mode.

---

### Q6. Which command lists user jobs?

**Answer:**

```bash
jobs
```

---

### Q7. Which command moves a job to the background?

**Answer:**

```bash
bg %jobnumber
```

---

### Q8. Which command moves a job to the foreground?

**Answer:**

```bash
fg %jobnumber
```

---

### Q9. What is the purpose of cron?

**Answer:** To run recurring scheduled tasks.

---

### Q10. What is the purpose of at?

**Answer:** To run a one-time scheduled task.

---

# Memory Tricks

## Process Commands

```text
P → ps
P → pstree
T → top
```

---

## Job Commands

```text
J → jobs
B → bg
F → fg
```

---

## Scheduling

```text
A → At (Once)
C → Cron (Continuous)
```

---

# One-Line Exam Revision

**Linux manages processes using commands such as `ps`, `pstree`, and `top`, allows job control through `jobs`, `bg`, and `fg`, and supports task scheduling with `at` for one-time execution and `cron` for recurring automated tasks.**

🚀