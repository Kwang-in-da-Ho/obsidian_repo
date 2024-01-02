* Authentication management with [[IAM]]
* For high availability - [[Regions and Zones]]
## Serverless
[[AWS Lambda]]

## Elastic Computing
[[EC2(Elastic Compute Cloud)]]
[[Elastic BeanStalk]]
[[Amazon EKS]]

## Container Management

## AWS Configuration Examples
| AWS Services                                                | Description                                             | Use Case                                                        |
| ----------------------------------------------------------- | ------------------------------------------------------- | --------------------------------------------------------------- |
| [[EC2(Elastic Compute Cloud)]] + ELB(Elastic Load Balancer) | Traditional Approach (Virtual Machine + Load Balancing) | When you need control over OS, when you want to run custom SW   |
| [[Elastic BeanStalk]]                                       | Automatically creates EC2 instances and ELB             | Simplify management of web applications and batch applications. |
| [[ECS(Elastic Container Service]]                           | Run containers in EC2 based ECS clusters                | Simplify managing Microservices with Docker containers          |
| [[Amazon EKS]]                                              | Run and Scale k8s clusters                              |                                                                 |
| [[AWS Fargate]]                                             | Serverless version of ECS and EKS                       |                                                                 |
| [[AWS Lambda]]                                              | Serverless                                                        |                                                                 |

