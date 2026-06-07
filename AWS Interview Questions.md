# AWS Interview Questions

## Topics Covered

* IAM
* EC2
* VPC
* ELB
* Auto Scaling
* S3
* CloudFront
* Route 53
* Lambda
* RDS
* CloudWatch
* CloudTrail

---

# Basic Level Questions

## Cloud Fundamentals

1. What is Cloud Computing?
2. What are the benefits of Cloud Computing?
3. Difference between On-Premises and Cloud?
4. What is AWS?
5. What are Availability Zones?
6. What are AWS Regions?
7. What is Scalability?
8. What is High Availability?
9. What is Fault Tolerance?
10. What is Elasticity?

---

## IAM

1. What is IAM?
2. What is an IAM User?
3. What is an IAM Group?
4. What is an IAM Role?
5. What is an IAM Policy?
6. Difference between User and Role?
7. What is MFA?
8. Why should root account not be used daily?

---

## EC2

1. What is EC2?
2. What is an AMI?
3. What is an Instance Type?
4. What is EBS?
5. What is a Security Group?
6. What are Key Pairs?
7. What is the difference between Stop and Terminate?
8. What are EC2 Pricing Models?

---

## VPC

1. What is VPC?
2. What is a Subnet?
3. Difference between Public and Private Subnet?
4. What is CIDR?
5. What is an Internet Gateway?
6. What is a NAT Gateway?
7. What is a Route Table?
8. Difference between Security Group and NACL?

---

## Load Balancer & Auto Scaling

1. What is a Load Balancer?
2. Why do we need Load Balancing?
3. What is ALB?
4. What is NLB?
5. What is Auto Scaling?
6. What are Auto Scaling Groups?
7. What are Scaling Policies?

---

## S3

1. What is S3?
2. What is a Bucket?
3. What is an Object?
4. What is Versioning?
5. What is Lifecycle Management?
6. What are S3 Storage Classes?
7. Difference between S3 Standard and Glacier?

---

## CloudFront

1. What is CDN?
2. What is CloudFront?
3. What is an Edge Location?
4. What is an Origin?
5. Why use CloudFront?

---

## Route 53

1. What is DNS?
2. What is Route 53?
3. What is DNS Resolution?
4. What are Routing Policies?
5. What is Failover Routing?

---

## Lambda

1. What is Lambda?
2. What is Serverless Computing?
3. What are Lambda Triggers?
4. What is a Handler?
5. What is Cold Start?
6. What is the maximum execution time of Lambda?

---

## RDS

1. What is RDS?
2. What databases are supported in RDS?
3. What is Multi-AZ?
4. What is Read Replica?
5. What is an RDS Endpoint?

---

## CloudWatch

1. What is CloudWatch?
2. What are Metrics?
3. What are Alarms?
4. What are Dashboards?
5. What are Logs?

---

## CloudTrail

1. What is CloudTrail?
2. What information does CloudTrail capture?
3. Why is CloudTrail used?
4. Difference between CloudWatch and CloudTrail?

---

# Intermediate Level Questions

## IAM

1. Difference between AWS Managed Policy and Customer Managed Policy?
2. What is the Principle of Least Privilege?
3. How does Cross-Account Access work?
4. How would you provide S3 access to EC2 without Access Keys?

---

## EC2

1. Difference between EBS and Instance Store?
2. Difference between gp3 and io2 volumes?
3. What happens when an EC2 instance is stopped?
4. How do Security Groups work?
5. How do you connect to a Linux EC2 instance?

---

## VPC

1. Explain VPC Peering.
2. What is Transit Gateway?
3. Difference between Stateful and Stateless Firewalls?
4. What are VPC Endpoints?
5. Difference between Gateway Endpoint and Interface Endpoint?
6. How does NAT Gateway work?

---

## ELB & Auto Scaling

1. Difference between ALB and NLB?
2. How does Auto Scaling work with CloudWatch?
3. What happens if an instance behind ALB becomes unhealthy?
4. Explain Target Groups.

---

## S3

1. How does Versioning help in recovery?
2. Explain S3 Lifecycle Policies.
3. What is Cross-Region Replication?
4. How do you secure an S3 bucket?
5. Difference between Bucket Policy and IAM Policy?

---

## CloudFront

1. How does CloudFront improve performance?
2. Explain Caching in CloudFront.
3. What happens on a Cache Miss?
4. How do CloudFront and S3 work together?

---

## Route 53

1. Difference between Weighted and Latency Routing?
2. How do Health Checks work?
3. What happens when the primary server fails?

---

## Lambda

1. Explain Lambda Execution Lifecycle.
2. What causes Cold Starts?
3. How does Lambda Scale?
4. Why is Lambda considered Stateless?
5. Difference between Lambda and EC2?

---

## RDS

1. Difference between Multi-AZ and Read Replica?
2. How does RDS backup work?
3. What is Automated Patching?
4. Why should RDS be placed in a Private Subnet?

---

## CloudWatch

1. How do CloudWatch Alarms work?
2. How can CloudWatch trigger Auto Scaling?
3. What are Custom Metrics?
4. How would you monitor application logs?

---

## CloudTrail

1. How would you investigate an accidental resource deletion?
2. Where are CloudTrail logs stored?
3. How does CloudTrail help in auditing?

---

# Scenario-Based Questions

## IAM

### Scenario 1

A developer needs access only to S3 buckets but should not be able to delete objects.

How would you configure IAM permissions?

---

### Scenario 2

An EC2 instance needs access to an S3 bucket.

Would you use Access Keys or IAM Roles? Why?

---

## EC2

### Scenario 1

An application is running on EC2 and CPU utilization constantly reaches 95%.

What would you do?

---

### Scenario 2

A production EC2 instance becomes unreachable.

What checks would you perform?

---

## VPC

### Scenario 1

You launched an EC2 instance in a public subnet but cannot access the internet.

What troubleshooting steps would you take?

---

### Scenario 2

Your application servers are in a private subnet and need internet access for updates.

How would you achieve this?

---

## ELB

### Scenario 1

One EC2 instance behind an ALB becomes unhealthy.

What happens next?

---

### Scenario 2

Traffic suddenly increases during a sale event.

How can ELB help?

---

## Auto Scaling

### Scenario 1

Traffic spikes every day between 9 AM and 11 AM.

Which Auto Scaling policy would you use?

---

### Scenario 2

CPU utilization exceeds 80% for 10 minutes.

How would Auto Scaling respond?

---

## S3

### Scenario 1

A user accidentally deletes a file from S3.

How can you recover it?

---

### Scenario 2

You need to archive logs for seven years at minimal cost.

Which storage class would you use?

---

## CloudFront

### Scenario 1

Users from Europe complain that your website is slow.

How would CloudFront help?

---

### Scenario 2

You update an image in S3 but users still see the old image.

Why is this happening?

---

## Route 53

### Scenario 1

Your primary application server goes down.

How can Route 53 automatically redirect traffic?

---

### Scenario 2

Users from India and the USA should connect to the nearest application server.

Which routing policy would you use?

---

## Lambda

### Scenario 1

Whenever a file is uploaded to S3, it should be processed automatically.

How would you design this solution?

---

### Scenario 2

A Lambda function is timing out.

How would you troubleshoot it?

---

## RDS

### Scenario 1

Your database server fails.

How does Multi-AZ help?

---

### Scenario 2

Application reads are very high but writes are low.

How would you improve performance?

---

## CloudWatch

### Scenario 1

CPU utilization exceeds 90%.

How would CloudWatch help?

---

### Scenario 2

The application team wants alerts whenever disk usage exceeds 85%.

How would you implement it?

---

## CloudTrail

### Scenario 1

An S3 bucket was deleted accidentally.

How would you identify who deleted it?

---

### Scenario 2

A security team wants a complete audit trail of AWS activity.

Which service would you use and why?

---

# Frequently Asked Real-Time Interview Questions

1. Explain your AWS architecture.
2. How do you secure AWS resources?
3. How do you design a highly available application?
4. Explain a production issue you resolved.
5. How would you migrate an application from On-Prem to AWS?
6. How would you reduce AWS costs?
7. How would you monitor a production application?
8. How would you troubleshoot a website outage?
9. How do you handle disaster recovery?
10. Explain a real-world architecture using Route 53, CloudFront, ALB, EC2, RDS, CloudWatch, and CloudTrail.

---

# Golden Scenario (Most Asked)

Design an E-Commerce Application on AWS:

User

↓

Route 53

↓

CloudFront

↓

Application Load Balancer

↓

Auto Scaling EC2 Instances

↓

RDS (Private Subnet)

↓

CloudWatch Monitoring

↓

CloudTrail Auditing

Explain:

* High Availability
* Security
* Scalability
* Monitoring
* Disaster Recovery

This single scenario covers 70–80% of AWS interview discussions for beginner and intermediate DevOps/Cloud Engineer roles.
