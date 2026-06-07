# AWS Troubleshooting Guide

## Purpose

This guide helps identify, troubleshoot, and resolve common AWS issues encountered in real-world environments.

---

# Troubleshooting Methodology

Whenever an issue occurs:

1. Identify the problem
2. Verify AWS resource status
3. Check networking
4. Check security
5. Check logs
6. Check monitoring metrics
7. Verify application configuration
8. Implement fix
9. Validate solution

---

# EC2 Troubleshooting

## Problem: Unable to SSH into EC2

### Symptoms

```text
Connection Timed Out
```

or

```text
Permission Denied
```

### Checks

#### Security Group

Verify:

```text
Inbound Rule

SSH
Port: 22
Source: Your Public IP
```

---

#### Public IP

Verify EC2 has:

```text
Public IPv4 Address
```

---

#### Internet Gateway

Verify:

```text
VPC
↓
Internet Gateway Attached
```

---

#### Route Table

Verify route:

```text
0.0.0.0/0
↓
Internet Gateway
```

---

#### Key Pair

Verify correct:

```text
.pem
```

file is being used.

---

### Resolution

* Add SSH rule
* Attach Public IP
* Verify Route Table
* Verify Internet Gateway
* Use correct Key Pair

---

# Problem: EC2 Instance Unreachable

### Checks

* EC2 Status Checks
* Security Groups
* NACL
* Route Tables
* CPU Utilization
* Disk Space

### Commands

```bash
df -h
free -m
top
```

---

# Problem: Website Hosted on EC2 Not Opening

### Checks

#### Security Group

Verify:

```text
HTTP  Port 80
HTTPS Port 443
```

allowed.

---

#### Application Status

```bash
systemctl status nginx

systemctl status apache2
```

---

#### Port Listening

```bash
netstat -tulpn
```

---

# VPC Troubleshooting

## Problem: Public EC2 Has No Internet Access

### Verify

#### Internet Gateway

Attached to VPC.

---

#### Route Table

```text
0.0.0.0/0
↓
Internet Gateway
```

---

#### Public IP

Instance must have:

```text
Auto Assign Public IP = Enabled
```

---

#### Security Group

Outbound Traffic:

```text
Allow All
```

---

# Problem: Private EC2 Cannot Download Updates

### Checks

Verify:

```text
Private Subnet
↓
Route Table
↓
NAT Gateway
```

---

### Route

```text
0.0.0.0/0
↓
NAT Gateway
```

---

# Security Group Troubleshooting

## Problem: Application Not Reachable

### Verify

Correct port is open:

```text
22  -> SSH

80  -> HTTP

443 -> HTTPS

3306 -> MySQL

5432 -> PostgreSQL
```

---

### Example

Bad Configuration:

```text
No Port 80 Rule
```

Good Configuration:

```text
HTTP
Port 80
Source 0.0.0.0/0
```

---

# NACL Troubleshooting

## Problem

Traffic reaches subnet but responses fail.

### Cause

NACL is Stateless.

Need both:

```text
Inbound Rule
Outbound Rule
```

configured.

---

# Load Balancer Troubleshooting

## Problem: ALB Shows Unhealthy Targets

### Checks

#### Security Group

ALB → EC2 communication allowed.

---

#### Health Check Path

Verify:

```text
/health

/index.html
```

exists.

---

#### Application Running

```bash
systemctl status nginx
```

---

#### Port Match

Example:

```text
Target Group Port = 80

Application Port = 80
```

---

# Auto Scaling Troubleshooting

## Problem: Auto Scaling Not Launching New Instances

### Verify

#### CloudWatch Alarm

Status:

```text
ALARM
```

---

#### Launch Template

Correct:

* AMI
* Security Group
* Instance Type

---

#### ASG Limits

Verify:

```text
Desired Capacity

Min Capacity

Max Capacity
```

---

# S3 Troubleshooting

## Problem: Access Denied

### Checks

#### IAM Permissions

Verify:

```json
{
  "Effect": "Allow",
  "Action": "s3:*"
}
```

---

#### Bucket Policy

Verify bucket allows access.

---

#### Object Ownership

Verify permissions.

---

# Problem: Static Website Not Loading

### Checks

#### Static Website Hosting

Enabled.

---

#### Index File

```text
index.html
```

must exist.

---

#### Bucket Policy

Public read access configured.

---

# CloudFront Troubleshooting

## Problem: Users See Old Content

### Cause

CloudFront Cache.

---

### Resolution

Create Invalidation.

Example:

```text
/*
```

---

## Problem: CloudFront Returning 403

### Checks

* Origin Access Settings
* S3 Permissions
* Bucket Policy

---

# Route 53 Troubleshooting

## Problem: Domain Not Resolving

### Verify

#### Hosted Zone

Exists.

---

#### Record Set

Correct:

```text
A Record

CNAME
```

---

#### Name Servers

Domain registrar updated.

---

## Problem: Website Not Opening Using Domain Name

### Verify

DNS resolves correctly:

```bash
nslookup example.com
```

---

# Lambda Troubleshooting

## Problem: Lambda Timing Out

### Checks

#### Timeout Setting

Default:

```text
3 Seconds
```

Increase if needed.

---

#### External Dependencies

Check:

* Database Calls
* API Calls

---

#### Logs

View:

```text
CloudWatch Logs
```

---

## Problem: Lambda Not Triggering

### Verify

Trigger exists:

```text
S3

API Gateway

CloudWatch
```

---

### Verify Permissions

Lambda execution role configured.

---

# RDS Troubleshooting

## Problem: Cannot Connect to Database

### Verify

#### Security Group

Example:

```text
3306 MySQL

5432 PostgreSQL
```

allowed.

---

#### Endpoint

Verify endpoint is correct.

---

#### Credentials

Verify:

```text
Username
Password
```

---

#### Public Accessibility

If external connection required:

```text
Public Access = Yes
```

---

# Problem: Database Performance Slow

### Checks

#### CPU

CloudWatch Metrics.

---

#### Storage

Check free space.

---

#### Connections

Verify connection count.

---

### Solutions

* Increase Instance Size
* Add Read Replica
* Optimize Queries

---

# CloudWatch Troubleshooting

## Problem: Alarm Not Triggering

### Verify

#### Metric

Correct metric selected.

---

#### Threshold

Example:

```text
CPU > 80%
```

---

#### Evaluation Period

Configured correctly.

---

## Problem: No Logs Available

### Verify

#### IAM Permissions

CloudWatch Agent permissions.

---

#### Log Group

Exists.

---

#### CloudWatch Agent

Running.

---

# CloudTrail Troubleshooting

## Problem: Unable to Find User Activity

### Verify

#### Trail Enabled

CloudTrail active.

---

#### Correct Region

Check event region.

---

#### Event History

Search using:

```text
Username

Resource Name

Event Name
```

---

# Most Common Production Issues

## Website Down

### Check

1. Route53
2. CloudFront
3. Load Balancer
4. EC2
5. Security Groups
6. Application Logs

---

## Database Down

### Check

1. RDS Status
2. Security Groups
3. Endpoint
4. Credentials
5. Storage

---

## High CPU

### Check

1. CloudWatch Metrics
2. Running Processes
3. Traffic Increase

### Fix

* Scale Out
* Optimize Application

---

## High AWS Bill

### Check

1. Running EC2
2. Unused EBS
3. NAT Gateway
4. Data Transfer
5. S3 Storage

---

# Golden Interview Scenario

## Client Complaint

"Our website is down."

### Troubleshooting Approach

Step 1

Check DNS

```text
Route53
```

↓

Step 2

Check CDN

```text
CloudFront
```

↓

Step 3

Check Load Balancer

```text
ALB Health Checks
```

↓

Step 4

Check EC2

```text
Status Checks
```

↓

Step 5

Check Application

```bash
systemctl status nginx
```

↓

Step 6

Check Database

```text
RDS Connectivity
```

↓

Step 7

Check Logs

```text
CloudWatch Logs
```

This structured approach is exactly what interviewers expect from AWS Engineers, Cloud Engineers, and DevOps Engineers.

---

# Quick Troubleshooting Cheat Sheet

| Problem                 | First Thing to Check |
| ----------------------- | -------------------- |
| SSH Failure             | Security Group       |
| No Internet             | Route Table + IGW    |
| Private EC2 No Internet | NAT Gateway          |
| Website Down            | ALB + EC2            |
| S3 Access Denied        | IAM + Bucket Policy  |
| Lambda Failure          | CloudWatch Logs      |
| RDS Connection Issue    | Security Group       |
| High CPU                | CloudWatch Metrics   |
| Domain Not Resolving    | Route 53             |
| Audit Investigation     | CloudTrail           |
