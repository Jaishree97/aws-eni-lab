# 🚀 AWS ENI Networking Lab

![AWS](https://img.shields.io/badge/AWS-EC2-orange?style=for-the-badge&logo=amazonaws)
![Linux](https://img.shields.io/badge/Linux-RedHat-red?style=for-the-badge&logo=redhat)
![Networking](https://img.shields.io/badge/Domain-Networking-green?style=for-the-badge)
![GitHub](https://img.shields.io/badge/GitHub-VersionControl-black?style=for-the-badge&logo=github)
![Status](https://img.shields.io/badge/Project-Completed-success?style=for-the-badge)

---

# 📌 Project Title

AWS Elastic Network Interface (ENI) Lab with Elastic IP & Apache Web Server

---

# 🎯 Project Objective

The objective of this project is to understand and implement AWS networking concepts using:

- Elastic Network Interfaces (ENI)
- Elastic IPs
- EC2 Networking
- Apache Web Hosting
- Security Groups
- Linux Administration
- AWS Console Navigation
- Git & GitHub Version Control

This project demonstrates practical implementation of AWS networking infrastructure and ENI lifecycle management.

---

# 🏗️ Architecture Overview

```text
AWS Cloud (us-east-2)
│
├── VPC
│
├── EC2 Instance (linux-server)
│   │
│   ├── Primary ENI
│   │    ├── Private IP: 172.31.47.xx
│   │    └── Elastic IP: 18.xx.xx.xx
│   │
│   └── Secondary ENI
│        ├── Private IP: 172.31.40.61
│        └── Elastic IP: 16.58.218.132
│
├── Security Groups
│    ├── SSH (22)
│    ├── HTTP (80)
│    └── ICMP
│
└── Apache HTTP Server
      └── NIC-LAB Web Page