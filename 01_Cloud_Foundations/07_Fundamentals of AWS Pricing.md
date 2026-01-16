# Fundamentals of AWS Pricing

## Learning Objectives

After completing this lesson, you should be able to:

- Describe the AWS pricing model.
- Explain the advantages of AWS pricing.
- Describe the AWS Free Tier.
- Explain Total Cost of Ownership (TCO).
- Identify the purpose of the AWS Pricing Calculator.

---

# AWS Pricing Model

AWS follows a **Pay-As-You-Go** pricing model.

### Principle

You pay only for the resources you use without long-term commitments or large upfront investments.

### Benefits

- No large capital expenses
- Flexible resource usage
- Cost optimization
- Scalable pricing

---

# Three Fundamental Drivers of AWS Cost

AWS pricing is primarily based on:

1. Compute
2. Storage
3. Data Transfer

---

# 1. Compute Costs

## Definition

Compute refers to processing power used by applications.

### Examples

- Amazon EC2 Instances
- AWS Lambda
- Containers

### Pricing

- Charged by the second or hour
- Depends on:
  - Instance type
  - Instance size
  - Operating system
  - Usage duration

### Formula

```text
Compute Cost = Resource Used × Time Used
```

### Example

Running an EC2 instance for 10 hours incurs charges based on its hourly rate.

---

# 2. Storage Costs

## Definition

Storage refers to saving data in AWS services.

### Examples

- Amazon S3
- Amazon EBS
- Amazon EFS

### Pricing

Typically charged per:

```text
GB Stored per Month
```

### Example

If 100 GB of data is stored, charges are based on storage consumed.

---

# 3. Data Transfer Costs

## Definition

Data transfer refers to moving data into or out of AWS.

---

### Inbound Data Transfer

Data entering AWS.

```text
Usually Free
```

### Example

Uploading files from your computer to Amazon S3.

---

### Outbound Data Transfer

Data leaving AWS.

```text
Usually Charged
```

### Example

Downloading files from AWS to users.

---

### Important Note

In most cases:

- Inbound transfer = Free
- Transfer between AWS services in the same Region = Free
- Outbound transfer = Charged

---

# AWS Pricing Summary

| Cost Driver | Typical Pricing Method |
|------------|-----------------------|
| Compute | Per second / hour |
| Storage | Per GB |
| Data Transfer Out | Per GB |
| Data Transfer In | Usually Free |

---

# Advantages of AWS Pricing Model

## 1. Pay Only for What You Use

No need to purchase infrastructure in advance.

### Benefit

Reduces wasted resources.

---

## 2. No Large Upfront Costs

Traditional IT requires purchasing:

- Servers
- Storage devices
- Networking equipment

AWS eliminates most capital expenses.

---

## 3. Scalability

Resources can increase or decrease as needed.

### Benefit

Costs align with actual usage.

---

## 4. Cost Transparency

Users can monitor and track costs in real time.

### Benefit

Better financial planning.

---

## 5. Flexible Pricing Options

AWS provides multiple pricing models:

- On-Demand
- Reserved Instances
- Savings Plans
- Spot Instances

### Benefit

Choose the most cost-effective option.

---

# AWS Free Tier

## Definition

AWS Free Tier allows new users to explore AWS services at no cost within specified limits.

### Purpose

- Learn AWS
- Test services
- Build small applications

---

## Types of Free Tier Offers

### 1. Always Free

Certain services remain free within usage limits.

### Example

Limited AWS Lambda requests.

---

### 2. 12-Month Free Tier

Available for new AWS customers.

### Examples

- Amazon EC2
- Amazon S3
- Amazon RDS

---

### 3. Short-Term Trials

Temporary free access to specific AWS services.

### Example

30-day or 60-day service trials.

---

# Total Cost of Ownership (TCO)

## Definition

Total Cost of Ownership (TCO) is the complete cost of owning and operating IT infrastructure over time.

---

# Traditional Data Center Costs

## Hardware Costs

- Servers
- Storage
- Networking equipment

## Facility Costs

- Building space
- Racks

## Utilities

- Electricity
- Cooling systems

## Personnel Costs

- IT administrators
- Maintenance staff

## Upgrade Costs

- Hardware replacements
- Software upgrades

---

# AWS and TCO

Cloud computing reduces TCO because AWS manages:

- Physical infrastructure
- Hardware maintenance
- Power and cooling
- Networking infrastructure

### Result

Organizations focus more on business innovation and less on infrastructure management.

---

# Example of TCO Reduction

## Traditional Environment

```text
Buy Servers
+ Data Center Space
+ Electricity
+ Cooling
+ Maintenance
+ Staff
= High TCO
```

## AWS Environment

```text
Pay for Services Used
= Lower TCO
```

---

# AWS Pricing Calculator

## Definition

The AWS Pricing Calculator is a tool used to estimate AWS service costs before deployment.

### Purpose

- Budget planning
- Cost estimation
- Resource comparison

---

# What the Calculator Helps With

### Estimate

- EC2 costs
- Storage costs
- Database costs
- Networking costs

### Compare

- Different architectures
- Different instance types
- Different storage options

### Forecast

- Monthly costs
- Annual costs

---

# Benefits of AWS Pricing Calculator

- Accurate budgeting
- Better planning
- Cost optimization
- Reduced financial risk

---

# Cost Optimization Best Practices

## 1. Use Only Required Resources

Avoid overprovisioning.

---

## 2. Monitor Usage

Track spending regularly.

---

## 3. Delete Unused Resources

Remove unnecessary services.

---

## 4. Use AWS Free Tier

Learn and experiment at minimal cost.

---

## 5. Choose Appropriate Pricing Models

Select On-Demand, Reserved, or Spot pricing based on workload.

---

# Quick Revision

## Three AWS Cost Drivers

```text
Compute
Storage
Data Transfer
```

---

## Data Transfer Rules

```text
Inbound = Usually Free
Outbound = Usually Charged
```

---

## AWS Free Tier

Allows users to explore AWS services within free usage limits.

---

## TCO

Total Cost of Ownership = Complete lifetime cost of IT infrastructure.

---

## AWS Pricing Calculator

Tool used to estimate AWS costs before deployment.

---

# Exam Tips

### Remember the Cost Drivers

```text
CSD

C → Compute
S → Storage
D → Data Transfer
```

### Key Facts

- Compute → Charged per second/hour
- Storage → Charged per GB
- Inbound Data → Usually Free
- Outbound Data → Usually Charged

### Most Important Definitions

**AWS Pricing Model:** Pay only for what you use.

**TCO:** Total cost of owning and operating infrastructure.

**AWS Free Tier:** Free access to AWS services within defined limits.

**AWS Pricing Calculator:** Cost estimation tool for AWS services.

---

# Key Takeaways

- AWS pricing is based on actual resource consumption.
- The three primary cost drivers are Compute, Storage, and Data Transfer.
- Most inbound data transfers are free.
- AWS Free Tier allows users to learn and experiment with AWS services.
- TCO includes all costs associated with IT infrastructure.
- AWS Pricing Calculator helps estimate cloud costs before deployment.
- Pay-as-you-go pricing reduces upfront investments and improves flexibility.