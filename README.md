# 🚀 AWS ENI Networking Lab with Elastic IP & Apache Web Server

![AWS](https://img.shields.io/badge/AWS-EC2-orange)
![Elastic IP](https://img.shields.io/badge/AWS-ElasticIP-yellow)
![Linux](https://img.shields.io/badge/Linux-RedHat-blue)
![Networking](https://img.shields.io/badge/Domain-Networking-green)
![Status](https://img.shields.io/badge/Project-Completed-brightgreen)

---

# 📌 Project Overview

This project demonstrates the implementation of AWS Elastic Network Interfaces (ENI) with multiple private/public IP configurations inside an EC2 environment.

The lab includes:

- Primary ENI configuration
- Secondary ENI attachment
- Elastic IP association
- Apache HTTP Server setup
- Multiple IP accessibility testing
- Linux networking validation
- ENI termination behavior
- Security Group configuration
- Git & GitHub project documentation

This project helped build practical understanding of AWS networking concepts, Elastic IP management, and multi-interface EC2 architecture.

---

# 🎯 Project Objective

The objective of this project is to design and implement AWS networking architecture using multiple ENIs and Elastic IPs.

### Key Objectives

- Understand ENI concepts
- Configure Primary & Secondary ENIs
- Associate Elastic IPs
- Validate multiple IP communication
- Configure Apache HTTP Server
- Test web accessibility
- Understand ENI termination behavior
- Practice Linux administration
- Build professional GitHub documentation

---

# 🏗️ Architecture Diagram

```text
AWS Cloud (us-east-2)
│
├── VPC
│
├── EC2 Instance (linux-server)
│   │
│   ├── Primary ENI (primary-eni)
│   │    ├── Private IP: 172.31.42.54
│   │    ├── Secondary Private IP: 172.31.42.55
│   │    └── Elastic IP: 3.23.201.105
│   │
│   └── Secondary ENI (sec-eni)
│        ├── Private IP: 172.31.40.61
│        └── Elastic IP: 16.58.218.132
│
├── Security Groups
│    ├── SSH (22)
│    └── HTTP (80)
│
└── Apache HTTP Server
      └── NIC-LAB Web Page
```

---

# 📂 Repository Structure

```text
aws-eni-lab/
│
├── README.md
│
├── screenshots/
│   ├── 01-ec2-instance-running.png
│   ├── 02-security-groups.png
│   ├── 03-primary-eni-details.png
│   ├── 04-primary-elastic-ip.png
│   ├── 05-secondary-eni-details.png
│   ├── 06-secondary-elastic-ip.png
│   ├── 07-primary-eni-termination-behavior.png
│   ├── 08-secondary-eni-termination-behavior.png
│   ├── 09-ssh-connection.png
│   ├── 10-linux-ip-address-verification.png
│   ├── 11-apache-installation.png
│   ├── 12-apache-service-validation.png
│   ├── 13-browser-output-primary-ip.png
│   ├── 14-browser-output-elastic-ip-primary.png
│   └── 15-browser-output-elastic-ip-secondary.png
│
├── commands/
│   ├── apache-commands.md
│   ├── eni-commands.md
│   └── linux-networking.md
│
├── notes/
│   ├── eni-concepts.md
│   ├── networking-basics.md
│   └── troubleshooting.md
│
└── docs/
    └── project-flow.md
```

---

# 🌍 AWS Region

```text
us-east-2 (Ohio)
```

---

# 🧰 AWS Services Used

| Service | Purpose |
|---|---|
| Amazon EC2 | Virtual Linux Server |
| Elastic Network Interface | Multiple network interfaces |
| Elastic IP | Static public IP |
| Security Groups | Traffic filtering |
| Apache HTTP Server | Web hosting |
| Linux | Server administration |
| GitHub | Project documentation |

---

# ✅ Prerequisites

- AWS Account
- EC2 Key Pair
- Git & GitHub
- Basic Linux Knowledge
- Networking Fundamentals
- SSH Client (PuTTY/Git Bash)

---

# 🚀 Lab Implementation Steps

## Step 1: Launch EC2 Instance

Created RedHat Linux EC2 instance.

| Configuration | Value |
|---|---|
| Instance Name | linux-server |
| Instance Type | t3.micro |
| Region | us-east-2 |
| Operating System | RedHat Linux |

---

## Step 2: Configure Security Groups

Configured inbound rules:

| Protocol | Port | Purpose |
|---|---|---|
| SSH | 22 | Remote Access |
| HTTP | 80 | Web Access |

---

## Step 3: Create Primary ENI

Configured primary ENI with:

- Primary Private IP
- Secondary Private IP
- Elastic IP association

---

## Step 4: Create Secondary ENI

Created additional network interface with:

- Separate private IP
- Dedicated Elastic IP
- Separate security group

---

## Step 5: Attach Secondary ENI

Attached secondary ENI to running EC2 instance successfully.

Purpose:
- Multi-network interface communication
- Advanced AWS networking practice

---

## Step 6: Validate Linux Networking

Verified network interfaces using:

```bash
ip a
```

Validated:
- Primary private IP
- Secondary private IP
- Additional ENI interface

---

## Step 7: Install Apache HTTP Server

Installed Apache using:

```bash
yum install httpd -y
```

Started service:

```bash
systemctl start httpd
```

Enabled service:

```bash
systemctl enable httpd
```

---

## Step 8: Validate Apache Server

Validation performed using:

```bash
curl localhost
```

Successfully verified Apache web server response.

---

## Step 9: Configure Custom Web Page

Created custom webpage:

```html
<h1>NIC-LAB</h1>
```

Accessible through:
- Primary Elastic IP
- Secondary Elastic IP
- Secondary ENI

---

## Step 10: Test ENI Termination Behavior

Validated:

- Secondary ENI survives instance termination
- Primary ENI deleted automatically

This helped understand AWS ENI lifecycle behavior.

---

# 🐧 Linux Commands Documentation

Detailed command documentation available here:

- [Apache Commands](commands/apache-commands.md)
- [ENI Commands](commands/eni-commands.md)
- [Linux Networking](commands/linux-networking.md)

---

# 📝 Additional Notes

Detailed conceptual and troubleshooting notes available here:

- [ENI Concepts](notes/eni-concepts.md)
- [Networking Basics](notes/networking-basics.md)
- [Troubleshooting Notes](notes/troubleshooting.md)

---

# 📄 Project Workflow Documentation

Complete project implementation workflow available here:

- [Project Flow](docs/project-flow.md)

---

# 📸 Screenshots

## EC2 Instance

![EC2 Instance](screenshots/01-ec2-instance.png)

---

## Primary ENI

![Primary ENI](screenshots/04-primary-eni.png)

---

## Secondary ENI

![Secondary ENI](screenshots/06-secondary-eni.png)

---

## Apache Validation

![Apache Validation](screenshots/11-apache-validation.png)

---

## Web Output

![Web Output](screenshots/12-web-output-primary-ip.png)

---

# 🔐 Security Concepts Learned

- Elastic Network Interfaces
- Elastic IP Management
- Public vs Private IP
- Security Groups
- HTTP Protocol
- SSH Connectivity
- Linux Networking
- Multi-IP Architecture

---

# ⚠️ Challenges Faced

- ENI attachment troubleshooting
- Elastic IP association
- Apache service validation
- SSH connectivity issues
- Multi-IP verification
- Security Group configuration

---

# 🧠 Key Learning Outcomes

After completing this project, I learned:

- AWS ENI architecture
- Elastic IP association
- Linux networking fundamentals
- Apache HTTP server configuration
- Multi-network interface validation
- AWS security group management
- SSH administration
- EC2 networking concepts
- ENI lifecycle behavior
- Practical cloud networking

---

# 🧹 Cleanup

All AWS resources created during this lab were deleted after testing to avoid unnecessary AWS billing charges.

---

# 🚀 Future Improvements

- Add Load Balancer
- Configure Auto Scaling
- Implement Terraform automation
- Add CloudWatch monitoring
- Configure Route53
- Implement NAT Gateway

---

# 👩‍💻 Author

**Jaishree Chaure**

Passionate about AWS, Linux, Networking, and DevOps Engineering.  
Currently building hands-on cloud and infrastructure projects to strengthen practical skills in AWS and DevOps.

🔗 GitHub: https://github.com/Jaishree97