# What Is AWS?

## Learning Objectives

After completing this lesson, you should be able to:

- Explain what a web service is.
- Identify the main services offered by Amazon Web Services (AWS).
- Describe ways to access AWS services.
- Navigate AWS documentation resources.

---

# What is AWS?

## Definition

**Amazon Web Services (AWS)** is a cloud computing platform provided by Amazon that offers a wide range of on-demand IT services over the internet.

AWS allows individuals, businesses, and governments to access computing resources without owning physical infrastructure.

### AWS Provides

- Computing power
- Storage
- Databases
- Networking
- Security services
- Analytics
- Artificial Intelligence (AI)
- Machine Learning (ML)

---

# What is a Web Service?

## Definition

A **web service** is a software service that is accessible over the internet and allows applications to communicate with each other.

### Examples

- Online banking
- Email services
- Weather applications
- Cloud storage services

### Characteristics

- Internet-based
- Accessible from anywhere
- Supports communication between systems
- Often uses APIs

---

# Why AWS?

Organizations use AWS because it provides:

- Scalability
- Reliability
- Security
- Flexibility
- Global availability
- Pay-as-you-go pricing

### Benefits

- No upfront infrastructure costs
- Faster deployment
- Easy scaling
- Reduced maintenance

---

# AWS Global Infrastructure

AWS operates a global cloud infrastructure consisting of:

### Regions

Geographical areas containing AWS data centers.

### Availability Zones (AZs)

One or more isolated data centers within a region.

### Edge Locations

Sites that deliver content closer to users for lower latency.

### Benefits

- High availability
- Fault tolerance
- Disaster recovery
- Faster performance

---

# Main AWS Service Categories

AWS offers hundreds of cloud services.

---

# 1. Compute Services

Provide processing power for applications.

### Popular Services

#### Amazon EC2

Elastic Compute Cloud (virtual servers).

#### AWS Lambda

Run code without managing servers.

#### Amazon ECS

Container management service.

#### Amazon EKS

Managed Kubernetes service.

---

# 2. Storage Services

Store and retrieve data.

### Popular Services

#### Amazon S3

Simple Storage Service for object storage.

#### Amazon EBS

Block storage for EC2 instances.

#### Amazon EFS

Elastic file storage.

### Benefits

- Durable
- Scalable
- Secure

---

# 3. Database Services

Manage structured and unstructured data.

### Popular Services

#### Amazon RDS

Managed relational databases.

#### Amazon DynamoDB

NoSQL database service.

#### Amazon Aurora

High-performance relational database.

### Benefits

- Automated backups
- High availability
- Easy scaling

---

# 4. Networking Services

Connect cloud resources securely.

### Popular Services

#### Amazon VPC

Virtual Private Cloud.

#### Elastic Load Balancer (ELB)

Distributes traffic across servers.

#### Amazon Route 53

DNS and domain management service.

### Benefits

- Secure communication
- Traffic management
- High availability

---

# 5. Security Services

Protect cloud resources and data.

### Popular Services

#### AWS Identity and Access Management (IAM)

Controls user permissions.

#### AWS Shield

Protection against DDoS attacks.

#### AWS Key Management Service (KMS)

Encryption key management.

### Benefits

- Access control
- Data protection
- Compliance support

---

# 6. Analytics Services

Analyze large amounts of data.

### Popular Services

#### Amazon Athena

Query data using SQL.

#### Amazon Redshift

Data warehousing service.

#### Amazon EMR

Big data processing platform.

---

# 7. Artificial Intelligence and Machine Learning

Build intelligent applications.

### Popular Services

#### Amazon SageMaker

Build and deploy ML models.

#### Amazon Rekognition

Image and video analysis.

#### Amazon Comprehend

Natural language processing.

---

# Ways to Access AWS Services

AWS services can be accessed in multiple ways.

---

# 1. AWS Management Console

## Description

A web-based graphical user interface (GUI).

### Features

- Easy to use
- Browser-based
- No programming required

### Best For

- Beginners
- Administrators
- Learning AWS

---

# 2. AWS Command Line Interface (CLI)

## Description

Manage AWS resources using commands.

### Benefits

- Automation
- Faster administration
- Scripting support

### Example

```bash
aws s3 ls
```

Lists S3 buckets.

---

# 3. AWS Software Development Kits (SDKs)

## Description

Libraries that allow applications to interact with AWS services.

### Supported Languages

- Python
- Java
- JavaScript
- C#
- Go
- PHP

### Benefit

Developers can integrate AWS directly into applications.

---

# 4. AWS APIs

## Description

Application Programming Interfaces used to communicate directly with AWS services.

### Benefits

- Automation
- Custom integrations
- Programmatic access

---

# AWS Documentation

AWS provides extensive documentation for learning and troubleshooting.

### Documentation Includes

- Service guides
- Tutorials
- API references
- Best practices
- Architecture examples

### Benefits

- Official source of information
- Step-by-step instructions
- Updated regularly

---

# AWS Service Access Comparison

| Method | User Type | Interface |
|----------|-----------|-----------|
| AWS Console | Beginners/Admins | Graphical |
| AWS CLI | Administrators | Command Line |
| AWS SDK | Developers | Programming Libraries |
| AWS API | Advanced Users | Direct Service Calls |

---

# AWS Shared Responsibility Model

AWS and customers share security responsibilities.

### AWS Responsible For

- Physical security
- Hardware
- Networking infrastructure
- Data center operations

### Customer Responsible For

- Data security
- User permissions
- Application security
- Configuration management

---

# Why AWS is Popular

### Advantages

- Global infrastructure
- Large service portfolio
- Pay-as-you-go pricing
- High availability
- Security and compliance
- Scalability
- Innovation

---

# Quick Revision

## AWS

Cloud platform that provides on-demand IT services over the internet.

---

## Main Service Categories

1. Compute
2. Storage
3. Databases
4. Networking
5. Security
6. Analytics
7. AI & Machine Learning

---

## Ways to Access AWS

1. AWS Management Console
2. AWS CLI
3. AWS SDKs
4. AWS APIs

---

# Exam Tips

### Remember AWS Service Categories

```text
Compute
Storage
Database
Networking
Security
Analytics
AI/ML
```

### Remember AWS Access Methods

```text
Console
CLI
SDK
API
```

### One-Line Definitions

- **AWS:** Cloud platform by Amazon.
- **EC2:** Virtual server service.
- **S3:** Object storage service.
- **RDS:** Managed relational database.
- **IAM:** Access management service.
- **Lambda:** Serverless computing service.

---

# Key Takeaways

- AWS is Amazon's cloud computing platform.
- AWS provides on-demand computing resources over the internet.
- Major services include Compute, Storage, Database, Networking, and Security.
- AWS services can be accessed through the Console, CLI, SDKs, and APIs.
- AWS offers global infrastructure for reliability and scalability.
- AWS documentation is the primary resource for learning and support.