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
  - Actually our goal is to *not* interact with the cloud; but rather to make the cloud vanish so you can get on with your work and life. 


### S3


- S3 stands for Something Simple Storage System and So-on
- S3 buckets live in AWS Regions and have infinite capacity per bucket
- They are not file systems


- I set up a bucket in advance called cloud101awsbucket
- 


### Lambda


- [Lambda documentation](http://boto3.readthedocs.io/en/latest/reference/services/lambda.html)
- We want a lambda function to operate as an agent; for example sending an email
- AWS Simple Notification Service (SNS) permits us to send emails and such 
  - [Here is a tutorial for this.](http://docs.aws.amazon.com/lambda/latest/dg/with-sns-example.html)
- Because lambda is acting automatically on your behalf it needs permissions (2 terms needed)
  - Role: A construct assigned to your lambda
  - Policy: Actual code (JSON) attached to this Role



### Prerequisites


- Establish a free tier account on AWS
- Note down your password in a safe location
