## What is it?
* Simplest way to deploy and scale web app in AWS
	* provides end-to-end web app management
	* supports many languages and frameworks
	* No usage charges*
### Features
* Auto load balancing
* Auto scaling
* Manage platform updates

## Creating an EB Application
### Prerequisites
* An EC2 Instance profile with Elastic Beanstalk policies
	* IAM Console > Role > Create Role > choose AWS Service, use case EC2
	* Attach following
		* `AWSElasticBeanstalkWebTier`
		- `AWSElasticBeanstalkWorkerTier`
		- `AWSElasticBeanstalkMulticontainerDocker`
	- Enter a name for the role (`aws-elasticbeanstalk-ec2-role`)
### Steps
1. Open Elastic Beanstalk management console

## What EB Automatically Creates
### EC2 Instance
* And install runtime you chose when creating EB Environment*
### Auto Scaling Group
* Desired, Minimum, Maximum capacity is set with your choice
### Load Balancer