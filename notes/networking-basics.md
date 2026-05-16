# Networking Basics

## Public IP
Used for internet communication.

Example:
- 3.23.201.105

## Private IP
Used for internal AWS communication.

Example:
- 172.31.42.54

## Elastic IP
Static public IP provided by AWS.

Benefits:
- Persistent public access
- Can be remapped to another instance

## Security Group
Acts as a virtual firewall for EC2.

Rules used:
- SSH (22)
- HTTP (80)

## Apache HTTP Server
Used to host web applications on Linux servers.

Installed using:

```bash
yum install httpd -y
```

## ENI Validation

Used command:

```bash
ip a
```

to verify:
- Multiple interfaces
- Multiple private IPs