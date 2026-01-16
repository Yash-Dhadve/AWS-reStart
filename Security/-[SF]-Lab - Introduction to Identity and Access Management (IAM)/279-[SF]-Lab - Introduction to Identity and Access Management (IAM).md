# AWS IAM Lab Walkthrough & Interview Notes

# Lab: Introduction to AWS Identity and Access Management (IAM)

## Objective

Learn how to:

* Create and configure IAM Password Policies
* Manage IAM Users and User Groups
* Understand IAM Policies
* Assign users to groups
* Test permissions using IAM Sign-In URL
* Apply Role-Based Access Control (RBAC)

---

# 1. What is IAM?

IAM (Identity and Access Management) is an AWS service used to securely manage:

* Users
* Groups
* Roles
* Permissions
* Access Policies

### Key Benefits

* Centralized access control
* Least privilege implementation
* Secure authentication
* Fine-grained authorization

---

# 2. IAM Components

## IAM User

Represents an individual person or application.

Examples:

* user-1
* user-2
* user-3

---

## IAM Group

Collection of users having similar permissions.

Examples:

| Group       | Purpose              |
| ----------- | -------------------- |
| EC2-Support | Read EC2 Resources   |
| S3-Support  | Read S3 Resources    |
| EC2-Admin   | Manage EC2 Instances |

---

## IAM Policy

JSON document defining permissions.

Contains:

### Effect

Determines action.

Examples:

```json
"Effect":"Allow"
```

```json
"Effect":"Deny"
```

### Action

Specifies AWS API operations.

Example:

```json
"Action":"ec2:DescribeInstances"
```

### Resource

Target AWS resource.

Example:

```json
"Resource":"*"
```

---

# 3. Task 1 - Create Password Policy

## Navigation

```text
IAM
 └── Account Settings
      └── Change Password Policy
```

### Configuration

| Setting             | Value            |
| ------------------- | ---------------- |
| Minimum Length      | 10               |
| Uppercase           | Enabled          |
| Lowercase           | Enabled          |
| Numbers             | Enabled          |
| Symbols             | Enabled          |
| Password Expiration | 90 Days          |
| Prevent Reuse       | Last 5 Passwords |

### Purpose

Improves account security.

### Interview Question

Q: Why use Password Policy?

Answer:
To enforce strong passwords and reduce the risk of unauthorized access.

---

# 4. Task 2 - Explore Users

## Navigation

```text
IAM
 └── Users
```

### Existing Users

```text
user-1
user-2
user-3
```

### Observation

Initially:

```text
No permissions
No group membership
```

Permissions are inherited from groups.

---

# 5. Task 2 - Explore User Groups

## Navigation

```text
IAM
 └── User Groups
```

### Group 1: EC2-Support

Attached Policy:

```text
AmazonEC2ReadOnlyAccess
```

Capabilities:

* View EC2
* View CloudWatch
* View ELB
* View Auto Scaling

Cannot:

* Start Instance
* Stop Instance
* Delete Instance

---

### Group 2: S3-Support

Attached Policy:

```text
AmazonS3ReadOnlyAccess
```

Capabilities:

* List Buckets
* View Objects

Cannot:

* Upload
* Delete
* Modify

---

### Group 3: EC2-Admin

Policy Type:

```text
Customer Inline Policy
```

Capabilities:

* Describe EC2
* Start Instances
* Stop Instances

---

# 6. Managed Policy vs Inline Policy

## Managed Policy

Created once and attached to multiple users/groups.

Examples:

```text
AmazonEC2ReadOnlyAccess
AmazonS3ReadOnlyAccess
```

Advantages:

* Reusable
* Easy to maintain

---

## Inline Policy

Attached to only one user/group.

Advantages:

* Specific permissions
* One-off requirements

Example:

```text
EC2-Admin-Policy
```

---

# 7. Task 3 - Add Users to Groups

## Business Requirement

| User   | Group       |
| ------ | ----------- |
| user-1 | S3-Support  |
| user-2 | EC2-Support |
| user-3 | EC2-Admin   |

---

## Steps

### Add user-1

```text
IAM
 └── User Groups
      └── S3-Support
           └── Users
                └── Add Users
```

Select:

```text
user-1
```

---

### Add user-2

Assign to:

```text
EC2-Support
```

---

### Add user-3

Assign to:

```text
EC2-Admin
```

---

## Verification

Each group should show:

```text
Users = 1
```

---

# 8. Task 4 - IAM Sign-In URL

## Navigation

```text
IAM
 └── Dashboard
```

Copy:

```text
IAM User Sign-In URL
```

Example:

```text
https://123456789012.signin.aws.amazon.com/console
```

Purpose:

Allows IAM users to log into AWS Console.

---

# 9. Permission Testing

## Login as user-1

Credentials:

```text
Username: user-1
Password: Lab-Password1
```

### Result

Can:

```text
View S3 Buckets
View Objects
```

Cannot:

```text
Access EC2
```

Error:

```text
You are not authorized to perform this operation
```

---

## Login as user-2

Credentials:

```text
Username: user-2
Password: Lab-Password2
```

### Result

Can:

```text
View EC2 Instances
```

Cannot:

```text
Stop EC2 Instance
```

Error:

```text
Failed to stop instance
Not authorized
```

Cannot:

```text
Access S3
```

---

## Login as user-3

Credentials:

```text
Username: user-3
Password: Lab-Password3
```

### Result

Can:

```text
View EC2
Start EC2
Stop EC2
```

Instance successfully enters:

```text
Stopping State
```

---

# Permission Matrix

| User   | S3 View | EC2 View | Start EC2 | Stop EC2 |
| ------ | ------- | -------- | --------- | -------- |
| user-1 | Yes     | No       | No        | No       |
| user-2 | No      | Yes      | No        | No       |
| user-3 | No      | Yes      | Yes       | Yes      |

---

# Key Concepts Learned

## Principle of Least Privilege

Users receive only the permissions required for their job.

Examples:

* S3 Team → S3 Access
* EC2 Support → Read EC2
* EC2 Admin → Manage EC2

---

## Role Based Access Control (RBAC)

Permissions are assigned through groups rather than directly to users.

Benefits:

* Easier management
* Better security
* Scalability

---

# Interview Questions

## Q1. What is IAM?

AWS service used to manage authentication and authorization.

---

## Q2. Difference between Authentication and Authorization?

Authentication:

```text
Who are you?
```

Authorization:

```text
What can you do?
```

---

## Q3. What is an IAM Policy?

JSON document defining permissions.

---

## Q4. What is the difference between IAM User and IAM Role?

User:

```text
Permanent identity
```

Role:

```text
Temporary permissions
```

---

## Q5. Managed Policy vs Inline Policy?

Managed:

```text
Reusable
```

Inline:

```text
Attached to single entity
```

---

## Q6. What is Least Privilege?

Grant only required permissions.

---

## Q7. Why use IAM Groups?

To assign permissions to multiple users efficiently.

---

# Lab Summary

Successfully performed:

✅ Password Policy Configuration

✅ IAM User Exploration

✅ IAM Group Exploration

✅ Managed & Inline Policy Inspection

✅ User-to-Group Assignment

✅ IAM Sign-In URL Usage

✅ Permission Verification

✅ Role-Based Access Control Implementation

✅ EC2 and S3 Access Testing

---

# Real-World Architecture

```text
IAM
│
├── Users
│   ├── user-1
│   ├── user-2
│   └── user-3
│
├── Groups
│   ├── S3-Support
│   │      └── AmazonS3ReadOnlyAccess
│   │
│   ├── EC2-Support
│   │      └── AmazonEC2ReadOnlyAccess
│   │
│   └── EC2-Admin
│          └── EC2-Admin-Policy
│
└── Password Policy
       ├── 10 Characters
       ├── Complexity Enabled
       ├── Expire 90 Days
       └── Reuse Prevention
```
