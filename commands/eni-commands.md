# AWS ENI Commands Documentation

This document contains the AWS Elastic Network Interface (ENI) related commands and configurations performed during the AWS networking lab.

---

## Display Network Interfaces

```bash
ip a
```

### Explanation

Displays all available network interfaces and assigned IP addresses on the Linux EC2 instance.

---

## Show Host IP Address

```bash
hostname -i
```

### Explanation

Shows the internal/private IP address of the EC2 instance.

---

## Check Routing Table

```bash
ip route
```

### Explanation

Displays the routing table used for network communication and internet access.

---

## Display Interface Details

```bash
ip addr show
```

### Explanation

Provides detailed information about network interfaces and IP configurations.

---

## Verify Internet Connectivity

```bash
ping google.com
```

### Explanation

Checks whether the EC2 instance can access the internet successfully.

---

## Check Listening Ports

```bash
ss -tulnp
```

### Explanation

Displays all active listening ports and running network services.

---

## Verify Apache Port

```bash
netstat -tulnp
```

### Explanation

Verifies whether the Apache web server is listening on HTTP ports such as port 80.

---