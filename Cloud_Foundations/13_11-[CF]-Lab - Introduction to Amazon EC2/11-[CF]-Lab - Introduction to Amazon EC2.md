# AWS EC2 Lab Walkthrough

## Lab Title

Amazon EC2 Instance Launch, Monitoring, Security Group Configuration, Resizing, and Termination Protection

---

# Objective

The objective of this lab was to learn how to:

* Launch an Amazon EC2 instance.
* Configure security groups.
* Deploy a web server using User Data.
* Monitor an EC2 instance.
* Access a web application through HTTP.
* Resize EC2 instance resources.
* Test termination protection.
* Terminate an EC2 instance.

---

# Task 1: Launch an EC2 Instance

### Instance Configuration

| Setting        | Value                     |
| -------------- | ------------------------- |
| Instance Name  | Web Server                |
| AMI            | Amazon Linux 2023         |
| Instance Type  | t3.micro                  |
| Key Pair       | None                      |
| VPC            | Lab VPC                   |
| Security Group | Web Server security group |

### Security Group Configuration

* Removed SSH (Port 22) access.
* Created a custom security group named **Web Server security group**.

### User Data Script

```bash
#!/bin/bash
yum -y install httpd
systemctl enable httpd
systemctl start httpd
echo '<html><h1>Hello From Your Web Server!</h1></html>' > /var/www/html/index.html
```

### Termination Protection

* Enabled termination protection before launching the instance.

### Result

* Instance launched successfully.
* Instance state changed to **Running**.
* Status checks passed successfully.

---

# Task 2: Monitor the EC2 Instance

### Status Checks

Verified:

* System Status Check: Passed
* Instance Status Check: Passed
* EBS Status Check: Passed

### Monitoring

Observed CloudWatch metrics such as:

* CPU Utilization
* Network In
* Network Out

### Instance Screenshot

Retrieved the instance screenshot using:

```text
Actions
→ Monitor and troubleshoot
→ Get Instance Screenshot
```

### Result

Successfully monitored the EC2 instance and verified its health.

---

# Task 3: Configure Security Group and Access Web Server

### Initial Test

* Copied Public IPv4 address.
* Opened it in a browser.
* Website was not accessible initially.

### Root Cause

HTTP traffic was blocked because no inbound rule existed for Port 80.

### Security Group Modification

Added inbound rule:

| Type | Protocol | Port | Source                    |
| ---- | -------- | ---- | ------------------------- |
| HTTP | TCP      | 80   | Anywhere-IPv4 (0.0.0.0/0) |

### Verification

Opened:

```text
http://<Public-IP>
```

Output displayed:

```html
Hello From Your Web Server!
```

### Result

Successfully accessed the web server over HTTP.

---

# Task 4: Resize the EC2 Instance

### Stop Instance

Stopped the EC2 instance before modification.

### Change Instance Type

Changed:

```text
t3.micro → t3.small
```

### Resize EBS Volume

Modified root volume size:

```text
8 GiB → 10 GiB
```

### Start Instance

Restarted the EC2 instance after modifications.

### Result

Successfully increased compute and storage resources.

---

# Task 5: Test Termination Protection

### Initial Termination Attempt

Attempted:

```text
Instance State
→ Terminate Instance
```

Termination failed because termination protection was enabled.

### Disable Termination Protection

Performed:

```text
Actions
→ Instance Settings
→ Change Termination Protection
```

Disabled protection.

### Terminate Instance

Successfully terminated the EC2 instance.

### Result

Verified the functionality of termination protection.

---

# Learning Outcomes

After completing this lab, I learned:

1. How to launch an Amazon EC2 instance.
2. How to use Amazon Linux AMIs.
3. How to configure Security Groups.
4. How to deploy a web server using User Data scripts.
5. How to monitor EC2 health and performance.
6. How to allow HTTP traffic through security groups.
7. How to resize EC2 compute and storage resources.
8. How termination protection prevents accidental deletion.
9. How to safely terminate AWS resources.

---

# Conclusion

The lab successfully demonstrated the deployment, monitoring, management, resizing, and termination of an Amazon EC2 instance. Security Groups, User Data scripts, CloudWatch monitoring, EBS volume management, and termination protection were explored, providing practical experience with core AWS EC2 operations.

