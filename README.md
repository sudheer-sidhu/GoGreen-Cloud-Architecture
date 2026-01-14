# GoGreen Insurance – Cloud Infrastructure Architecture Case Study

## Overview
This repository contains a cloud architecture case study for **GoGreen Insurance Company**, designed as part of the *Cloud Infrastructure and Services* module. The objective was to modernize a legacy hosting environment by designing a secure, highly available, and cost-conscious AWS-based architecture that meets strict performance and recovery requirements.

The solution focuses on high availability, disaster recovery, encryption, scalability, and operational monitoring—without modifying the existing database schema.

## Business Problem
GoGreen Insurance operates on a legacy infrastructure that suffers from:
- Limited availability and no Multi-AZ or disaster recovery setup
- Inability to meet **21,000 IOPS** database performance requirements
- Risky maintenance and patching processes
- Inability to guarantee a **4-hour Recovery Point Objective (RPO)**
- Decentralized and insecure document storage

## Solution Summary
The proposed solution migrates the existing environment to AWS using a **multi-tier architecture** with:
- A secure VPC design with public and private subnets
- Auto-scaled Web and Application tiers
- A high-performance, highly available RDS database layer
- Centralized document storage using Amazon S3 with cross-region replication
- Monitoring, alerting, and operational automation using native AWS services

A warm standby disaster recovery setup is implemented in a secondary region to balance resilience and cost.

## Key Architectural Highlights
- **Network:** Multi-AZ VPC with tier isolation and controlled ingress
- **Security:** Security groups, IAM roles, Secrets Manager, and restricted ports
- **Encryption:** Data encrypted at rest and in transit across all tiers
- **Database:** High-IOPS RDS configuration with automated backups and snapshot replication
- **RPO (4 hours):** Achieved via RDS automated backups, EC2 snapshots, and S3 versioning
- **Scalability:** Auto Scaling for Web and Application tiers
- **Monitoring & Alerts:** Amazon CloudWatch and SNS for operational visibility
- **Cost Optimization:** AMD-based instances, Savings Plans, S3 Glacier, and warm standby DR

## Disaster Recovery Strategy
- Primary region hosts full production workload
- Secondary region maintains a minimal standby footprint
- Cross-region replication for backups and documents
- Fast scale-up capability during regional failure

## Files in This Repository
- `GoGreen Case Study_TP088624.pdf` – Final architecture presentation
- `README.md` – Project overview and architectural explanation

## Author
**V.Sudheer**  
TP Number: TP088624  
Module: Cloud Infrastructure and Services
University: Asia Pacific University (APU)
Country: Malaysia
