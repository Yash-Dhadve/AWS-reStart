# AWS Shared Responsibility Model

## Module Objectives

After completing this module, you should be able to:

- Describe AWS Cloud security and the Shared Responsibility Model.
- Identify AWS security responsibilities.
- Identify customer security responsibilities.
- Understand the difference between "Security of the Cloud" and "Security in the Cloud".

---

# Introduction

Security is the highest priority at AWS.

AWS provides:

- Secure cloud infrastructure
- High availability
- Reliability
- Scalability
- Security tools and services

When a customer uses AWS, security responsibilities are shared between AWS and the customer.

This concept is called the **AWS Shared Responsibility Model**.

---

# AWS Shared Responsibility Model

## Core Principle

### AWS Responsibility

**Security OF the Cloud**

AWS protects the infrastructure that runs AWS services.

---

### Customer Responsibility

**Security IN the Cloud**

Customers secure their own data, applications, and configurations running on AWS.

---

# Shared Responsibility Diagram

```text
                    AWS Shared Responsibility Model

 ┌──────────────────────────────────────────────────────┐
 │               Customer Responsibility                │
 │            (Security IN the Cloud)                   │
 ├──────────────────────────────────────────────────────┤
 │ • Customer Data                                      │
 │ • Applications                                       │
 │ • IAM Users & Permissions                            │
 │ • Operating System Configuration                     │
 │ • Network Configuration                              │
 │ • Firewall Configuration                             │
 │ • Encryption Settings                                │
 │ • Security Groups                                    │
 │ • Data Protection                                    │
 └──────────────────────────────────────────────────────┘

 ┌──────────────────────────────────────────────────────┐
 │                  AWS Responsibility                  │
 │             (Security OF the Cloud)                  │
 ├──────────────────────────────────────────────────────┤
 │ • Physical Data Centers                              │
 │ • Hardware                                           │
 │ • Networking Infrastructure                          │
 │ • Storage Infrastructure                             │
 │ • Compute Infrastructure                             │
 │ • Database Infrastructure                            │
 │ • Global Infrastructure                              │
 │ • Regions                                            │
 │ • Availability Zones                                │
 │ • Edge Locations                                     │
 └──────────────────────────────────────────────────────┘
```

---

# AWS Responsibilities

## Security OF the Cloud

AWS is responsible for protecting:

### 1. Physical Facilities

- Data centers
- Buildings
- Physical access controls

---

### 2. Hardware

- Servers
- Storage devices
- Network equipment

---

### 3. Networking Infrastructure

- Routers
- Switches
- Global backbone network

---

### 4. Virtualization Layer

- Hypervisors
- Host operating systems

---

### 5. AWS Global Infrastructure

- Regions
- Availability Zones
- Edge Locations

---

### 6. Managed Service Infrastructure

AWS manages underlying infrastructure for AWS services.

Examples:

- Amazon RDS
- AWS Lambda
- Amazon DynamoDB

---

# Customer Responsibilities

## Security IN the Cloud

Customers are responsible for securing everything they deploy on AWS.

---

### 1. Customer Data

Examples:

- Databases
- Files
- Backups
- Business information

---

### 2. Applications

Examples:

- Web applications
- APIs
- Enterprise software

---

### 3. Identity and Access Management

Using:

- IAM Users
- IAM Groups
- IAM Roles
- Policies

---

### 4. Operating System Management

Examples:

- Installing updates
- Applying security patches
- Hardening systems

---

### 5. Firewall Configuration

Examples:

- Security Groups
- Network ACLs

---

### 6. Encryption

#### Client-Side Encryption

Data encrypted before sending to AWS.

#### Server-Side Encryption

Data encrypted while stored in AWS.

---

### 7. Network Security

Examples:

- SSL/TLS
- VPN
- Secure communication channels

---

# Security Responsibilities by Service Type

## Infrastructure as a Service (IaaS)

### Examples

- Amazon EC2
- Amazon EBS
- Amazon VPC

---

### AWS Manages

- Physical hardware
- Networking
- Data centers
- Virtualization layer

---

### Customer Manages

- Guest OS
- Applications
- Security patches
- Firewalls
- Security groups
- Data

---

## Platform as a Service (PaaS)

### Examples

- Amazon RDS
- AWS Lambda
- Amazon DynamoDB

---

### AWS Manages

- Infrastructure
- Operating systems
- Platform maintenance
- Database patching
- Firewall management
- Disaster recovery

---

### Customer Manages

- Data
- User access
- Permissions
- Data classification

---

# Examples of Shared Responsibility

## Example 1: Amazon EC2

### AWS Responsibility

- Physical server
- Network infrastructure
- Hypervisor

### Customer Responsibility

- EC2 Operating System
- Software installation
- Application security
- Security patches
- Data encryption

---

## Example 2: Amazon RDS

### AWS Responsibility

- Database software patching
- OS maintenance
- Hardware maintenance
- Backup infrastructure

### Customer Responsibility

- Database data
- User permissions
- Access control
- Encryption settings

---

## Example 3: AWS Lambda

### AWS Responsibility

- Server management
- Runtime infrastructure
- Scaling

### Customer Responsibility

- Function code
- IAM permissions
- Sensitive data protection

---

# Importance of the Shared Responsibility Model

## Benefits

### Security Clarity

Clearly defines who is responsible for what.

---

### Better Protection

Both AWS and customers contribute to security.

---

### Compliance Support

Helps organizations meet regulatory requirements.

---

### Reduced Operational Burden

AWS handles infrastructure security.

---

# Quick Comparison

| Area | AWS Responsibility | Customer Responsibility |
|--------|------------------|-------------------------|
| Data Centers | ✅ | ❌ |
| Hardware | ✅ | ❌ |
| Networking Infrastructure | ✅ | ❌ |
| Regions & AZs | ✅ | ❌ |
| Customer Data | ❌ | ✅ |
| Applications | ❌ | ✅ |
| IAM Permissions | ❌ | ✅ |
| Security Groups | ❌ | ✅ |
| OS Patching (EC2) | ❌ | ✅ |
| Data Encryption | Shared | Shared |

---

# Key Takeaways

## AWS and Customer Share Security Responsibilities

### AWS

Responsible for:

- Security OF the Cloud
- Hardware
- Software infrastructure
- Networking
- Physical facilities
- AWS Global Infrastructure

---

### Customer

Responsible for:

- Security IN the Cloud
- Data
- Applications
- IAM configuration
- OS patching
- Firewall settings
- Security groups

---

### IaaS Services

Examples:

- EC2
- EBS
- VPC

Customer performs most security management tasks.

---

### PaaS / Managed Services

Examples:

- RDS
- Lambda
- DynamoDB

AWS manages a larger portion of security responsibilities.

---

# Exam / Interview Questions

### Q1. What is the AWS Shared Responsibility Model?

**Answer:** A security model where AWS and customers share security responsibilities.

---

### Q2. What does AWS mean by "Security OF the Cloud"?

**Answer:** AWS protects infrastructure, hardware, networking, and facilities.

---

### Q3. What does "Security IN the Cloud" mean?

**Answer:** Customers secure their data, applications, IAM settings, and configurations.

---

### Q4. Who is responsible for EC2 operating system patching?

**Answer:** The customer.

---

### Q5. Who is responsible for AWS data center security?

**Answer:** AWS.

---

### Q6. Who manages IAM users and permissions?

**Answer:** The customer.

---

### Q7. Is Amazon RDS an IaaS or PaaS service?

**Answer:** PaaS (Managed Service).

---

### Q8. Who is responsible for security group configuration?

**Answer:** The customer.

---

### Q9. Which side is responsible for AWS Regions and Availability Zones?

**Answer:** AWS.

---

### Q10. What is the easiest way to remember the Shared Responsibility Model?

**Answer:**

- **AWS = Security OF the Cloud**
- **Customer = Security IN the Cloud**

---

# Memory Trick

## OF vs IN

### AWS → Security OF the Cloud

Think:

**"AWS Owns Facilities"**

- Data Centers
- Hardware
- Networking
- Regions
- Availability Zones

---

### Customer → Security IN the Cloud

Think:

**"Customer Controls Content"**

- Data
- Applications
- Users
- Permissions
- OS
- Firewalls
