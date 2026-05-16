# 🚀 AWS ENI Networking Lab with Elastic IP & Apache Web Server

![AWS](https://img.shields.io/badge/AWS-EC2-orange?style=for-the-badge&logo=amazonaws)
![Linux](https://img.shields.io/badge/Linux-Administration-black?style=for-the-badge&logo=linux)
![Apache](https://img.shields.io/badge/Apache-WebServer-red?style=for-the-badge&logo=apache)
![Networking](https://img.shields.io/badge/AWS-Networking-blue?style=for-the-badge)
![GitHub](https://img.shields.io/badge/GitHub-VersionControl-white?style=for-the-badge&logo=github)
![Project](https://img.shields.io/badge/Project-Completed-brightgreen?style=for-the-badge)

---

# 📌 Project Overview

This project demonstrates the implementation of **AWS Elastic Network Interfaces (ENI)** with **Elastic IPs**, **Apache HTTP Server**, and **Linux Administration** inside AWS EC2 infrastructure.

The purpose of this lab is to understand how multiple ENIs work in AWS networking and how Elastic IPs can be mapped to different interfaces attached to a single EC2 instance.

The project includes:

- Primary ENI configuration
- Secondary ENI creation and attachment
- Elastic IP association
- Apache HTTP Server setup
- Web server validation through browser
- ENI termination behavior testing
- Linux networking validation
- Git & GitHub integration

This lab helped build practical understanding of AWS networking fundamentals, EC2 networking, and Linux server management.

---

# 🎯 Project Objective

The objective of this project is to design and implement secure AWS networking architecture using Elastic Network Interfaces.

### Key Objectives

- Understand AWS ENI concepts
- Configure Primary & Secondary ENI
- Associate Elastic IPs with ENIs
- Deploy Apache Web Server
- Validate network connectivity
- Understand ENI deletion behavior
- Practice Linux administration
- Push project to GitHub professionally

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
│    └── HTTP (80)
│
└── Apache HTTP Server
      └── NIC-LAB Web Page
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
| Amazon EC2 | Launch Linux virtual server |
| Elastic Network Interface (ENI) | Attach multiple network interfaces |
| Elastic IP | Static public IP assignment |
| Security Groups | Firewall and traffic filtering |
| VPC | Virtual private cloud networking |
| Apache HTTP Server | Host web application |
| Git & GitHub | Version control and project hosting |

---

# ✅ Prerequisites

Before starting this lab, ensure the following requirements are available:

- AWS Account
- EC2 Key Pair
- Linux basic knowledge
- Git installed
- GitHub account
- VS Code installed
- PuTTY / MobaXterm / Git Bash
- Understanding of networking basics

---

# 🚀 AWS LAB IMPLEMENTATION

# Step 1 — Launch EC2 Instance

### Console Navigation

```text
AWS Console
→ EC2
→ Instances
→ Launch Instance
```

### EC2 Configuration

| Parameter | Value |
|---|---|
| Name | linux-server |
| AMI | Amazon Linux 2 |
| Instance Type | t2.micro |
| Key Pair | your-key |
| VPC | Default VPC |
| Auto Assign Public IP | Enabled |

---

# Step 2 — Configure Security Group

### Inbound Rules

| Type | Port | Source |
|---|---|---|
| SSH | 22 | My IP |
| HTTP | 80 | Anywhere |

---

# Step 3 — Connect to EC2 Instance

### SSH Command

```bash
ssh -i your-key.pem ec2-user@<PUBLIC-IP>
```

### Become Root User

```bash
sudo su
```

---

# Step 4 — Install Apache HTTP Server

### Update Packages

```bash
yum update -y
```

### Install Apache

```bash
yum install httpd -y
```

### Start Apache Service

```bash
systemctl start httpd
```

### Enable Apache at Boot

```bash
systemctl enable httpd
```

### Verify Apache Status

```bash
systemctl status httpd
```

---

# Step 5 — Create Custom Web Page

### Navigate to Web Directory

```bash
cd /var/www/html
```

### Create Index File

```bash
vim index.html
```

### Add HTML Content

```html
<h1>NIC-LAB</h1>
```

### Restart Apache

```bash
systemctl restart httpd
```

---

# Step 6 — Create Secondary ENI

### Console Navigation

```text
AWS Console
→ EC2
→ Network Interfaces
→ Create Network Interface
```

### ENI Configuration

| Parameter | Value |
|---|---|
| Name | sec-eni |
| Subnet | Same subnet as EC2 |
| Security Group | sec-nic-sg |

---

# Step 7 — Attach Secondary ENI

### Console Navigation

```text
EC2
→ Network Interfaces
→ Select sec-eni
→ Actions
→ Attach
```

### Attach To

| Parameter | Value |
|---|---|
| Instance | linux-server |
| Device Index | 1 |

---

# Step 8 — Allocate Elastic IP

### Console Navigation

```text
EC2
→ Elastic IPs
→ Allocate Elastic IP
```

Allocate two Elastic IPs:

- One for Primary ENI
- One for Secondary ENI

---

# Step 9 — Associate Elastic IPs

### Associate Primary Elastic IP

```text
Elastic IP
→ Associate
→ Select Primary ENI
```

### Associate Secondary Elastic IP

```text
Elastic IP
→ Associate
→ Select Secondary ENI
```

---

# Step 10 — Verify Website

Open browser:

```text
http://<Elastic-IP>
```

Expected Output:

```text
NIC-LAB
```

---

# 🔍 Verify Network Interfaces

### Check Network Interfaces in Linux

```bash
ip addr
```

### Check Routing Table

```bash
ip route
```

### Check Listening Ports

```bash
netstat -tulpn
```

---

# ⚠️ ENI Termination Behavior

## Primary ENI

When EC2 instance is terminated:

- Primary ENI gets deleted automatically
- Public IP gets released
- Elastic IP disassociates

## Secondary ENI

If:

```text
Delete on termination = Disabled
```

Then:

- Secondary ENI remains available
- Elastic IP remains attached
- Can be attached to another EC2 instance

This is useful for failover and persistent networking.

---

# 📂 Repository Structure

```text
aws-eni-lab/
│
├── README.md
│
├── screenshots/
│
├── commands/
│   ├── apache-commands.md
│   ├── eni-commands.md
│   └── linux-networking.md
│
├── notes/
│   ├── eni-concepts.md
│   ├── troubleshooting.md
│   └── networking-basics.md
│
└── docs/
    └── project-flow.md
```

---

# 💻 Linux Commands Used

### Check Interfaces

```bash
ip addr
```

### Check Routes

```bash
ip route
```

### Check Apache Status

```bash
systemctl status httpd
```

### Restart Apache

```bash
systemctl restart httpd
```

### Check Listening Ports

```bash
ss -tulpn
```

---

# 🌐 Git & GitHub Commands

### Initialize Git

```bash
git init
```

### Check Status

```bash
git status
```

### Add Files

```bash
git add .
```

### Commit Changes

```bash
git commit -m "Added AWS ENI Networking Lab project"
```

### Add Remote Repository

```bash
git remote add origin https://github.com/yourusername/aws-eni-lab.git
```

### Push Code to GitHub

```bash
git branch -M main
git push -u origin main
```

---

# 📸 Project Screenshots

Include screenshots for:

- EC2 instance
- Network interfaces
- Elastic IPs
- Apache web page
- ENI attachment
- Security groups
- Browser output
- ENI termination behavior

---

# 🧠 Key Learnings

Through this project, I learned:

- AWS ENI architecture
- Elastic IP association
- Linux server administration
- Apache Web Server deployment
- EC2 networking concepts
- ENI persistence behavior
- GitHub project management
- Real-world cloud networking basics

---

# 🚀 Future Improvements

- Add Load Balancer
- Configure Auto Scaling
- Add Monitoring with CloudWatch
- Create Multi-AZ setup
- Automate deployment using Terraform

---

# 👩‍💻 Author

### Jaishree Chaure

AWS | Linux | DevOps Learner

---

# ⭐ Conclusion

This AWS ENI Networking Lab provided hands-on experience with AWS networking, Linux administration, and Elastic Network Interface management.

The project demonstrates practical cloud networking implementation using multiple ENIs, Elastic IPs, Apache Web Server, and GitHub project documentation.