---
title: "Lambda S3 and EC2"
teaching: 40
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


## EC2


As we move from the basics into actually implementing there are two future ideas we want to emphasize.


1. You will want to have a good plan for 'How do I do this on my own?'
2. When stuff does not work: You will want to have some tools for figuring out why


In the latter case setting up a lambda function is a good exercise in 'How do I debug?' as we shall see.


Let's start up an EC2 instance with these objectives
- What the types mean
- What the operating systems mean
- What the key pair is and how it is used
  - Why my personal public/private keys are not used here but are used elsewhere
- What block storage means and costs
- What stopping does
- What terminating does
- What CloudWatch is
- What CloudTrail is
- What EFS is

- EC2 stands for AWS Virtual Machine that you pay for by the hour
- How do I interact with the Amazon cloud? Four answers: Console, command line, app, API
  - The console appears in your browser. You authenticate, navigate, wizardize, adjust, repeat
  - The command line you install on your local machine... and you will need to help it authenticate
  - The app is an app you install from the internet... and you will need to help it authenticate
  - The API is (in Python) something called boto. It permits you to do stuff on the cloud from within your Python code.
    - Substitute your favorite alternative language here if you are not a Pythonista
- Why do I have to interact with the Amazon cloud? 
  - Actually our goal is to make the cloud vanish so you can get on with your work and life. 


## S3


- S3 stands for Something Simple Storage System and So-on
- S3 buckets live in AWS Regions and have infinite capacity per bucket
- They are not file systems although they can be seen in this light


- I set up a bucket in advance called cloud101awsbucket


## Lambda


#### Preamble 1: Living in the Wild West

I tried to set up a lambda function to send me email under two different circumstances. This proved to be 
very effective in forcing me to develop a couple of debugging tools and principles. To begin such a list:


1. In the console explore all of the tabs belonging to an **Entity**. 
2. Pose basic questions and consult StackOverflow (etc) answers *casually*.
3. Explore links on an Entity's tab system; particularly ones that point to ***View Cloudwatch logs***
4. When you copy and paste example code make sure you run through all the code to substitute your versions
5. Understand the *region* basis for the AWS cloud


#### Preamble 2: boto3 and the AWS CLI


The command line interface or CLI is a useful tool for manipulating your AWS account from the
command line... including your local machine. 


On windows you may be accustomed to using Power Shell and this proved to be a bad idea over the weekend.
The Command Prompt window worked fine. 


boto3 is the Python library for talking to AWS. It includes the capacity to authenticate so that you
can do what you want to because AWS believes it is really you. This brings up the important topic
of GitHub.


#### Setting up a lambda function


- [Lambda documentation](http://boto3.readthedocs.io/en/latest/reference/services/lambda.html)
- [Invoke lambda from the command line](http://docs.aws.amazon.com/lambda/latest/dg/with-userapp-walkthrough-custom-events-invoke.html)
- We want a lambda function to operate as an agent; e.g. sending an email
- AWS Simple Notification Service (SNS) is one approach
  - [Here is a tutorial for this.](http://docs.aws.amazon.com/lambda/latest/dg/with-sns-example.html)
- AWS Simple Email Service (SES) is more to the point
- Because lambda is acting automatically on your behalf it needs permissions (2 IAM jargony terms needed)
  - Role: A construct assigned to your lambda
  - Policy: Actual code (JSON) attached to this Role
  - A lambda service can be set up so that anyone can run it 
    - This is not recommended so I do it
- Setting up SES requires us to use the LHS navigator to test an email


[A blog for the setup](http://www.wisdomofjim.com/blog/sending-an-email-from-aws-lambda-function-in-nodejs-with-aws-simple-email-service)


- Notice this does not actually tell us how to run the thing
- Notice that we can add triggers but the proper verb to run the thing is **invoke**
- Notice that a careful scan of the javascript code is imperative
- Notice that this is not Python... so a Python version would be better 


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



