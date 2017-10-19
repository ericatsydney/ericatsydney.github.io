---
layout: post
title:  "AWS training"
date:   2017-09-20 20:30:00 +1000
categories: Geek
---

Cloud Computing Concept includes:
- on demand
- IT
- access online
- pay as you go

Using cloud computing has the benefits as low cost, elastic, flexible, secured.

Here's a table to categorize the AWS product by 5 Pilars



Regions

It's public trans between region, encrypt your data. (alt solution private cloud)

EC2
T2 - For burst usage, e.g. high traffic in specific time

Reserved Cost Model: Pay upfront, 50 -75% lower hourly rate

Cow/ Pet strategy for server

ELB
Detect health
remove fail
reroute to healthy

VPC
Use case: Corporate Data Center

Route 53

EBS, S3, Glacier:
How to duplicate EBS in other region:
Snapshot EBS to S3( auto scaling) and restore S3 in other region as EBS
Automated lifecycle S3 -> Glacier -> delete (notice: one way only)

IAM:
active folder?

Cloutwatch: SNS trigger alarm

Redshift: data warehousing and analytics

Cloudformation: yaml, json format, cloudformer to export

AWS snowball: Import/Export, use physical storage to upload to S3

Disaster Recovery: 
Multi site, Warm Standby , pilot light, backup & restore.

Web architect:
Route 53 -> ELB -> Security Group(EC2, Cloudwatch), RDS -> S3 -> Cloudfront

Security Groups: set firewall and apply them to all instance in scalling

Pricing tool: TCO Calculator

Security done by AWS: ddos shield, API SSL(MAN in the middle), package sniffing and so on..

Key Management Service, Encrypt service ....

CloudTrail:records api calls
https://aws.amazon.com/security/
AWS Trusted Advisor

Storage gateway?


