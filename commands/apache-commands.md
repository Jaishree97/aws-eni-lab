# Apache Web Server Setup

This document contains the Apache HTTP Server installation and configuration steps performed on the AWS EC2 instance.

---

# Install Apache HTTP Server

## Command

```bash
sudo yum install httpd -y
```

## Purpose

Installs the Apache HTTP Server package on the EC2 instance.

---

# Start Apache Service

## Command

```bash
sudo systemctl start httpd
```

## Purpose

Starts the Apache web server service immediately.

---

# Enable Apache on Boot

## Command

```bash
sudo systemctl enable httpd
```

## Purpose

Ensures Apache service automatically starts whenever the EC2 instance reboots.

---

# Check Apache Service Status

## Command

```bash
sudo systemctl status httpd
```

## Purpose

Verifies whether the Apache service is active and running properly.

---

# Restart Apache Service

## Command

```bash
sudo systemctl restart httpd
```

## Purpose

Restarts the Apache service after configuration changes or troubleshooting.

---

# Verify Apache Locally

## Command

```bash
curl localhost
```

## Purpose

Checks whether the Apache server is responding locally from the EC2 instance.

---

# Create Custom Web Page

## Command

```bash
echo "NIC-LAB" > /var/www/html/index.html
```

## Purpose

Creates a custom HTML page inside Apache’s default web root directory.

---

# Access Apache from Browser

## Steps

1. Copy the Public IP or Elastic IP of the EC2 instance.
2. Paste the IP address into the web browser.
3. Verify the custom webpage output.

## Expected Output

```text
NIC-LAB
```

---

# Apache Troubleshooting Commands

## Check Listening Ports

```bash
sudo netstat -tulnp | grep httpd
```

## Check Firewall Rules

```bash
sudo firewall-cmd --list-all
```

## View Apache Logs

```bash
sudo tail -f /var/log/httpd/error_log
```

---

# Learning Outcome

By completing this setup, the following concepts were implemented:

- Apache Web Server Installation
- Linux Service Management
- EC2 Web Hosting
- HTTP Service Validation
- Browser-based Access Testing
- Linux Networking Basics
- AWS EC2 Administration

---