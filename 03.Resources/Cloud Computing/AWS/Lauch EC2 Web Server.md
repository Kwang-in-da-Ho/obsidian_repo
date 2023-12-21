## 1. Install Apache Web Server
```shell
sudo su #change to super user
yum update -y #update package manager(yum)
yum install httpd -y #install httpd(Apache Web Server)
systemctl start httpd -y #start web server
```

## 2. Allow HTTP Connection for Security Group
* go to **Security Group** and add HTTP for Inbound Rules