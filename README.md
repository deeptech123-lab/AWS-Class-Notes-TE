# AWS Class Notes — Day 1

# Topic
- On-Premises Data Centers
- Why Cloud Computing
- Cloud Computing Providers
- Types of Cloud Computing

---

# 1. Introduction to Traditional IT Infrastructure (On-Premises Data Centers)

## What is an On-Premises Data Center?

An **On-Premises (On-Prem)** Data Center is a physical infrastructure where an organization hosts and manages its own:

- Servers
- Storage devices
- Networking equipment
- Applications
- Databases
- Security systems

inside its own office or dedicated facility.

---

# 2. Components of an On-Prem Data Center

## Physical Infrastructure
- Server racks
- Cooling systems
- Power supply & UPS
- Cabling
- Fire protection systems

## Networking
- Routers
- Switches
- Firewalls
- Load balancers

## Storage
- HDD/SSD storage arrays
- Backup systems
- SAN/NAS

## Compute
- Physical servers
- Virtual machines

---

# 3. Problems with Traditional On-Prem Infrastructure

## High Initial Investment (CAPEX)
Organizations must purchase:
- Servers
- Storage
- Networking devices
- Software licenses

before even starting operations.

---

## Maintenance Overhead
Need dedicated teams for:
- Hardware maintenance
- Security patches
- Monitoring
- Power & cooling management

---

## Scalability Issues
If traffic increases suddenly:
- Need to buy new hardware
- Setup takes weeks/months

---

## Disaster Recovery Challenges
- Hardware failures
- Natural disasters
- Data loss risks

require expensive backup solutions.

---

## Limited Flexibility
Resources remain underutilized during low traffic periods.

---

# 4. What is Cloud Computing?

## Definition

Cloud Computing is the delivery of:
- Computing power
- Storage
- Networking
- Databases
- Applications

over the internet on a **pay-as-you-go** model.

Instead of owning hardware, organizations rent resources from cloud providers.

---

# 5. Why Cloud Computing?

## 1. Cost Optimization
- No upfront infrastructure cost
- Pay only for what you use

---

## 2. Scalability
Resources can scale:
- Up (Vertical Scaling)
- Out (Horizontal Scaling)

within minutes.

---

## 3. High Availability
Cloud providers offer:
- Multiple regions
- Availability Zones
- Backup systems

---

## 4. Faster Deployment
Infrastructure can be created in minutes using:
- AWS Console
- CLI
- Terraform
- CloudFormation

---

## 5. Security
Cloud providers provide:
- Encryption
- IAM
- Security monitoring
- Compliance certifications

---

## 6. Global Reach
Applications can be deployed closer to users worldwide.

---

# 6. Major Cloud Computing Providers in the Market

## 1. Amazon Web Services (AWS)

### Features
- Largest cloud provider
- Huge service portfolio
- Strong global infrastructure

### Popular Services
- EC2
- S3
- RDS
- Lambda
- VPC

---

## 2. Microsoft Azure

### Features
- Strong enterprise integration
- Best for Windows environments

### Popular Services
- Virtual Machines
- Azure Blob Storage
- Azure Active Directory

---

## 3. Google Cloud Platform (GCP)

### Features
- Strong in AI/ML and Kubernetes
- Excellent data analytics services

### Popular Services
- Compute Engine
- GKE
- BigQuery

---

## 4. Oracle Cloud Infrastructure (OCI)

### Features
- Strong database services
- Enterprise workloads

---

## 5. IBM Cloud

### Features
- Hybrid cloud solutions
- Enterprise integrations

---

# 7. Types of Cloud Computing

## 1. Public Cloud

Infrastructure is owned and managed by third-party cloud providers.

### Examples
- AWS
- Azure
- GCP

### Advantages
- Cost-effective
- Highly scalable
- Easy deployment

### Use Cases
- Startups
- Web applications
- Testing environments

---

## 2. Private Cloud

Infrastructure is dedicated to a single organization.

### Advantages
- More control
- Better customization
- Higher security

### Disadvantages
- Expensive
- Requires management

### Use Cases
- Banking
- Government
- Healthcare

---

## 3. Hybrid Cloud

Combination of:
- Public Cloud
- Private Cloud

Data and applications can move between both.

### Advantages
- Flexibility
- Better disaster recovery
- Compliance support

### Use Cases
- Enterprises migrating gradually to cloud

---

## 4. Multi-Cloud

Using multiple cloud providers simultaneously.

### Example
- AWS for compute
- Azure for identity
- GCP for analytics

### Advantages
- Avoid vendor lock-in
- Best service selection
- High redundancy

---

# 8. Cloud Service Models

## IaaS — Infrastructure as a Service
Provides:
- Virtual machines
- Storage
- Networking

### Example
- AWS EC2

---

## PaaS — Platform as a Service
Provides:
- Runtime environment
- Development platform

### Example
- AWS Elastic Beanstalk

---

## SaaS — Software as a Service
Software delivered over internet.

### Examples
- Gmail
- Zoom
- Microsoft 365

---

# 9. Real-Time Examples

## Netflix
Uses AWS for:
- Streaming
- Scalability
- Global content delivery

---

## Swiggy / Zomato
Use cloud for:
- Real-time order processing
- Traffic scaling during peak hours

---

## Banking Applications
Use hybrid cloud for:
- Security
- Compliance
- Disaster recovery

---

# 10. Interview Questions

## Basic Questions
1. What is cloud computing?
2. Difference between On-Prem and Cloud?
3. What are the advantages of cloud computing?
4. What is scalability?
5. What are Availability Zones?

---

## Intermediate Questions
1. Difference between Public and Private Cloud?
2. What is Hybrid Cloud?
3. Explain IaaS, PaaS, SaaS.
4. Why do companies migrate to cloud?
5. What is pay-as-you-go pricing?

---

# 11. Practical Demonstration Ideas

## Demo 1
Show how difficult physical infrastructure setup is compared to cloud provisioning.

---

## Demo 2
Create:
- EC2 instance
- S3 bucket

within minutes to demonstrate cloud agility.

---

# 12. Key Takeaways

- Traditional infrastructure is expensive and difficult to scale.
- Cloud computing provides flexibility, scalability, and cost optimization.
- AWS is the leading cloud provider.
- Organizations choose different cloud types based on business needs.
- Cloud is transforming modern IT infrastructure globally.

---

# Homework / Assignment

## Task 1
Research:
- AWS Regions
- Availability Zones

---

## Task 2
Create a Free Tier AWS account.

---

## Task 3
Compare:
- AWS
- Azure
- GCP

based on:
- Pricing
- Services
- Popularity
- Use cases
