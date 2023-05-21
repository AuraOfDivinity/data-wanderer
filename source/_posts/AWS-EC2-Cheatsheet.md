---
title: AWS EC2 Cheatsheet
date: 2023-05-21 07:10:04
tags:
- EC2
- Cheatsheet    
categories: 
- AWS
---

## What is AWS EC2?

**EC2** stands for Elastic Compute Cloud which is an infrastructure as a services (Iaas).
EC2 mainly consists in the capabilities of,

1. Renting virtual machines (EC2)
2. Storing data on virtual drives (EBS)
3. Distributing load across machines (ELB)
4. Scaling the services using Auto-scaling groups (ASG)

## What are different configuration options for EC2?

1. OS: Linux, Windows or Mac OS
2. How much compute power and CPU?
3. How much storage space and if that storage space is network attached (EBS/EFS) or hardware (EC2 Instance Storage)
4. Network Card
5. Firewall Groups (I.e the security groups)
6. Bootstrap script

## What is the User Data Script?

It is possible to to bootstrap(i.e launching commands) our EC2 instance using the EC2 User Data script at the initial launch of the instance and would never be run again. These commands may include instructions to install updates, install software , download common files etc. The User Data script has root access.

## What are different EC2 Instance Types?

### General Purpose

Great for diverse workloads with a balance of Compute, Memory & Networking.

### Compute Optimized

Compute optimized are ideal for compute bound applications that benefit from high performance processors.

Batch processing workloads
Media Transcoding
High Performance web server
Scientific modeling & machine learning
Dedicated gaming servers.

### Memory Optimized

Memory optimized instances are designed to deliver fast performance for workloads that process large data sets in memory.

High performance relational/non-relational databases
Distributed web scale cache stores
In-memory databases optimized for BI
Applications performing real time processing of unstructured data.

### Accelerated Computing

Accelerated Computing instances use hardware accelerators, or co-processors to perform functions such as floating-point number calculations, graphics processing, or data pattern matching.

### Storagee Optimized

This instance family provides Non-Volatile Memory Express (NVMe) SSD-Backed instance storage optimized for low latency, very high random I/O performance, high sequential read throughput and high IOPS at a low cost.

High frequency online transaction processing (OLTP) systems
Relational & NoSQL databases
Data warehousing applications

## What are security groups?

Security groups acts as a firewall to the EC2 instance and control how the traffic is allowed in or out of the EC2 instances. They regulate,

1. Authorized IP ranges
2. Access to ports 
3. Control of inbound network traffic
4. Control of outbound network traffic

Security groups only contain allow rules and can be referenced by IP’s or other security groups.
Security groups can be attached to multiple instances and an instance can have multiple security groups attached to it.
Security groups are locked down to a region/VPC combination
It’s a good idea to maintain a separate  security group for SSH access.
By default all inbound traffic is blocked and all outbound traffic is authorized.

## What are some regularly used ports?

22 - SSH (Secure Shell)- Log into an EC2 instance
21 - FTP (File Transfer Protocol)- Upload files into a file share
22 - SFTP(Secure File Transfer Protocol) - Upload files using SSH
80 - HTTP - Access unsecured websites 
443 - HTTPS - Access secured websites
3389 - RDP ( Remotes Desktop Protocol) - Login to a windows instance.

## What is SSH & Instance connect?

SSH allows users to control a remote machine all using the command line.

EC2 Instance connect allows users to do a browser based SSH session into a given EC2 instance.

## What are different EC2 Instance Purchasing Options?

### EC2 On Demand

Pay for what you use ( Linux & Windows billing per second after first minute. Other OS’s billing per hour)
Has the highest cost but no upfront payment
No long term commitment

Recommended for short term uninterrupted workloads where you can’t predict how the application will behave.

### Reserved Instance

Upto 72% discount compared to on demand

You reserve a specific instance attribute (Instance Type, Region, Tenancy, OS)
Reservation Period - ( 1year or 3 years) Higher the reservation period, higher the discount.
Payment Options - No upfront, partial upfront and all upfront
Reserved instance scope - Regional or Zonal.
Buy and sell unused reserved instanced in the marketplace.

Convertible Reserved instances - can changes the reserved attribute later on.

### Savings Plan

Get the same discount of 72% mentioned on the reserved instances.
Commit to a certain type of usage ($10 for 1 or 3 years)
Usage beyond the Savings plan mentioned above is billed at the On Demand price.
Locked to a specific instance family & region (M5 in us-east-1)
Flexible across the instance size (M5.xlarge, M5.2xlarge), OS (Linux, Windows), Tenancy

### Spot Instances

Can get the highest discount upto  90% & the most cost efficient instance type in AWS.

Recommended for workloads that are resilient for failure such as,
Batch jobs, Data analysis, Image processing, Distributed workloads, workloads with flexible start and end times and are not suited for critical workloads such as databases.

### Dedicated Hosts

A physical server with EC2 instance capacity fully dedicated for your use.
Allows to address compliance requirements and use existing server bound software licenses.
Most expensive instance type.

Recommended for use cases where there are compliance requirements or licensing requirements.

### Dedicated Instances

Instance that run on hardware dedicated to you. 
May share the hardware with other instances in the same account.

### Capacity Reservations

Reserve on demand instances capacity in a specific AZ for any duration.
No time commitment or discount

Recommended for use cases where there are short term uninterrupted workloads that need to be in a specific AZ.

## What is a Spot Fleet?

A spot fleet = Set of spot instances + (optional) On demand instances
A spot fleet will try to meet the target capacity with the provided price constraints.
Define multiple launch options (referred to as launch pools with different instance type, OS and availability zones)
The fleet will choose the best and most efficient pool for you.
Spot fleets stop launching instances when the capacity is or the max cost is reached.

## What are different strategies to allocate spot instances within a spot fleet?

Lowest Price - From the pool with the lowest price (Cost optimization + Short workloads)
Diversified - Distributed across all pools ( Good for availability + long workloads). 
Capacity optimized - pool with the optimal capacity for the number of instances
Price Capacity Optimized - (Recommended for most use cases) chooses the pools with the highest capacity available and then selects the pool with the lowest price.

## How to terminate a spot instance?

Spot instances are created through spot requests. Each spot request specifies the maximum price, desired number of instances, launch specification, valid time period and the request type.

The request type could be either one time or persistent. If the request type is one time request, as soon as the spot instance is created the spot request would be removed. However if it’s persistent, the spot request is kept active even when the spot instances are interrupted.

When using persistent spot requests the users should make sure to cancel the spot request first and then interrupt the spot instance to successfully terminate the spot instance.