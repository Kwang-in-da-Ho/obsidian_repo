## Why Cloud Computing?
* On-demand resource provisioning
* "Go Global" in just a few miunutes
* Avoid undifferentiated heavy lifting
	* ex) setting up highly available DB

## IaaS vs PaaS
|                      | IaaS                                                                                   | PaaS                                               |
| -------------------- | -------------------------------------------------------------------------------------- | -------------------------------------------------- |
| What do you use?     | Only infrasturcture                                                                    | the Platform                                       |
| Provider provides..  | Hardware, Networing, Virtualization                                                    | All infrastructures + OS, App runtime, scaling, .. |
| Your responsibilties | OS upgrades and patches, Application code and runtime, configuring load balancing, ... | App / Service Configuration, Application code      |
| Examples                     |                                                                                        | AWS Elastic Beanstalk, Azure App Service, Google App Engine                                                    |

## Serverless Architecture
### What it means
* Does not mean "No Servers"
* Refers to an architecture where the developer does not have to worry about server infrastructure
### Features
* Flexible scaling and automated high availability
* Pay for use
	* Pay for **requests** and **not servers**
### Examples
* [[AWS Lambda]]