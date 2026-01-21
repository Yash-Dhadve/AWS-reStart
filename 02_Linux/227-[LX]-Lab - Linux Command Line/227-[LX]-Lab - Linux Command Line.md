# Linux Command Line Lab Walkthrough

## Aim

In this lab, I connected to an Amazon Linux EC2 instance using SSH and practiced basic Linux command-line operations, including viewing system information and using command history.

## Requirements

* AWS Academy Lab Environment
* AWS Management Console Access
* Amazon Linux EC2 Instance
* SSH Utility such as PuTTY for Windows or Terminal for macOS/Linux

## Procedure

### Task 1: Connect to the Amazon Linux EC2 Instance

I started the AWS lab, waited until the status changed to **Ready**, and opened the AWS Management Console.

From the **Details** section, I retrieved the connection credentials, downloaded the SSH key file, and noted the public IP address of the EC2 instance.

I then connected to the instance using SSH.

For macOS/Linux:

```bash
ssh -i labsuser.pem ec2-user@<Public-IP>
```

On Windows, I configured PuTTY with the downloaded PPK file and connected to the instance.

Once I connected successfully, I was logged in as `ec2-user`.

### Task 2: Execute Basic Linux Commands

I used a series of Linux commands to check system details.

```bash
whoami
```

This confirmed the current user:

```text
ec2-user
```

```bash
hostname -s
```

This returned the short hostname.

```bash
uptime -p
```

This showed how long the system had been running.

```bash
who -H -a
```

This displayed information about logged-in users.

I also checked the current time in different time zones:

```bash
TZ=America/New_York date
TZ=America/Los_Angeles date
```

Then I viewed calendar formats:

```bash
cal -j
cal -s
cal -m
```

Finally, I checked user and group details:

```bash
id ec2-user
```

That showed the user ID, group ID, and group memberships.

### Task 3: Use Command History and Search

I viewed my shell command history with:

```bash
history
```

I also used reverse search with `CTRL + R` and typed `TZ` to find earlier timezone commands.

After that, I ran:

```bash
date
```

Then I repeated the previous command with:

```bash
!!
```

## Result

I successfully connected to the Amazon Linux EC2 instance and used several Linux commands to gather system information. I also practiced Bash history, reverse search, and command reuse to work more efficiently at the command line.

## Conclusion

This lab gave me hands-on experience with SSH connectivity, Linux system information commands, calendar utilities, user identification commands, and Bash history features. These are important skills for basic Linux administration and troubleshooting.
