# AWS Production Incidents

## Purpose

This document contains real-world AWS production incidents, root causes, troubleshooting approaches, and resolutions.

These incidents help students understand:

* Production Support
* DevOps Operations
* Incident Response
* Root Cause Analysis (RCA)
* AWS Troubleshooting

---

# Incident 1

## Website Down After Deployment

### Client Impact

* Users unable to access website
* Revenue loss
* High Priority Incident

### Symptoms

* Website returns HTTP 503
* ALB shows unhealthy targets

### Investigation

1. Checked Route 53
2. Checked ALB
3. Checked EC2 instances

### Root Cause

New deployment changed application configuration.

Application service failed to start.

### Resolution

* Rollback deployment
* Restart application
* Verify health checks

### Prevention

* Blue/Green Deployment
* Deployment validation checks

---

# Incident 2

## EC2 Server Unreachable

### Symptoms

* SSH timeout
* Application unavailable

### Investigation

1. Instance running
2. Security Group checked
3. Route table verified

### Root Cause

Security Group accidentally removed SSH access.

### Resolution

Restore inbound TCP 22 rule.

### Prevention

Use Infrastructure as Code (Terraform/CloudFormation).

---

# Incident 3

## RDS Database Connection Failure

### Symptoms

Application displays:

Database Connection Failed

### Investigation

1. RDS status checked
2. Endpoint verified
3. Security Groups reviewed

### Root Cause

Database Security Group did not allow application server traffic.

### Resolution

Allow application Security Group on port 3306.

### Prevention

Document connectivity requirements.

---

# Incident 4

## Sudden Traffic Spike

### Client Impact

Application became slow during sale event.

### Symptoms

* CPU 100%
* High response time
* User complaints

### Investigation

CloudWatch metrics reviewed.

### Root Cause

Auto Scaling not configured.

### Resolution

* Create Auto Scaling Group
* Configure scaling policy

### Prevention

Load testing before major events.

---

# Incident 5

## S3 Bucket Accidentally Deleted

### Symptoms

Application images unavailable.

### Investigation

CloudTrail logs reviewed.

### Root Cause

Administrator accidentally deleted bucket.

### Resolution

Restore data from backup.

### Prevention

* Enable Versioning
* Enable MFA Delete

---

# Incident 6

## CloudFront Serving Old Content

### Symptoms

Users still see outdated images.

### Investigation

Verified S3 object updated successfully.

### Root Cause

CloudFront cached old content.

### Resolution

Create CloudFront Invalidation.

### Prevention

Use versioned file names.

Example:

```text
logo-v1.png
logo-v2.png
```

---

# Incident 7

## DNS Outage

### Symptoms

Website inaccessible.

### Investigation

DNS lookup failed.

### Root Cause

Incorrect Route 53 record update.

### Resolution

Restore correct DNS record.

### Prevention

Approval process for DNS changes.

---

# Incident 8

## Lambda Function Timeout

### Symptoms

API requests failing.

### Investigation

CloudWatch logs reviewed.

### Root Cause

Lambda waiting for slow external API response.

### Resolution

* Increase timeout
* Retry mechanism added

### Prevention

Use asynchronous processing.

---

# Incident 9

## High AWS Bill

### Symptoms

Monthly AWS bill doubled.

### Investigation

Cost Explorer reviewed.

### Root Cause

Developer launched large EC2 instances and forgot to terminate them.

### Resolution

Terminate unused resources.

### Prevention

* AWS Budgets
* Resource tagging
* Cost monitoring

---

# Incident 10

## NAT Gateway Misconfiguration

### Symptoms

Private instances unable to download updates.

### Investigation

Route tables reviewed.

### Root Cause

Missing route to NAT Gateway.

### Resolution

Add:

```text
0.0.0.0/0 → NAT Gateway
```

### Prevention

Infrastructure review before production release.

---

# Incident 11

## Load Balancer Healthy but Application Down

### Symptoms

ALB shows healthy targets.

Users receive application errors.

### Investigation

Checked application logs.

### Root Cause

Application service crashed but health endpoint still returned HTTP 200.

### Resolution

Improve health checks.

### Prevention

Use application-aware health checks.

---

# Incident 12

## Storage Full on EC2

### Symptoms

Application stopped processing requests.

### Investigation

Checked disk usage.

```bash
df -h
```

### Root Cause

Log files consumed all disk space.

### Resolution

* Remove old logs
* Increase EBS size

### Prevention

Log rotation policy.

---

# Incident 13

## Read Performance Issue in RDS

### Symptoms

Slow application response.

### Investigation

Database monitoring showed heavy read workload.

### Root Cause

Single RDS instance handling all reads.

### Resolution

Create Read Replica.

### Prevention

Capacity planning.

---

# Incident 14

## Accidental Resource Deletion

### Symptoms

Production EC2 instance terminated.

### Investigation

CloudTrail reviewed.

### Root Cause

Engineer terminated wrong instance.

### Resolution

Restore from AMI backup.

### Prevention

* Termination protection
* Restricted IAM permissions

---

# Incident 15

## Application Outage Due to Expired SSL Certificate

### Symptoms

Browser security warnings.

### Investigation

Certificate expiration date checked.

### Root Cause

Certificate expired.

### Resolution

Renew certificate.

### Prevention

Use ACM managed certificates.

---

# Major Severity Levels

## P1 (Critical)

Examples:

* Production Down
* Database Unavailable
* Revenue Impact

Response Time:

15 Minutes

---

## P2 (High)

Examples:

* Partial Outage
* Performance Issues

Response Time:

30 Minutes

---

## P3 (Medium)

Examples:

* Non-critical functionality issue

Response Time:

4 Hours

---

## P4 (Low)

Examples:

* Cosmetic UI issue
* Documentation issue

Response Time:

24 Hours

---

# Standard Incident Handling Process

## Step 1

Identify Incident

---

## Step 2

Assess Business Impact

---

## Step 3

Gather Logs

Sources:

* CloudWatch
* CloudTrail
* Application Logs

---

## Step 4

Find Root Cause

Use:

* Metrics
* Logs
* AWS Console
* Monitoring Dashboards

---

## Step 5

Apply Fix

---

## Step 6

Validate Service

---

## Step 7

Perform RCA

Document:

* What happened?
* Why it happened?
* How it was fixed?
* Prevention steps?

---

# Production Incident Interview Questions

### Q1

Production website is down.

How would you troubleshoot?

---

### Q2

Users report slow application performance.

What AWS services would you check first?

---

### Q3

Database connections suddenly fail.

What steps would you follow?

---

### Q4

A Lambda function starts timing out.

How would you investigate?

---

### Q5

How would you identify who deleted an S3 bucket?

---

### Q6

A private EC2 instance cannot access the internet.

What would you check?

---

### Q7

AWS bill increased by 40%.

How would you identify the cause?

---

# Golden Production Support Approach

Whenever a production issue occurs:

1. Check Monitoring (CloudWatch)
2. Check Logs
3. Check Recent Changes
4. Check Networking
5. Check IAM Permissions
6. Check CloudTrail
7. Fix the Issue
8. Perform RCA

Following this process solves the majority of AWS production incidents encountered in real-world environments.
