# AWS EC2 Lab Walkthrough

## Lab Title

Amazon EC2 Instance Launch, Monitoring, Security Group Configuration, Resizing, and Termination Protection

---

# Objective

In this lab, I learned how to:

* Launch an Amazon EC2 instance.
* Configure security groups.
* Deploy a web server with User Data.
* Monitor an EC2 instance.
* Access a web application over HTTP.
* Resize EC2 instance resources.
* Test termination protection.
* Terminate an EC2 instance.

---

# Task 1: Launch an EC2 Instance

I launched a new EC2 instance with the following settings:

| Setting        | Value                     |
| -------------- | ------------------------- |
| Instance Name  | Web Server                |
| AMI            | Amazon Linux 2023         |
| Instance Type  | t3.micro                  |
| Key Pair       | None                      |
| VPC            | Lab VPC                   |
| Security Group | Web Server security group |

I created a custom security group named **Web Server security group** and removed SSH access on port 22 because I did not need direct SSH access for this lab.

I also used this User Data script to install and start the web server automatically:

```bash
#!/bin/bash
yum -y install httpd
systemctl enable httpd
systemctl start httpd
echo '<html><h1>Hello From Your Web Server!</h1></html>' > /var/www/html/index.html
```

Before launching the instance, I enabled termination protection.

The instance launched successfully, changed to the **Running** state, and passed the initial status checks.

---

# Task 2: Monitor the EC2 Instance

I checked the instance status and confirmed that the following checks passed:

* System Status Check
* Instance Status Check
* EBS Status Check

I also reviewed CloudWatch metrics such as:

* CPU Utilization
* Network In
* Network Out

To inspect the instance more closely, I used the console option for getting the instance screenshot under **Actions -> Monitor and troubleshoot -> Get Instance Screenshot**.

This helped me confirm that the EC2 instance was healthy and running as expected.

---

# Task 3: Configure Security Group and Access the Web Server

I copied the public IPv4 address of the instance and tried opening it in a browser, but the website did not load at first.

I realized that HTTP traffic was blocked because there was no inbound rule for port 80.

To fix that, I added this inbound rule to the security group:

| Type | Protocol | Port | Source                    |
| ---- | -------- | ---- | ------------------------- |
| HTTP | TCP      | 80   | Anywhere-IPv4 (0.0.0.0/0) |

After updating the rule, I opened:

```text
http://<Public-IP>
```

The page displayed:

```html
Hello From Your Web Server!
```

That confirmed the web server was reachable over HTTP.

---

# Task 4: Resize the EC2 Instance

I stopped the EC2 instance before making any changes.

Then I changed the instance type from:

```text
t3.micro -> t3.small
```

I also increased the root EBS volume from:

```text
8 GiB -> 10 GiB
```

After the resize was complete, I started the instance again.

The instance came back up successfully with the updated compute and storage settings.

---

# Task 5: Test Termination Protection

I first tried to terminate the instance from **Instance State -> Terminate Instance**, but the request failed because termination protection was enabled.

Next, I disabled termination protection from **Actions -> Instance Settings -> Change Termination Protection**.

After that, I terminated the instance successfully.

This confirmed that termination protection blocks accidental deletion until it is intentionally turned off.

---

# Learning Outcomes

After completing this lab, I learned:

1. How to launch an Amazon EC2 instance.
2. How to use an Amazon Linux AMI.
3. How to configure security groups.
4. How to deploy a web server with User Data.
5. How to monitor EC2 health and performance.
6. How to allow HTTP traffic through a security group.
7. How to resize EC2 compute and storage resources.
8. How termination protection helps prevent accidental deletion.
9. How to terminate AWS resources safely.

---

# Conclusion

This lab gave me hands-on practice with launching, monitoring, resizing, and terminating an Amazon EC2 instance. I also worked with security groups, User Data, CloudWatch monitoring, EBS volume management, and termination protection, which helped me understand the core building blocks of EC2 administration.
