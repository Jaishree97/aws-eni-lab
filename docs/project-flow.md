# AWS ENI Networking Lab - Project Flow

# 📌 Project Workflow

This document explains the complete implementation flow of the AWS ENI Networking Lab project.

---

# Step 1 — Launch EC2 Instance

Created a Red Hat Linux EC2 instance in AWS.

### Configuration
- Instance Type: t3.micro
- Region: us-east-2 (Ohio)
- Operating System: Red Hat Enterprise Linux
- Default VPC used

---

# Step 2 — Configure Security Groups

Created security group rules to allow:

| Port | Protocol | Purpose |
|------|-----------|----------|
| 22 | SSH | Remote access |
| 80 | HTTP | Apache web access |

---

# Step 3 — Connect EC2 via SSH

Connected to the server using PEM key authentication.

```bash
ssh -i "fdkey.pem" ec2-user@3.23.201.105
```

Successfully logged into the Linux server.

---

# Step 4 — Verify Network Configuration

Checked network interfaces and IP addresses.

```bash
hostname -i
ip a
```

Verified:
- Primary private IP
- Secondary private IP
- Active network interface

---

# Step 5 — Create Secondary ENI

Created an additional Elastic Network Interface (ENI) in AWS.

### Secondary ENI Configuration
- Same subnet as EC2
- Separate private IP
- Separate security group

Attached the ENI to the EC2 instance successfully.

---

# Step 6 — Associate Elastic IPs

Allocated and attached Elastic IP addresses.

### Elastic IP Mapping

| Interface | Private IP | Elastic IP |
|-----------|-------------|-------------|
| Primary ENI | 172.31.42.54 | 3.23.201.105 |
| Secondary ENI | 172.31.40.61 | 16.58.218.132 |

---

# Step 7 — Install Apache HTTP Server

Installed Apache Web Server on the EC2 instance.

```bash
sudo yum install httpd -y
```

Started and enabled Apache service.

```bash
sudo systemctl start httpd
sudo systemctl enable httpd
```

---

# Step 8 — Deploy Test Web Page

Created a custom HTML page.

```bash
echo "NIC-LAB" > /var/www/html/index.html
```

---

# Step 9 — Validate Web Access

Verified Apache web page using:

- Primary Public IP
- Elastic IP
- Secondary ENI Elastic IP

Successfully accessed:

```text
NIC-LAB
```

from browser.

---

# Step 10 — Verify ENI Termination Behavior

Tested ENI deletion settings.

### Observations

- Primary ENI:
  - Automatically deleted with EC2 termination

- Secondary ENI:
  - Remained available after instance termination

This demonstrates AWS ENI persistence behavior.

---

# 📚 Skills Practiced

- AWS EC2
- Elastic Network Interfaces (ENI)
- Elastic IP
- Linux Administration
- Apache HTTP Server
- Security Groups
- SSH Connectivity
- AWS Networking
- GitHub Documentation

---

# ✅ Project Outcome

Successfully implemented and validated:
- Multi-interface EC2 networking
- Elastic IP association
- Apache web hosting
- ENI lifecycle behavior
- Linux networking verification

This project improved practical understanding of AWS networking and cloud infrastructure administration.