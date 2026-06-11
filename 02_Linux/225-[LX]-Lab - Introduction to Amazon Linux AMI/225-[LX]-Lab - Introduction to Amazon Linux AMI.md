# Lab Walkthrough: Introduction to an Amazon Linux AMI

## Objective

The objective of this lab was to gain hands-on experience with connecting to an Amazon Linux EC2 instance using Secure Shell (SSH) and exploring the Linux manual pages using the `man` command.

## Procedure

### 1. Started the Lab Environment

* Launched the lab from the Vocareum platform by selecting **Start Lab**.
* Waited until the lab status changed to **Ready**.
* Opened the AWS Management Console using the provided AWS button.

### 2. Retrieved Connection Credentials

* Opened the **Details** section in Vocareum.
* Downloaded the SSH key file (`labsuser.ppk` for Windows).
* Noted the public IP address of the Amazon EC2 instance.

### 3. Connected to the Amazon Linux Instance

* Opened PuTTY on the local machine.
* Configured the session using the EC2 instance's public IP address.
* Loaded the downloaded `.ppk` file under SSH authentication settings.
* Established the SSH connection and logged in as the `ec2-user`.

### 4. Accessed Linux Manual Pages

* Executed the following command to open the manual page for the `man` utility:

```bash
man man
```

### 5. Explored the Man Pages

* Navigated through the manual pages using the keyboard arrow keys.
* Identified important sections of the man page, including:

  * NAME
  * SYNOPSIS
  * DESCRIPTION
  * OVERVIEW
  * EXAMPLES
  * FILES
  * OPTIONS
  * SEE ALSO

### 6. Used the Search Functionality

* Searched within the manual page by typing:

```bash
/description
```

* Pressed **Enter** to locate the keyword.
* Used the `n` key to move to the next search result.

### 7. Exited the Manual Pages

* Pressed the `q` key to quit the man page interface and return to the Linux command prompt.

## Outcome

The lab provided practical experience in remotely accessing an Amazon Linux EC2 instance through SSH and introduced the Linux manual page system. It enhanced understanding of how to obtain command documentation, navigate help pages, and use built-in search capabilities to explore Linux commands efficiently.
