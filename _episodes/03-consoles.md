---
title: "Storing data in the cloud"
teaching: 0
exercises: 30
questions:
- "What are the three primary ways of talking to the cloud?"
- "What are the main activities supported by cloud consoles?"
objectives:
- "Learn how to spin up an instance, install the AWS Cli and create an s3 bucket"
keypoints:
- "AWS is low-cost, feature rich, has widest use"
- "At a high level you want to know about EC2, S3 and IAM"
---

### Logging in to the AWS Console & Creating an EC2 instance
Log in to https://uwescience.signin.aws.amazon.com/console. Use th IAM Username and Password that was provided to you Account ID/Alias: uwescience

Once you are logged on the the console, on the right top hand corner next to your IAM username you will see a region. Please make sure that US-East(Ohio) is selected from the drop down menu. We will be solely using the Ohio region for Neurohackweek cloud work. 

Under Build a Solution, select Launch A Virtual Machine

Step 1: Choose an Amazon Machine Image (AMI)
Select Ubuntu Server 16.04 LTS (HVM), SSD Volume Type 

Step 2: Choose an Instance Type
Select t2.micro, click Next: Configure Instance Details

Step 3: Configure Instance Details
The only thing you will need to change is the IAM role. Select  *neurohacks3fullaccess* from the Drop Down List. IAM roles allow AWS resources to communicate with one another without the use of access keys. Click Next: Add Storage

Step 4: Add Storage
Change the Size to 25GiB. Click Next: Add Tags

Step 5: Add Tags
Key - Name, Value - neurohack-amandatan
Key - Owner, Value - neurohack-amandatan

Please append *neurohack* to your IAM username for all AWS resources you provision. This helps us keep track of the resources. 

Step 6: Configure Security Group
Select the Select an existing security group button 
Check the neurohackweek-SG button and click Review and Launch

Step 7: Review Instance Launch
Click Launch

The Select an existing key pair or Create a new key pair window will pop up.

From the drop down menu, select Create a new key pair. The key pair name will be *neurohack-IAMusername* 

Make sure to 


### Logging on to the EC2 instance, installing the AWS Cli and s3 buckets






