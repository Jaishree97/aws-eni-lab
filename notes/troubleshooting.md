# Troubleshooting Notes

## Issue 1: Unable to Access Apache Web Page

### Cause
HTTP port 80 was not allowed in Security Group.

### Solution
Added inbound rule:
- HTTP (80)
- Source: 0.0.0.0/0

---

## Issue 2: SSH Connection Failed

### Cause
Incorrect PEM key permissions or wrong IP.

### Solution
Used correct command:

```bash
ssh -i "fdkey.pem" ec2-user@3.23.201.105
```

---

## Issue 3: Apache Service Not Running

### Solution

```bash
sudo systemctl start httpd
sudo systemctl enable httpd
```

---

## Issue 4: Secondary ENI Not Visible

### Solution

Verified using:

```bash
ip a
```