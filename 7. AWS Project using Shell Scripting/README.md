# Day 7 - AWS Project using Shell Scripting

## Task: Report the Resource Usage of AWS 

### Objective of the Project

- To track the usage of AWS Resources enabling informed decision-making regarding resource allocation, cost optimization, and service utilization patterns

### Services Monitored by the Project

- AWS EC2
- AWS S3
- AWS Lambda
- AWS IAM

### Prerequisites

1. Create an AWS EC2 Instance
2. SSH into the EC2 Instance 
3. Configure AWS CLI (in case you didn't)
4. Create a script file `vi aws_resource_tracker.sh`
5. Give all permissions to the file `chmod 777 aws_resource_tracker.sh`
6. Create a report file `touch resources_tracker_report`

### Project Shell Script

```sh
#!/bin/bash

########################
# Author: Harsha Vardhan Bashavathini
# Date: 19/11/2023
# Version: v1
# Description: This scripts reports the resource usage of some AWS Services
########################

# Debug Mode
set -x

# AWS S3
echo "Print list of S3 Buckets"
aws s3 ls >> resources_tracker_report

# AWS EC2
echo "Print list of EC2 Instances IDs"
aws ec2 describe-instances | jq '.Reservations[].Instances[].InstanceId' >> resources_tracker_report

# AWS Lambda
echo "Print list of Lambda Functions"
aws lambda list-functions >> resources_tracker_report

# AWS IAM Users
echo "Print list of IAM Users"
aws iam list-users >> resources_tracker_report
```

### Steps to Run

1. Open project script file  `vim aws_resource_tracker.sh`
2. Copy the Project Shell Script into the file 
3. Install Crontab 
	1. `sudo yum install cronie -y`  for Amazon Linux
	2. `apt-get install cron` for Ubuntu
4. Edit Crontab `crontab -e`
	1. Copy `0 17 * * * /bin/sh aws_resource_tracker.sh` into the editor
	2. Save and Exit (Esacape + :wq!)
5. Based on the cron expression, the script will run on specified times

### Resources Used

- https://docs.aws.amazon.com/cli/latest/
- https://www.freecodecamp.org/news/cron-jobs-in-linux/