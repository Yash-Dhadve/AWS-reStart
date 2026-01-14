# AWS Services and Service Categories

## Module Objectives

After completing this module, you should be able to:

- Identify AWS services and service categories.
- Understand the purpose of common AWS services.
- Use the AWS Management Console to manage AWS resources.

---

# Introduction to AWS Services

AWS provides a broad collection of cloud services that help organizations:

- Build applications
- Store data
- Manage networks
- Analyze information
- Improve security
- Deploy scalable infrastructure

AWS services are grouped into different categories based on their purpose.

---

# Major AWS Service Categories

## 1. Compute Services

### Purpose

Provide computing power for running applications and workloads.

### Common Services

#### Amazon EC2 (Elastic Compute Cloud)

- Virtual servers in the cloud.
- Launch and manage instances.
- Supports multiple operating systems.

##### Use Cases

- Web hosting
- Enterprise applications
- Development environments

---

#### AWS Lambda

- Serverless compute service.
- Runs code without managing servers.
- Charges only for execution time.

##### Use Cases

- Automation
- Event-driven applications
- Backend APIs

---

#### Amazon ECS (Elastic Container Service)

- Container orchestration service.
- Runs Docker containers.

##### Use Cases

- Microservices
- Containerized applications

---

#### Amazon EKS (Elastic Kubernetes Service)

- Managed Kubernetes service.

##### Use Cases

- Kubernetes deployments
- Container management

---

# 2. Storage Services

### Purpose

Store and retrieve data securely and reliably.

### Common Services

#### Amazon S3 (Simple Storage Service)

- Object storage service.
- Highly durable and scalable.

##### Features

- Unlimited storage
- Data backup
- Static website hosting

##### Use Cases

- File storage
- Backup
- Media hosting

---

#### Amazon EBS (Elastic Block Store)

- Block storage for EC2 instances.

##### Use Cases

- Databases
- Operating system disks

---

#### Amazon EFS (Elastic File System)

- Managed file storage service.

##### Use Cases

- Shared file storage
- Linux workloads

---

#### Amazon S3 Glacier

- Low-cost archival storage.

##### Use Cases

- Long-term backups
- Compliance archives

---

# 3. Networking and Content Delivery

### Purpose

Connect resources and deliver content efficiently.

### Common Services

#### Amazon VPC (Virtual Private Cloud)

- Creates isolated private networks in AWS.

##### Features

- Subnets
- Route tables
- Security groups

---

#### Elastic Load Balancer (ELB)

- Distributes traffic across multiple servers.

##### Benefits

- High availability
- Fault tolerance

---

#### Amazon Route 53

- Scalable DNS service.

##### Functions

- Domain registration
- DNS management
- Traffic routing

---

#### Amazon CloudFront

- Content Delivery Network (CDN).

##### Benefits

- Faster content delivery
- Reduced latency

---

# 4. Database Services

### Purpose

Store, manage, and retrieve structured or unstructured data.

### Common Services

#### Amazon RDS (Relational Database Service)

Managed relational databases such as:

- MySQL
- PostgreSQL
- MariaDB
- Oracle
- SQL Server

##### Benefits

- Automated backups
- Easy scaling
- Managed maintenance

---

#### Amazon DynamoDB

- Fully managed NoSQL database.

##### Features

- High performance
- Serverless architecture

---

#### Amazon Aurora

- High-performance relational database.

##### Compatible With

- MySQL
- PostgreSQL

---

# 5. Security, Identity, and Compliance

### Purpose

Protect AWS resources and control access.

### Common Services

#### AWS IAM (Identity and Access Management)

##### Functions

- User management
- Role management
- Permission control

---

#### AWS Organizations

##### Functions

- Manage multiple AWS accounts
- Centralized governance

---

#### AWS Shield

##### Purpose

Protects against DDoS attacks.

---

#### AWS WAF (Web Application Firewall)

##### Purpose

Protect web applications from common attacks.

---

# 6. Management and Governance

### Purpose

Monitor, manage, and govern AWS environments.

### Common Services

#### Amazon CloudWatch

##### Functions

- Monitoring
- Metrics collection
- Log analysis
- Alerting

---

#### AWS CloudTrail

##### Functions

- Records AWS API activity
- Tracks user actions

---

#### AWS Config

##### Functions

- Resource inventory
- Configuration tracking

---

# 7. Analytics Services

### Purpose

Process and analyze data.

### Common Services

#### Amazon Athena

- Query data stored in S3 using SQL.

---

#### Amazon Redshift

- Data warehouse service.

---

#### AWS Glue

- Data integration and ETL service.

---

# 8. Machine Learning and AI Services

### Purpose

Build and deploy AI/ML applications.

### Common Services

#### Amazon SageMaker

##### Functions

- Build ML models
- Train ML models
- Deploy ML models

---

#### Amazon Rekognition

##### Functions

- Image analysis
- Facial recognition
- Object detection

---

#### Amazon Comprehend

##### Functions

- Natural language processing
- Sentiment analysis

---

# AWS Management Console

## Definition

The AWS Management Console is a web-based interface used to access and manage AWS services.

### Features

- Graphical User Interface (GUI)
- Easy resource management
- Service dashboards
- Monitoring tools

---

## Benefits

- Beginner-friendly
- Centralized management
- Quick service access
- Visual monitoring

---

# AWS Service Category Overview

| Category | Purpose | Examples |
|-----------|----------|----------|
| Compute | Run applications | EC2, Lambda, ECS, EKS |
| Storage | Store data | S3, EBS, EFS, Glacier |
| Networking | Connect resources | VPC, Route 53, CloudFront |
| Database | Manage data | RDS, DynamoDB, Aurora |
| Security | Control access | IAM, WAF, Shield |
| Management | Monitor resources | CloudWatch, CloudTrail |
| Analytics | Analyze data | Athena, Redshift |
| AI/ML | Machine Learning | SageMaker, Rekognition |

---

# Key Takeaways

## AWS Services

- AWS provides hundreds of cloud services.
- Services are organized into categories.

---

## Compute Services

- Provide processing power.
- Examples: EC2, Lambda, ECS.

---

## Storage Services

- Store and retrieve data.
- Examples: S3, EBS, Glacier.

---

## Networking Services

- Connect resources securely.
- Examples: VPC, Route 53, CloudFront.

---

## Database Services

- Manage structured and unstructured data.
- Examples: RDS, DynamoDB, Aurora.

---

## Security Services

- Manage access and protect resources.
- Examples: IAM, WAF, Shield.

---

## AWS Management Console

- Web-based interface.
- Used to create, manage, and monitor AWS resources.

---

# Exam / Interview Questions

### Q1. What are the three major AWS service categories?

**Answer:** Compute, Storage, and Networking.

---

### Q2. Which AWS service provides virtual servers?

**Answer:** Amazon EC2.

---

### Q3. Which AWS service provides object storage?

**Answer:** Amazon S3.

---

### Q4. Which AWS service is serverless?

**Answer:** AWS Lambda.

---

### Q5. Which AWS service manages user permissions?

**Answer:** AWS IAM.

---

### Q6. Which AWS service provides DNS management?

**Answer:** Amazon Route 53.

---

### Q7. Which AWS service is a managed relational database?

**Answer:** Amazon RDS.

---

### Q8. What is the purpose of Amazon CloudWatch?

**Answer:** Monitoring resources, logs, and metrics.

---

### Q9. Which AWS service records API activity?

**Answer:** AWS CloudTrail.

---

### Q10. What is the AWS Management Console?

**Answer:** A web-based interface used to access and manage AWS services.
