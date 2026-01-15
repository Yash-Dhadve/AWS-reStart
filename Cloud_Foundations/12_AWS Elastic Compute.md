# Amazon Elastic Compute Cloud (Amazon EC2)

## Module Objectives

After completing this module, you should be able to:

- Explain the features and uses of Amazon EC2.
- Launch an EC2 instance.
- Understand Amazon Machine Images (AMIs).
- Understand EC2 instance types.
- Describe Amazon EC2 pricing models.

---

# Introduction to Compute Services

## What is Compute?

Compute refers to the processing power required to run applications, websites, databases, and workloads.

AWS provides multiple compute services for different use cases.

---

# AWS Runtime Compute Choices

AWS offers four major compute categories:

```text
AWS Compute Services
│
├── Virtual Machines (VMs)
│   ├── Amazon EC2
│   └── Amazon Lightsail
│
├── Containers
│   └── Amazon ECS
│
├── Platform as a Service (PaaS)
│   └── AWS Elastic Beanstalk
│
├── Serverless
│   ├── AWS Lambda
│   └── AWS Fargate
│
└── Specialized Solutions
    ├── AWS Outposts
    └── AWS Batch
```

---

# Compute Service Categories

## 1. Virtual Machines (VMs)

### Services

#### Amazon EC2

- Virtual servers in the cloud.
- High customization.
- Full control over OS and software.

#### Amazon Lightsail

- Simplified VPS solution.
- Budget-friendly hosting.

---

## 2. Containers

### Amazon ECS

(Amazon Elastic Container Service)

- Run Docker containers.
- Managed container orchestration.

---

## 3. Platform as a Service (PaaS)

### AWS Elastic Beanstalk

Deploy applications without managing infrastructure.

### Supported Languages

- Java
- Python
- Node.js
- PHP
- .NET
- Ruby
- Go
- Docker

---

## 4. Serverless

### AWS Lambda

Run code without managing servers.

### Supported Languages

- Python
- Java
- Node.js
- C#
- Ruby
- Go
- PowerShell

---

### AWS Fargate

- Serverless compute for containers.
- No server management required.

---

## 5. Specialized Solutions

### AWS Outposts

Run AWS services on-premises.

---

### AWS Batch

Run batch-processing jobs at scale.

---

# What is Amazon EC2?

## Definition

Amazon Elastic Compute Cloud (Amazon EC2) is a web service that provides secure, resizable virtual servers in the cloud.

---

## Key Features

### Elastic

Scale resources up or down based on demand.

---

### Secure

Supports:

- Security Groups
- IAM
- Encryption
- VPC Networking

---

### Resizable

Change instance size whenever required.

---

### Pay-As-You-Go

Pay only for resources used.

---

# EC2 Instance

## Definition

An EC2 Instance is a virtual machine running in AWS.

### Supported Operating Systems

#### Linux

Examples:

- Ubuntu
- Amazon Linux
- Red Hat
- CentOS

#### Windows

Examples:

- Windows Server 2019
- Windows Server 2022

---

# Amazon Machine Image (AMI)

## Definition

An Amazon Machine Image (AMI) is a template used to create EC2 instances.

It contains:

- Operating System
- Software packages
- Configurations
- Storage settings

---

## Purpose

Provides all information required to launch an EC2 instance.

---

## Examples

### Linux AMI

```text
Ubuntu Server
Amazon Linux
Red Hat Enterprise Linux
```

### Windows AMI

```text
Windows Server 2019
Windows Server 2022
```

---

# EC2 Instance Types

## Definition

An EC2 Instance Type defines the hardware configuration of an EC2 instance.

It determines:

- CPU
- Memory (RAM)
- Storage
- Network Performance

---

## Example

```text
t2.micro
t3.micro
m5.large
c5.xlarge
```

---

# Instance Family Overview

## General Purpose

Balanced CPU and memory.

### Examples

```text
T-Series
M-Series
```

### Use Cases

- Web servers
- Small databases
- Development environments

---

## Compute Optimized

High CPU performance.

### Example

```text
C-Series
```

### Use Cases

- Gaming servers
- Scientific computing
- Batch processing

---

## Memory Optimized

Large RAM capacity.

### Example

```text
R-Series
```

### Use Cases

- In-memory databases
- Analytics

---

## Storage Optimized

High-speed storage.

### Example

```text
I-Series
```

### Use Cases

- Data warehousing
- Big data workloads

---

# Steps to Launch an EC2 Instance

## Step 1

Choose an AMI.

Example:

```text
Ubuntu Server 22.04
```

---

## Step 2

Choose an Instance Type.

Example:

```text
t2.micro
```

---

## Step 3

Configure Instance Details.

Examples:

- VPC
- Subnet
- Auto Scaling

---

## Step 4

Add Storage.

Example:

```text
8 GB EBS Volume
```

---

## Step 5

Configure Security Group.

Example:

```text
Allow SSH (22)
Allow HTTP (80)
Allow HTTPS (443)
```

---

## Step 6

Create or Select Key Pair.

Example:

```text
my-key.pem
```

---

## Step 7

Launch Instance.

---

# Important EC2 Configuration Components

## 1. Key Pair

### Purpose

Secure login to EC2 instances.

### Components

#### Public Key

Stored by AWS.

#### Private Key

Stored by the user.

---

## 2. Security Groups

### Purpose

Act as virtual firewalls.

### Control

- Inbound traffic
- Outbound traffic

---

### Example

```text
SSH  - Port 22
HTTP - Port 80
HTTPS - Port 443
```

---

## 3. Elastic IP

### Purpose

Static public IP address.

### Benefit

IP remains unchanged after reboot.

---

## 4. User Data

### Purpose

Automatically execute scripts during instance startup.

### Example

Install Apache automatically:

```bash
#!/bin/bash
yum install httpd -y
systemctl start httpd
```

---

# Amazon EC2 Pricing Models

AWS offers multiple pricing options.

---

# 1. On-Demand Instances

## Description

Pay only for usage.

### Benefits

- No long-term commitment.
- Flexible.

### Best For

```text
Testing
Short-term projects
Unpredictable workloads
```

---

# 2. Reserved Instances

## Description

Commit for 1 or 3 years.

### Benefits

- Significant discounts.
- Lower cost.

### Best For

```text
Steady workloads
Production environments
```

---

# 3. Spot Instances

## Description

Use unused AWS capacity at discounted prices.

### Benefits

- Up to 90% cheaper.

### Limitation

AWS can terminate instances anytime.

### Best For

```text
Batch jobs
Testing
Big data processing
```

---

# 4. Dedicated Hosts

## Description

Physical servers dedicated to one customer.

### Benefits

- Compliance requirements.
- Licensing advantages.

### Best For

```text
Enterprise workloads
Regulatory requirements
```

---

# EC2 Pricing Comparison

| Pricing Model | Cost | Commitment | Best Use Case |
|--------------|-------|------------|--------------|
| On-Demand | High | None | Short-term workloads |
| Reserved | Lower | 1-3 Years | Predictable workloads |
| Spot | Lowest | None | Flexible workloads |
| Dedicated Hosts | Highest | Optional | Compliance workloads |

---

# Amazon EC2 Use Cases

## Web Hosting

```text
Web Applications
Company Websites
Blogs
```

---

## Development & Testing

```text
Testing Environments
Development Servers
```

---

## Enterprise Applications

```text
ERP Systems
CRM Systems
Business Applications
```

---

## Big Data Processing

```text
Analytics
Data Processing
Machine Learning
```

---

## Gaming Servers

```text
Multiplayer Games
Game Backends
```

---

# Quick Comparison

| Term | Meaning |
|--------|----------|
| EC2 | Virtual machine in AWS |
| AMI | Template for launching EC2 |
| Instance Type | Hardware specification |
| Security Group | Virtual firewall |
| Key Pair | Secure login mechanism |
| Elastic IP | Static public IP |
| User Data | Startup automation script |

---

# Key Takeaways

## Amazon EC2

- Provides virtual machines in AWS.
- Supports Linux and Windows operating systems.

---

## AMI

- Template used to launch EC2 instances.
- Contains OS and configurations.

---

## Instance Types

Define:

- CPU
- Memory
- Storage
- Network performance

---

## Launching an EC2 Instance

Requires:

- AMI
- Instance Type
- Storage
- Security Group
- Key Pair

---

## Pricing Models

- On-Demand
- Reserved
- Spot
- Dedicated Hosts

---

# Exam / Interview Questions

### Q1. What is Amazon EC2?

**Answer:** A cloud service that provides virtual servers (instances) in AWS.

---

### Q2. What does EC2 stand for?

**Answer:** Elastic Compute Cloud.

---

### Q3. What is an AMI?

**Answer:** Amazon Machine Image, a template used to launch EC2 instances.

---

### Q4. What information does an instance type define?

**Answer:** CPU, memory, storage, and network performance.

---

### Q5. Which EC2 pricing model is best for temporary workloads?

**Answer:** On-Demand Instances.

---

### Q6. Which EC2 pricing model is the cheapest?

**Answer:** Spot Instances.

---

### Q7. What is a Security Group?

**Answer:** A virtual firewall that controls instance traffic.

---

### Q8. What is a Key Pair?

**Answer:** A public/private key combination used for secure access.

---

### Q9. Which EC2 pricing model requires a long-term commitment?

**Answer:** Reserved Instances.

---

### Q10. What is User Data in EC2?

**Answer:** A startup script that runs automatically when the instance launches.

---

# Memory Trick

## EC2 Launch Requirements

Remember:

### A-I-S-S-K-U

```text
A → AMI
I → Instance Type
S → Storage
S → Security Group
K → Key Pair
U → User Data
```

---

## Pricing Models

Remember:

### ORSD

```text
O → On-Demand
R → Reserved
S → Spot
D → Dedicated Hosts
```

---

# One-Line Exam Revision

**Amazon EC2 is a secure, scalable virtual machine service in AWS where instances are launched using an AMI and Instance Type, with pricing options including On-Demand, Reserved, Spot, and Dedicated Hosts.**

🚀