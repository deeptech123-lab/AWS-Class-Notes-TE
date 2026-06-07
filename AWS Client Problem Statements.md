# AWS Client Problem Statements

## Purpose

This document contains real-world client requirements and business problems that can be solved using AWS services.

These scenarios help students learn:

* AWS Architecture Design
* Solution Architecture
* High Availability
* Scalability
* Security
* Cost Optimization
* Disaster Recovery

---

# Problem Statement 1

## Company Website Frequently Goes Down During Sales

### Client Requirement

An e-commerce company hosts its website on a single server.

During festival sales:

* Website becomes slow
* Users cannot place orders
* Revenue loss occurs

### Challenges

* Single Point of Failure
* No Load Balancing
* No Auto Scaling

### AWS Services Expected

* EC2
* ALB
* Auto Scaling
* CloudWatch

### Solution Goal

Design a highly available architecture that automatically scales during high traffic.

---

# Problem Statement 2

## Global Users Experiencing Slow Website Performance

### Client Requirement

The application is hosted in Mumbai.

Users from:

* USA
* Europe
* Australia

experience high latency.

### Challenges

* Long distance requests
* Slow content delivery

### AWS Services Expected

* CloudFront
* S3
* Route 53

### Solution Goal

Deliver content from the nearest AWS location.

---

# Problem Statement 3

## Secure Database Deployment

### Client Requirement

A banking application stores customer information.

Database should:

* Not be publicly accessible
* Be highly available
* Be automatically backed up

### AWS Services Expected

* RDS
* VPC
* Private Subnet
* Security Groups

### Solution Goal

Design a secure and highly available database architecture.

---

# Problem Statement 4

## Automatic Image Processing

### Client Requirement

Whenever a customer uploads an image:

* Resize image
* Generate thumbnail
* Store processed image

without manual intervention.

### AWS Services Expected

* S3
* Lambda

### Solution Goal

Create an event-driven serverless architecture.

---

# Problem Statement 5

## Disaster Recovery Requirement

### Client Requirement

The client requires:

* Daily backups
* Quick recovery from failures
* Minimal downtime

### AWS Services Expected

* S3
* RDS Snapshots
* Multi-AZ
* Cross Region Replication

### Solution Goal

Implement a disaster recovery strategy.

---

# Problem Statement 6

## Audit and Compliance Requirement

### Client Requirement

Security team wants answers for:

* Who created resources?
* Who deleted resources?
* When changes happened?

### AWS Services Expected

* CloudTrail
* CloudWatch

### Solution Goal

Implement complete auditing and tracking.

---

# Problem Statement 7

## Cost Optimization

### Client Requirement

AWS bill increased significantly.

Management wants:

* Reduced costs
* Same performance

### AWS Services Expected

* EC2 Rightsizing
* Auto Scaling
* S3 Lifecycle Policies
* Cost Explorer

### Solution Goal

Reduce cloud costs without affecting users.

---

# Problem Statement 8

## Highly Available Web Application

### Client Requirement

Application should remain available even if:

* One EC2 fails
* One Availability Zone fails

### AWS Services Expected

* Multi-AZ Deployment
* ALB
* Auto Scaling

### Solution Goal

Achieve high availability.

---

# Problem Statement 9

## Secure Access to AWS Resources

### Client Requirement

Developers need:

* Access only to EC2
* No access to billing
* No access to production databases

### AWS Services Expected

* IAM Users
* IAM Groups
* IAM Policies

### Solution Goal

Implement least privilege access.

---

# Problem Statement 10

## Domain Management

### Client Requirement

Client owns:

example.com

Requirements:

* Domain registration
* DNS management
* Failover support

### AWS Services Expected

* Route 53

### Solution Goal

Create reliable DNS architecture.

---

# Problem Statement 11

## Log Monitoring and Alerts

### Client Requirement

Operations team wants alerts when:

* CPU > 80%
* Disk Usage > 85%
* Application Errors Increase

### AWS Services Expected

* CloudWatch Metrics
* CloudWatch Logs
* CloudWatch Alarms

### Solution Goal

Proactive monitoring and alerting.

---

# Problem Statement 12

## Static Website Hosting

### Client Requirement

Company wants to host:

* HTML
* CSS
* JavaScript

website at minimal cost.

### AWS Services Expected

* S3
* CloudFront
* Route 53

### Solution Goal

Build a serverless website hosting architecture.

---

# Problem Statement 13

## Application Database Scaling

### Client Requirement

Application receives millions of read requests.

Database performance is degrading.

### AWS Services Expected

* RDS Read Replicas

### Solution Goal

Improve read performance.

---

# Problem Statement 14

## Secure Private Access to AWS Services

### Client Requirement

Private EC2 instances need access to S3.

Traffic should not traverse the internet.

### AWS Services Expected

* VPC Endpoint
* S3

### Solution Goal

Provide private connectivity.

---

# Problem Statement 15

## Migration from On-Premises to AWS

### Client Requirement

Current Environment:

* Physical Servers
* Local Database
* Manual Scaling

Requirements:

* High Availability
* Elasticity
* Reduced Infrastructure Cost

### AWS Services Expected

* VPC
* EC2
* ALB
* Auto Scaling
* RDS

### Solution Goal

Migrate workloads to AWS.

---

# Capstone Problem Statement

## Design an AWS Architecture for an E-Commerce Company

### Business Requirements

* Global Users
* Secure Login
* Product Catalog
* Order Processing
* Payment Transactions
* High Availability
* Disaster Recovery
* Monitoring
* Auditing

### Expected AWS Services

* Route 53
* CloudFront
* S3
* ALB
* EC2
* Auto Scaling
* RDS
* CloudWatch
* CloudTrail

### Deliverables

Students should explain:

1. Architecture Diagram
2. Security Design
3. High Availability Strategy
4. Scaling Strategy
5. Monitoring Setup
6. Disaster Recovery Plan
7. Cost Optimization Techniques

---

# Bonus Challenge

Design Netflix on AWS

Requirements:

* Global Video Delivery
* Millions of Users
* High Availability
* Content Storage
* Monitoring

Expected Services:

* CloudFront
* S3
* EC2
* Auto Scaling
* Route 53
* CloudWatch

Explain how each service contributes to the solution.
