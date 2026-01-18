# Managing Log Files in Linux

## Module Objectives

After completing this module, you should be able to:

- Understand log files.
- Identify common Linux log locations.
- Read and analyze log files.
- Use commands to search log entries.
- Monitor logs in real time.
- Understand log rotation and its benefits.

---

# Introduction to Log Files

## What is a Log File?

A log file is a file that records events, messages, and activities occurring on a Linux system.

Logs help administrators:

- Monitor system activity
- Troubleshoot problems
- Investigate security incidents
- Audit system usage

---

# Why Are Log Files Important?

Logs provide information about:

```text
System Events
Application Events
Errors
Warnings
Security Activities
User Actions
```

---

# Examples of Logged Events

### User Login

```text
User yash logged in
```

---

### Service Start

```text
Apache service started
```

---

### System Error

```text
Disk read error
```

---

### Failed Login Attempt

```text
Authentication failure
```

---

# Logging Process

```text
Application
      │
      ▼
Log Message
      │
      ▼
Log File
      │
      ▼
Administrator Review
```

---

# Common Log File Location

Most Linux log files are stored in:

```text
/var/log
```

---

## View Log Directory

```bash
ls /var/log
```

---

# Common Linux Log Files

| Log File | Purpose |
|-----------|----------|
| /var/log/messages | General system messages |
| /var/log/secure | Authentication and security logs |
| /var/log/cron | Scheduled task logs |
| /var/log/maillog | Mail server logs |
| /var/log/boot.log | Boot process logs |

---

# System Log

## /var/log/messages

Contains:

- General system messages
- Service information
- Kernel messages

---

## Example

```bash
cat /var/log/messages
```

---

# Security Log

## /var/log/secure

Contains:

- Login attempts
- Authentication events
- sudo usage

---

## Example

```bash
cat /var/log/secure
```

---

# Cron Log

## /var/log/cron

Contains information about:

```text
Scheduled Jobs
Cron Tasks
```

---

## Example

```bash
cat /var/log/cron
```

---

# Reading Log Files

Linux provides several commands for viewing logs.

---

# cat Command

## Purpose

Displays entire file contents.

---

## Syntax

```bash
cat logfile
```

---

## Example

```bash
cat /var/log/messages
```

---

# less Command

## Purpose

View large log files page by page.

---

## Syntax

```bash
less logfile
```

---

## Example

```bash
less /var/log/messages
```

---

## Navigation

| Key | Action |
|------|---------|
| Up Arrow | Scroll Up |
| Down Arrow | Scroll Down |
| Space | Next Page |
| q | Quit |

---

# more Command

## Purpose

View log files one page at a time.

---

## Example

```bash
more /var/log/messages
```

---

# head Command

## Purpose

Display first lines of a log file.

---

## Syntax

```bash
head logfile
```

---

## Example

```bash
head /var/log/messages
```

Shows first 10 lines.

---

# Custom Number of Lines

```bash
head -20 logfile
```

---

# tail Command

## Purpose

Display last lines of a file.

---

## Syntax

```bash
tail logfile
```

---

## Example

```bash
tail /var/log/messages
```

Shows latest entries.

---

# Real-Time Monitoring

## tail -f

Monitors log updates live.

---

## Syntax

```bash
tail -f logfile
```

---

## Example

```bash
tail -f /var/log/messages
```

Useful for:

```text
Troubleshooting
Monitoring Services
Watching Live Activity
```

---

# Searching Log Files

## grep Command

Used to search specific text patterns.

---

## Syntax

```bash
grep pattern logfile
```

---

## Example

```bash
grep error /var/log/messages
```

---

# Search for Failed Logins

```bash
grep failed /var/log/secure
```

---

# Case-Insensitive Search

```bash
grep -i error logfile
```

---

# Combining Commands

## Search Recent Errors

```bash
tail -100 /var/log/messages | grep error
```

---

## Search Login Events

```bash
grep sshd /var/log/secure
```

---

# Common Log Messages

## Information

```text
INFO
```

General information.

---

## Warning

```text
WARNING
```

Potential issue.

---

## Error

```text
ERROR
```

Problem requiring attention.

---

## Critical

```text
CRITICAL
```

Serious system issue.

---

# Troubleshooting with Logs

Logs help identify:

- Failed services
- Authentication failures
- Hardware issues
- Application crashes

---

## Example

Service fails:

```bash
systemctl status httpd
```

Check logs:

```bash
tail /var/log/messages
```

---

# What is Log Rotation?

Log files continuously grow.

Without management:

```text
Logs Consume Disk Space
```

---

# Log Rotation

## Definition

Log rotation automatically:

- Archives old logs
- Compresses old logs
- Creates new log files

---

# Log Rotation Process

```text
Current Log
      │
      ▼
Archive Old Log
      │
      ▼
Compress Archive
      │
      ▼
Create New Log
```

---

# Benefits of Log Rotation

## 1. Saves Disk Space

Compressed logs use less storage.

---

## 2. Improves Performance

Smaller logs are easier to search.

---

## 3. Prevents Disk Exhaustion

Avoids:

```text
Disk Full Errors
```

---

## 4. Easier Management

Keeps logs organized.

---

# Example of Rotated Logs

```text
messages
messages.1
messages.2.gz
messages.3.gz
```

---

# Typical Log Rotation Tool

Linux commonly uses:

```text
logrotate
```

---

# logrotate

Automates:

- Rotation
- Compression
- Cleanup

---

# Example Configuration

```text
Rotate Weekly
Keep 4 Archives
Compress Old Logs
```

---

# Useful Commands Summary

| Command | Purpose |
|----------|----------|
| cat | Display full log |
| less | View large logs |
| more | View page-by-page |
| head | First lines |
| tail | Last lines |
| tail -f | Live monitoring |
| grep | Search logs |
| logrotate | Manage log rotation |

---

# Key Takeaways

## Log Files

Store:

```text
System Events
Errors
Warnings
Security Events
```

---

## Main Log Directory

```text
/var/log
```

---

## Viewing Logs

Use:

```bash
cat
less
more
head
tail
```

---

## Searching Logs

Use:

```bash
grep
```

---

## Live Monitoring

Use:

```bash
tail -f
```

---

## Log Rotation

Benefits:

- Saves space
- Improves performance
- Prevents oversized logs

---

# Exam / Interview Questions

### Q1. What is a log file?

**Answer:** A file that records system, application, and security events.

---

### Q2. Where are most Linux log files stored?

**Answer:**

```text
/var/log
```

---

### Q3. Which command displays an entire log file?

**Answer:**

```bash
cat
```

---

### Q4. Which command displays the last lines of a log file?

**Answer:**

```bash
tail
```

---

### Q5. Which command monitors logs in real time?

**Answer:**

```bash
tail -f
```

---

### Q6. Which command searches for text in logs?

**Answer:**

```bash
grep
```

---

### Q7. Which log file stores authentication events?

**Answer:**

```text
/var/log/secure
```

---

### Q8. Which log file stores general system messages?

**Answer:**

```text
/var/log/messages
```

---

### Q9. What is log rotation?

**Answer:** Automatic archiving, compression, and replacement of old log files.

---

### Q10. Which tool manages log rotation?

**Answer:**

```text
logrotate
```

---

# Memory Tricks

## Viewing Logs

```text
C → cat
L → less
H → head
T → tail
```

---

## Searching

```text
G → grep
```

---

## Monitoring

```text
tail -f = Follow Log
```

---

## Log Directory

Remember:

```text
/var/log
```

---

# One-Line Exam Revision

**Linux log files record system, application, and security events, are primarily stored in `/var/log`, can be analyzed using commands such as `cat`, `less`, `tail`, and `grep`, and are managed efficiently through log rotation using tools like `logrotate`.**

🚀