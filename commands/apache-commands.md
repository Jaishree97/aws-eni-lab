# Apache Commands

## Install Apache HTTP Server

```bash
sudo yum install httpd -y
```

## Start Apache Service

```bash
sudo systemctl start httpd
```

## Enable Apache on Boot

```bash
sudo systemctl enable httpd
```

## Check Apache Status

```bash
sudo systemctl status httpd
```

## Restart Apache

```bash
sudo systemctl restart httpd
```

## Verify Apache Locally

```bash
curl localhost
```

## Create Custom Web Page

```bash
echo "NIC-LAB" > /var/www/html/index.html
```