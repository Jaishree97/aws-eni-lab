# AWS ENI Concepts

## What is ENI?

Elastic Network Interface (ENI) is a virtual network card attached to an EC2 instance.

An ENI contains:
- Private IPv4 address
- Elastic IP
- MAC address
- Security groups

## Types of ENI

### Primary ENI
- Automatically attached during EC2 launch
- Cannot be detached

### Secondary ENI
- Manually created and attached
- Can be detached and reused

## Advantages of ENI
- Multiple IP addresses
- Better network management
- Failover support
- High availability architecture

## Practical Learning
In this lab:
- Created Primary & Secondary ENI
- Associated Elastic IPs
- Tested Apache access using multiple IPs