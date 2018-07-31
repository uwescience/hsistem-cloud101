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

### Pre-requisites
Mac: iTerm/Terminal 
Windows: [Windows bash](https://docs.microsoft.com/en-us/windows/wsl/install-win10), [Putty](https://www.putty.org)

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

Make sure to Download Key Pair. Note where the Key Pair is saved (for Mac/Linux, it is usually automatically saved to your Downloads folder). Once you have saved the Key Pair (e.g. neurohack-amandatan.pem), click Launch Instances.

You will see the Launch Status screen. Click on ID number associated with your instance. 

You will be taken to the EC2 dashboard. Look for the IPv4 Public IP. You will need this IP to ssh into your instance.  

### Logging on to the EC2 instance, installing the AWS Cli and creating s3 buckets

Open iTerm or Terminal (Mac) or Windows Bash and locate the Key Pair file you downloaded. Change the permission of the file using chmod 400. 

Log on to your instance with ssh: 

``` ssh -i "neurohack-amandatan.pem" ubuntu@52.14.247.95 ```

Once logged on, update and upgrade packages and install the awscli:

``` sudo apt update ```

``` sudo apt upgrade ```

``` sudo apt install awscli```

To list bucket contents (this will list ALL the s3 buckets in the account): 

``` aws s3 ls ```
 
 To create a new bucket (please use *neurohack-IAMusername*)

``` aws s3 mb s3://neurohack-amandatan```

You should now be able to see your bucket when you list the bucket contents again. 

### Uploading a file to s3 via console and uploading to EC2 instance, etc. 






