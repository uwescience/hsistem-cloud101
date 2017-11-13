---
title: "Lambda S3 and EC2"
teaching: 15
exercises: 0
questions:
- "What is S3?"
- "What is EC2?"
- "What is Lambda?"
objectives:
- "Having a working knowledge of lambda, EC2 and S3"
- "Know how to navigate to **Fire It Up** web pages"
- "Know the distinction between object storage and block storage"
keypoints:
- AWS provides storage and virtual machines; and supports little task-oriented creatures called Lambda functions
- Visit us (eScience cloud) during office hours or by arrangement to carry this further
---

### EC2


- EC2 stands for AWS Virtual Machine that you pay for by the hour
- How do I interact with the Amazon cloud? Four answers: Console, command line, app, API
  - The console appears in your browser. You authenticate, navigate, wizardize, adjust, repeat
  - The command line you install on your local machine... and you will need to help it authenticate
  - The app is an app you install from the internet... and you will need to help it authenticate
  - The API is (in Python) something called boto. It permits you to do stuff on the cloud from within your Python code.
    - Substitute your favorite alternative language here if you are not a Pythonista
- Why do I have to interact with the Amazon cloud? 
  - Actually our goal is to make the cloud vanish so you can get on with your work and life. 


### S3


- S3 stands for Something Simple Storage System and So-on
- S3 buckets live in AWS Regions and have infinite capacity per bucket
- They are not file systems although they can be seen in this light


- I set up a bucket in advance called cloud101awsbucket


### Lambda


- [Lambda documentation](http://boto3.readthedocs.io/en/latest/reference/services/lambda.html)
- [Invoke lambda from the command line](http://docs.aws.amazon.com/lambda/latest/dg/with-userapp-walkthrough-custom-events-invoke.html)
- We want a lambda function to operate as an agent; e.g. sending an email
- AWS Simple Notification Service (SNS) is one approach
  - [Here is a tutorial for this.](http://docs.aws.amazon.com/lambda/latest/dg/with-sns-example.html)
- AWS Simple Email Service (SES) is another
- Because lambda is acting automatically on your behalf it needs permissions (2 IAM jargony terms needed)
  - Role: A construct assigned to your lambda
  - Policy: Actual code (JSON) attached to this Role


#### Invoke cloud101 lambda from the command line


```
aws lambda invoke --function-name cloud101 --region us-east-1 outputfile.txt
```


#### Invoke cloud101 lambda from Python on my local machine

```
import boto3
client = boto3.client('lambda')
return_dict = client.invoke(FunctionName='cloud101')
```


#### Invoke cloud101 lambda from Python on a cloud-based JupyterHub


Note comments at top indicating some preliminary steps to get boto running. 
Boto is the Python library that 'speaks' the AWS API language.


```
# To get this working it was necessary to...
#   open up a terminal from the main JHub console
#   from there run $ pip install boto3
#   from there run $ aws config
#                      enter my public key
#                      enter my secret key
#                      stipulate a default region of us-east-1
#                      stipulate output as json
#   stipulate region_name='us-east-1' in the client generation
import boto3
client = boto3.client('lambda', region_name='us-east-1')
return_dict = client.invoke(FunctionName='cloud101')
print(return_dict)
```



