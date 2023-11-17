# Day 4 - AWS - Creating Virtual Machines

## Option 1: Creating VMs using User Interface

1. Log into your AWS Account, you should see the AWS Dashboard

![](https://github.com/harsha-commit/devops-zero-to-hero/blob/main/Screenshots/Screenshot%202023-11-17%20at%208.16.44%E2%80%AFPM.png)

2. In the top left corner, in the search bar type "EC2" and select the EC2 Option

![](https://github.com/harsha-commit/devops-zero-to-hero/blob/main/Screenshots/Screenshot%202023-11-17%20at%208.18.21%E2%80%AFPM.png)

3. In the EC2 Dashboard, click on the "Instances" option

![](https://github.com/harsha-commit/devops-zero-to-hero/blob/main/Screenshots/Screenshot%202023-11-17%20at%208.20.46%E2%80%AFPM.png)

4. In the EC2 Instances Dashboard, click on "Launch Instances"

![](https://github.com/harsha-commit/devops-zero-to-hero/blob/main/Screenshots/Screenshot%202023-11-17%20at%208.22.38%E2%80%AFPM.png)

5. Name the instance and click on "Launch Instance" on the bottom right. As this is not an AWS course, we will skip the configuration options. Choose "Proceed with no key pair", if prompted

![](https://github.com/harsha-commit/devops-zero-to-hero/blob/main/Screenshots/Screenshot%202023-11-17%20at%208.23.50%E2%80%AFPM.png)

6. Within a few seconds, your VM is provisioned

![](https://github.com/harsha-commit/devops-zero-to-hero/blob/main/Screenshots/Screenshot%202023-11-17%20at%208.26.50%E2%80%AFPM.png)

7. Now terminate the EC2 Instance, by selecting the Instance and clicking on "Instance State"

![](https://github.com/harsha-commit/devops-zero-to-hero/blob/main/Screenshots/Screenshot%202023-11-17%20at%208.29.01%E2%80%AFPM.png)

## Option 2: Creating VMs using AWS APIs

- Using User Interface is suitable for smaller tasks, but creating and configuring multiple VMs becomes cumbersome. This also holds true for other AWS Services
- AWS provides APIs to interact with the AWS Services using scripts, which enables automation, thus enabling speed and efficiency
	- For example, for managing EC2 Instances, AWS provides AWS EC2 API
- The requests of scripts sent to an API must be valid and the User must be Authenticated and Authorized
- We can write scripts using
	- AWS CLI
	- AWS APIs
	- AWS CFT (CloudFormation Templates)
	- Terraform, etc


