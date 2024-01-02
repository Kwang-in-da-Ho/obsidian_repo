## What is it?
* A virtual machine
## Basic Concepts

|          Feature          | Explanation                                                                                |
|:-------------------------:|:------------------------------------------------------------------------------------------ |
| Amazon Machine Image(AMI) | The OS and SW on your instance                                                             |
|     Instance Families     | Family of hardware for specific purposes (Genaral/Compute/Storage/Memory optimized or GPU) |
|    Elastic Block Store    | Attach Disks to EC2 Instances                                                              |
|      Security Group       | Virtual firewall to control inbound/outbound traffic                                       |
|         Key Pair          | public key => stored in EC2, private key => you keep it                                                                                           |


## Features
1. Create and manage lifecycle
2. Attach Storage to EC2 instance (EBS - Electric Block Storage)
3. Load Balancing for multiple EC2 instances

## Launching EC2 Web Server
### 1. Install Apache Web Server
```shell
sudo su #change to super user
yum update -y #update package manager(yum)
yum install httpd -y #install httpd(Apache Web Server)
systemctl start httpd -y #start web server
```

### 2. Allow HTTP Connection for Security Group
* go to **Security Group** and add HTTP for Inbound Rules
