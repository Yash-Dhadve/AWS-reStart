# Amazon Simple Storage Service (Amazon S3)

## Module Objectives

After completing this module, you should be able to:

- Describe the purpose and benefits of Amazon S3.
- Understand how Amazon S3 stores data.
- Identify Amazon S3 storage classes.
- Explain Amazon S3 pricing basics.
- Access Amazon S3 using different methods.

---

# What is Amazon S3?

## Definition

Amazon Simple Storage Service (Amazon S3) is a fully managed object storage service provided by AWS.

It is designed to provide:

- High durability
- High availability
- Scalability
- Security
- Low-cost storage

---

# Key Features of Amazon S3

### Fully Managed

AWS manages:

- Hardware
- Storage infrastructure
- Availability
- Maintenance

---

### Unlimited Storage

- Store virtually unlimited data.
- Scale automatically.

---

### High Durability

Amazon S3 is designed for:

- 99.999999999% (11 nines) durability.

---

### High Availability

Data remains accessible even during failures.

---

### Pay-As-You-Go Pricing

You only pay for:

- Storage used
- Requests made
- Data transferred

---

# Amazon S3 Storage Concepts

## Bucket

A bucket is a container used to store objects in Amazon S3.

### Examples

```text
my-backup-bucket
company-documents
website-images
```

---

## Object

An object is the actual file stored inside a bucket.

### Examples

```text
photo.jpg
video.mp4
report.pdf
backup.zip
```

---

## Structure

```text
Amazon S3
│
└── Bucket
    │
    ├── photo.jpg
    ├── report.pdf
    ├── backup.zip
    └── video.mp4
```

---

# Benefits of Amazon S3

## 1. Scalability

- Automatically scales storage.
- No capacity planning required.

---

## 2. Durability

- Data is replicated across multiple devices.
- Designed for 99.999999999% durability.

---

## 3. Availability

- Data remains accessible when needed.

---

## 4. Security

Supports:

- Encryption
- Access control
- IAM integration
- Bucket policies

---

## 5. Cost Efficiency

- Pay only for what you use.
- Multiple storage classes available.

---

# Amazon S3 Storage Classes

Amazon S3 provides different storage classes for different use cases.

---

# 1. Amazon S3 Standard

## Purpose

Frequently accessed data.

### Features

- High availability
- High durability
- Low latency
- High throughput

### Use Cases

- Websites
- Mobile applications
- Content distribution
- Analytics

### Examples

```text
Website images
Application data
Active user files
```

---

# 2. Amazon S3 Intelligent-Tiering

## Purpose

Automatically optimize storage costs.

### Features

- Monitors access patterns.
- Automatically moves objects between tiers.
- No retrieval charges.

### Benefits

- Reduces storage costs.
- No performance impact.

### Best For

```text
Data with unpredictable access patterns
```

---

# 3. Amazon S3 Standard-Infrequent Access (Standard-IA)

## Purpose

Data accessed occasionally but requires fast retrieval.

### Features

- Lower storage cost
- Retrieval fee applies
- Fast access when needed

### Use Cases

```text
Backups
Disaster Recovery files
Long-term storage
```

---

# 4. Amazon S3 One Zone-Infrequent Access (One Zone-IA)

## Purpose

Infrequently accessed data stored in a single Availability Zone.

### Features

- Lower cost than Standard-IA
- Stored in one AZ only
- Fast retrieval

### Use Cases

```text
Secondary backups
Replicated data
Re-creatable data
```

---

# 5. Amazon S3 Glacier

## Purpose

Low-cost archival storage.

### Features

- Secure
- Durable
- Very low storage cost

### Retrieval Time

- Minutes to hours

### Use Cases

```text
Archives
Compliance records
Old backups
```

---

# 6. Amazon S3 Glacier Deep Archive

## Purpose

Lowest-cost Amazon S3 storage option.

### Features

- Extremely low storage cost
- Long-term retention

### Retrieval Time

- Several hours

### Use Cases

```text
Legal records
Long-term archives
Compliance data
```

---

# Storage Class Comparison

| Storage Class | Access Frequency | Retrieval Speed | Cost |
|---------------|------------------|----------------|------|
| S3 Standard | Frequent | Milliseconds | High |
| Intelligent-Tiering | Variable | Milliseconds | Optimized |
| Standard-IA | Infrequent | Milliseconds | Lower |
| One Zone-IA | Infrequent | Milliseconds | Lower |
| Glacier | Rare | Minutes to Hours | Very Low |
| Glacier Deep Archive | Very Rare | Hours | Lowest |

---

# Accessing Amazon S3

You can access Amazon S3 in multiple ways.

---

## 1. AWS Management Console

### Description

Web-based graphical interface.

### Best For

- Beginners
- Manual management

---

## 2. AWS CLI

### Description

Command-line interface for managing AWS services.

### Example

```bash
aws s3 ls
```

---

## 3. AWS SDKs

### Description

Programmatically interact with S3 using code.

### Supported Languages

- Java
- Python
- JavaScript
- C#
- Go
- PHP

---

## 4. REST Endpoints

### Description

Direct access using HTTP or HTTPS URLs.

### Example

```text
https://bucket-name.s3.amazonaws.com/file.jpg
```

---

# Amazon S3 Pricing

## Pay Only For What You Use

Pricing is based on:

### 1. Storage

Amount of data stored.

---

### 2. Requests

Operations performed.

Examples:

- PUT
- GET
- DELETE

---

### 3. Data Transfer

Data transferred out of AWS.

---

### 4. Retrieval Charges

Applicable for:

- Standard-IA
- One Zone-IA
- Glacier

---

# Common Amazon S3 Use Cases

## Backup and Recovery

```text
Database backups
System backups
Disaster recovery
```

---

## Static Website Hosting

```text
HTML
CSS
JavaScript
Images
```

---

## Content Storage

```text
Photos
Videos
Documents
Audio files
```

---

## Data Lakes

Store large datasets for:

- Analytics
- Machine Learning
- Reporting

---

## Log Storage

Store:

- Application logs
- Server logs
- Security logs

---

# Amazon S3 Security Features

## IAM Integration

Control user permissions.

---

## Bucket Policies

Control bucket access.

---

## Encryption

### Server-Side Encryption (SSE)

AWS encrypts data after upload.

---

### Client-Side Encryption

Data encrypted before upload.

---

## Versioning

Keep multiple versions of files.

---

## Access Logging

Track bucket activity.

---

# Quick Comparison

| Term | Meaning |
|--------|----------|
| Bucket | Container for storing objects |
| Object | Actual file stored in S3 |
| Storage Class | Defines cost and performance |
| Versioning | Stores multiple file versions |
| Glacier | Low-cost archival storage |
| URL Access | Access files through HTTP/HTTPS |

---

# Key Takeaways

## Amazon S3

- Fully managed object storage service.
- Stores data as objects inside buckets.

---

## Storage Capacity

- Virtually unlimited storage.

---

## Pricing

- Pay only for what you use.

---

## Access Methods

- AWS Management Console
- AWS CLI
- AWS SDKs
- REST APIs

---

## Storage Classes

- Standard
- Intelligent-Tiering
- Standard-IA
- One Zone-IA
- Glacier
- Glacier Deep Archive

---

## Benefits

- High durability
- High availability
- Scalability
- Security
- Cost optimization

---

# Exam / Interview Questions

### Q1. What is Amazon S3?

**Answer:** A fully managed object storage service provided by AWS.

---

### Q2. How is data stored in Amazon S3?

**Answer:** As objects inside buckets.

---

### Q3. What is a bucket?

**Answer:** A container used to store objects in Amazon S3.

---

### Q4. What is an object?

**Answer:** A file stored inside an S3 bucket.

---

### Q5. Which storage class is best for frequently accessed data?

**Answer:** Amazon S3 Standard.

---

### Q6. Which storage class automatically moves data between access tiers?

**Answer:** Amazon S3 Intelligent-Tiering.

---

### Q7. Which storage class is best for archival storage?

**Answer:** Amazon S3 Glacier.

---

### Q8. What is the cheapest S3 storage class?

**Answer:** Amazon S3 Glacier Deep Archive.

---

### Q9. Name four ways to access Amazon S3.

**Answer:**

- AWS Management Console
- AWS CLI
- AWS SDKs
- REST APIs

---

### Q10. How does Amazon S3 pricing work?

**Answer:** Pay only for storage used, requests made, retrievals, and data transfer.

---

# Memory Trick

## Storage Class Order

```text
Standard
↓
Intelligent-Tiering
↓
Standard-IA
↓
One Zone-IA
↓
Glacier
↓
Glacier Deep Archive
```

### Easy Way to Remember

**"Standard Intelligent Students Often Graduate Deeply"**

- Standard
- Intelligent-Tiering
- Standard-IA
- One Zone-IA
- Glacier
- Deep Archive

---

# One-Line Exam Revision

**Amazon S3 is a fully managed object storage service where data is stored as objects inside buckets, offering virtually unlimited storage with multiple storage classes and pay-as-you-go pricing.**

🚀