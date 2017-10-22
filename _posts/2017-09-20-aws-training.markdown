---
layout: post
title:  "AWS training"
date:   2017-09-20 20:30:00 +1000
categories: Geek
---

Concept
=======

Cloud Computing Concept includes:
- on demand
- IT
- access online
- pay as you go

Using cloud computing has the benefits as low cost, elastic, flexible, secured.


Product
=======

Here're the tables to list AWS key services by 5 pilars (security, reliability, performance)

|Areas   | Key Services  |
|---|---|
| Identity and Access Management | IAM, MFA  |
| Detective Control  | CloudTrail, Config, Cloudwatch  |
| Infrastructure protection  | VPC  |
| Data Protection | ELB, EBS, S3, RDS |
| Incident Response | IAM, Cloudformation |

Reliability Key Service: Cloudwatch
|Areas   | Key Services  |
|---|---|
| Foundations | IAM, VPC  |
| Change Management  | CloudTrail, Config  |
| Failure Management  | Cloudformation  |

Performance Key Service: Cloudwatch
|Areas   | Key Services  |
|---|---|
| Selection | EBS, Auto Scaling, S3, Glacier, RDS, Dynamo DB  |
| Review | Cloudformation |
| Monitoring | Cloudwatch, Lamda |
| Trade-off | Cloudfront, Elasticache, RDS read replica |


CloudTrail: records account activity by actions across different services in AWS

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


Topic
=====
Cow/ Pet strategy for server


EC2
T2 - For burst usage, e.g. high traffic in specific time

Reserved Cost Model: Pay upfront, 50 -75% lower hourly rate




Disaster Recovery: 
Multi site, Warm Standby , pilot light, backup & restore.

Web architect:
Route 53 -> ELB -> Security Group(EC2, Cloudwatch), RDS -> S3 -> Cloudfront

Security Groups: set firewall and apply them to all instance in scalling

Pricing tool: TCO Calculator

Security done by AWS: ddos shield, API SSL(MAN in the middle), package sniffing and so on..

Key Management Service, Encrypt service ....



AWS Trusted Advisor

Storage gateway?


Regions                                                                          
                                                                                 
It's public trans between region, encrypt your data. (alt solution private cloud)