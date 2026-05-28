# AWS Class Notes — Day 1

# Topic

* On-Premises Data Centers
* Why Cloud Computing
* Cloud Computing Providers
* Types of Cloud Computing
* AWS IAM
* AWS EC2
* AWS VPC
* AWS Pricing
* Load Balancing & Auto Scaling

---

# 1. Introduction to Traditional IT Infrastructure (On-Premises Data Centers)

## What is an On-Premises Data Center?

An **On-Premises (On-Prem)** Data Center is a physical infrastructure where an organization hosts and manages its own:

* Servers
* Storage devices
* Networking equipment
* Applications
* Databases
* Security systems

inside its own office or dedicated facility.

---

# 2. Components of an On-Prem Data Center

## Physical Infrastructure

* Server racks
* Cooling systems
* Power supply & UPS
* Cabling
* Fire protection systems

## Networking

* Routers
* Switches
* Firewalls
* Load balancers

## Storage

* HDD/SSD storage arrays
* Backup systems
* SAN/NAS

## Compute

* Physical servers
* Virtual machines

---

# 3. Problems with Traditional On-Prem Infrastructure

## High Initial Investment (CAPEX)

Organizations must purchase:

* Servers
* Storage
* Networking devices
* Software licenses

before even starting operations.

---

## Maintenance Overhead

Need dedicated teams for:

* Hardware maintenance
* Security patches
* Monitoring
* Power & cooling management

---

## Scalability Issues

If traffic increases suddenly:

* Need to buy new hardware
* Setup takes weeks/months

---

## Disaster Recovery Challenges

* Hardware failures
* Natural disasters
* Data loss risks

require expensive backup solutions.

---

## Limited Flexibility

Resources remain underutilized during low traffic periods.

---

# 4. What is Cloud Computing?

## Definition

Cloud Computing is the delivery of:

* Computing power
* Storage
* Networking
* Databases
* Applications

over the internet on a **pay-as-you-go** model.

Instead of owning hardware, organizations rent resources from cloud providers.

---

# 5. Why Cloud Computing?

## 1. Cost Optimization

* No upfront infrastructure cost
* Pay only for what you use

---

## 2. Scalability

Resources can scale:

* Up (Vertical Scaling)
* Out (Horizontal Scaling)

within minutes.

---

## 3. High Availability

Cloud providers offer:

* Multiple regions
* Availability Zones
* Backup systems

---

## 4. Faster Deployment

Infrastructure can be created in minutes using:

* AWS Console
* CLI
* Terraform
* CloudFormation

---

## 5. Security

Cloud providers provide:

* Encryption
* IAM
* Security monitoring
* Compliance certifications

---

## 6. Global Reach

Applications can be deployed closer to users worldwide.

---

# 6. Major Cloud Computing Providers in the Market

## 1. Amazon Web Services (AWS)

### Features

* Largest cloud provider
* Huge service portfolio
* Strong global infrastructure

### Popular Services

* EC2
* S3
* RDS
* Lambda
* VPC

---

## 2. Microsoft Azure

### Features

* Strong enterprise integration
* Best for Windows environments

### Popular Services

* Virtual Machines
* Azure Blob Storage
* Azure Active Directory

---

## 3. Google Cloud Platform (GCP)

### Features

* Strong in AI/ML and Kubernetes
* Excellent data analytics services

### Popular Services

* Compute Engine
* GKE
* BigQuery

---

## 4. Oracle Cloud Infrastructure (OCI)

### Features

* Strong database services
* Enterprise workloads

---

## 5. IBM Cloud

### Features

* Hybrid cloud solutions
* Enterprise integrations

---

# 7. Types of Cloud Computing

## 1. Public Cloud

Infrastructure is owned and managed by third-party cloud providers.

### Examples

* AWS
* Azure
* GCP

### Advantages

* Cost-effective
* Highly scalable
* Easy deployment

### Use Cases

* Startups
* Web applications
* Testing environments

---

## 2. Private Cloud

Infrastructure is dedicated to a single organization.

### Advantages

* More control
* Better customization
* Higher security

### Disadvantages

* Expensive
* Requires management

### Use Cases

* Banking
* Government
* Healthcare

---

## 3. Hybrid Cloud

Combination of:

* Public Cloud
* Private Cloud

Data and applications can move between both.

### Advantages

* Flexibility
* Better disaster recovery
* Compliance support

### Use Cases

* Enterprises migrating gradually to cloud

---

## 4. Multi-Cloud

Using multiple cloud providers simultaneously.

### Example

* AWS for compute
* Azure for identity
* GCP for analytics

### Advantages

* Avoid vendor lock-in
* Best service selection
* High redundancy

---

# 8. Cloud Service Models

## IaaS — Infrastructure as a Service

Provides:

* Virtual machines
* Storage
* Networking

### Example

* AWS EC2

---

## PaaS — Platform as a Service

Provides:

* Runtime environment
* Development platform

### Example

* AWS Elastic Beanstalk

---

## SaaS — Software as a Service

Software delivered over internet.

### Examples

* Gmail
* Zoom
* Microsoft 365

---

# 9. AWS IAM (Identity and Access Management)

## What is IAM?

AWS IAM is a service used to securely control access to AWS resources.

Using IAM, organizations can:

* Create users
* Create groups
* Assign permissions
* Manage authentication and authorization

---

## IAM Users

An IAM User represents a person or application that interacts with AWS.

### Examples

* DevOps Engineer
* Developer
* Automation scripts
* CI/CD pipelines

### Features

* Username and password
* Access keys
* MFA support
* Permission-based access

---

## IAM User Groups

IAM Groups are collections of IAM users.

### Example Groups

* Developers
* DevOps
* QA Team
* Security Team
* Admins

### Advantages

* Easier permission management
* Assign policies to groups instead of individual users

---

## IAM Roles

IAM Roles provide temporary permissions to AWS services or users.

### Common Use Cases

* EC2 accessing S3
* Lambda accessing DynamoDB
* Cross-account access
* ECS task permissions

### Key Point

Roles do not have permanent credentials.

---

## IAM Policies

Policies are JSON documents that define permissions.

### Types of Policies

#### 1. AWS Managed Policies

Predefined by AWS.

Example:

* AdministratorAccess
* AmazonS3ReadOnlyAccess

#### 2. Customer Managed Policies

Created and managed by organizations.

#### 3. Inline Policies

Directly attached to a single user, group, or role.

---

## IAM Best Practices

* Enable MFA for all users
* Avoid using root account daily
* Use roles instead of access keys where possible
* Follow least privilege principle
* Rotate access keys regularly

---

# 10. AWS EC2 (Elastic Compute Cloud)

## What is EC2?

Amazon EC2 is a virtual server service in AWS used to run applications in the cloud.

EC2 provides scalable compute capacity.

---

## EC2 Components

### 1. AMI (Amazon Machine Image)

An AMI is a template used to launch EC2 instances.

### AMI Includes

* Operating system
* Application server
* Software packages
* Configuration settings

### Common AMIs

* Amazon Linux
* Ubuntu
* Red Hat
* Windows Server

---

### 2. Instance Types

Instance types define CPU, memory, storage, and networking capacity.

### Common Families

#### General Purpose

* t2
* t3
* t4g
* m5

Use Case:

* Web applications
* Small databases

#### Compute Optimized

* c5
* c6g

Use Case:

* High-performance applications
* Gaming servers
* Batch processing

#### Memory Optimized

* r5
* x1

Use Case:

* In-memory databases
* Big data analytics

#### Storage Optimized

* i3
* d2

Use Case:

* Data warehousing
* High IOPS workloads

---

### 3. EBS (Elastic Block Store)

EBS provides persistent block storage for EC2.

### Features

* Persistent storage
* Snapshots
* Encryption support
* High availability

### Types

* gp3 (General Purpose SSD)
* io1/io2 (Provisioned IOPS SSD)
* st1 (Throughput Optimized HDD)
* sc1 (Cold HDD)

---

### 4. Security Groups

Security Groups act as virtual firewalls for EC2 instances.

### Characteristics

* Stateful
* Allow rules only
* Control inbound and outbound traffic

---

### 5. Key Pairs

Used for securely connecting to Linux EC2 instances using SSH.

---

## EC2 Pricing Models

### 1. On-Demand

* Pay per usage
* No long-term commitment

### 2. Reserved Instances

* 1-year or 3-year commitment
* Lower cost

### 3. Spot Instances

* Unused AWS capacity
* Very low cost
* Can terminate anytime

### 4. Savings Plans

* Flexible pricing model
* Reduced pricing commitment

---

# 11. Elastic Load Balancer (ELB)

## What is Load Balancing?

Load balancing distributes incoming traffic across multiple servers.

### Benefits

* High availability
* Fault tolerance
* Better performance
* Scalability

---

## Types of Load Balancers

### 1. Application Load Balancer (ALB)

Works at Layer 7 (HTTP/HTTPS).

### Features

* Path-based routing
* Host-based routing
* Microservices support

### Example

* Route /api traffic to backend API servers
* Route /images to image servers

---

### 2. Network Load Balancer (NLB)

Works at Layer 4 (TCP/UDP).

### Features

* Ultra-high performance
* Low latency
* Static IP support

---

### 3. Gateway Load Balancer (GWLB)

Used for deploying virtual appliances.

### Use Cases

* Firewalls
* Intrusion detection systems

---

# 12. Auto Scaling

## What is Auto Scaling?

Auto Scaling automatically adjusts the number of EC2 instances based on demand.

---

## Benefits

* Cost optimization
* High availability
* Automatic scaling
* Improved fault tolerance

---

## Scaling Types

### Dynamic Scaling

Automatically scales based on:

* CPU utilization
* Memory usage
* Network traffic

### Scheduled Scaling

Scale resources based on predefined schedules.

Example:

* Increase instances during office hours.

---

## Auto Scaling Components

* Launch Templates
* Auto Scaling Groups (ASG)
* Scaling Policies
* CloudWatch Metrics

---

# 13. AWS VPC (Virtual Private Cloud)

## What is VPC?

Amazon VPC allows users to create isolated virtual networks inside AWS.

---

## Core Components of VPC

### 1. CIDR Block

Defines the IP address range of the VPC.

Example:

* 10.0.0.0/16

---

### 2. Subnets

Subnets divide the VPC into smaller networks.

#### Public Subnet

* Connected to Internet Gateway
* Hosts public-facing resources

#### Private Subnet

* No direct internet access
* Hosts databases/internal applications

---

### 3. Route Tables

Control traffic routing inside VPC.

### Example Routes

* Local VPC communication
* Internet Gateway routing
* NAT Gateway routing

---

### 4. Internet Gateway (IGW)

Allows internet access for public subnets.

---

### 5. NAT Gateway

Allows private subnet instances to access the internet securely.

### Example

* Download software updates from private subnet

---

### 6. Network ACL (NACL)

Acts as a subnet-level firewall.

### Characteristics

* Stateless
* Supports allow and deny rules

---

### 7. Security Groups

Acts as an instance-level firewall.

### Characteristics

* Stateful
* Allow rules only

---

### 8. VPC Peering

Connects two VPCs privately.

### Use Cases

* Communication between applications in different VPCs

---

### 9. Transit Gateway

Acts as a central hub connecting multiple VPCs and on-premises networks.

### Benefits

* Simplified network architecture
* Centralized routing

---

### 10. VPC Endpoints

Allow private connectivity to AWS services without internet.

### Types

* Gateway Endpoint
* Interface Endpoint

### Examples

* S3 Gateway Endpoint
* Secrets Manager Interface Endpoint

---

### 11. Site-to-Site VPN

Secure connection between on-premises data center and AWS over internet.

---

### 12. Direct Connect

Dedicated private network connection between on-premises and AWS.

### Benefits

* Low latency
* High bandwidth
* Stable connection

---

# 14. Real-Time AWS Architecture Example

## Example: E-Commerce Application

### Frontend

* Hosted on EC2 or S3 + CloudFront

### Load Balancer

* ALB distributes traffic

### Auto Scaling

* Automatically adds EC2 instances during high traffic

### Database

* RDS in private subnet

### Storage

* Product images stored in S3

### Networking

* VPC with public and private subnets

### Security

* IAM roles
* Security Groups
* NACLs

---

# 15. Real-Time Examples

## Netflix

Uses AWS for:

* Streaming
* Scalability
* Global content delivery

---

## Swiggy / Zomato

Use cloud for:

* Real-time order processing
* Traffic scaling during peak hours

---

## Banking Applications

Use hybrid cloud for:

* Security
* Compliance
* Disaster recovery

---

# 16. Interview Questions

## Basic Questions

1. What is cloud computing?
2. Difference between On-Prem and Cloud?
3. What are the advantages of cloud computing?
4. What is scalability?
5. What are Availability Zones?
6. What is IAM?
7. Difference between Security Group and NACL?
8. What is an AMI?
9. Difference between ALB and NLB?
10. What is Auto Scaling?

---

## Intermediate Questions

1. Difference between Public and Private Cloud?
2. What is Hybrid Cloud?
3. Explain IaaS, PaaS, SaaS.
4. Why do companies migrate to cloud?
5. What is pay-as-you-go pricing?
6. Difference between IAM Role and IAM User?
7. What is VPC Peering?
8. What is a NAT Gateway?
9. Explain EC2 pricing models.
10. Difference between Gateway Endpoint and Interface Endpoint?

---

# 17. Practical Demonstration Ideas

## Demo 1

Show how difficult physical infrastructure setup is compared to cloud provisioning.

---

## Demo 2

Create:

* EC2 instance
* S3 bucket

within minutes to demonstrate cloud agility.

---

## Demo 3

Create:

* VPC
* Public subnet
* Private subnet
* NAT Gateway
* EC2 instance

and demonstrate internet access.

---

## Demo 4

Create:

* Auto Scaling Group
* Application Load Balancer

and simulate scaling using CPU load.

---

# 18. Key Takeaways

* Traditional infrastructure is expensive and difficult to scale.
* Cloud computing provides flexibility, scalability, and cost optimization.
* AWS is the leading cloud provider.
* IAM secures AWS resources.
* EC2 provides scalable compute infrastructure.
* VPC provides secure network isolation.
* Load balancers and Auto Scaling improve availability and performance.
* Organizations choose different cloud types based on business needs.
* Cloud is transforming modern IT infrastructure globally.

---
