---
title: "Doing computations in the cloud"
teaching: 0
exercises: 30
questions:
- "What are the three primary ways of talking to the cloud?"
- "What are the main activities supported by cloud consoles?"

objectives:
- "Learn how to spin up an instance, install the AWS CLI and create an s3 bucket"

keypoints:
- "AWS is low-cost, feature rich, has widest use"
- "At a high level you want to know about EC2, S3 and IAM"
---

### How to do simple computations on your cloud machine

Here, we're going to install nibabel and numpy on our machine and
show that we can read some data and do some computations

### How to get a Jupyter notebook running on the cloud

Here, we install jupyter and configure it to run a notebook server

### How to get HCP data into your machine

Here, we get credentials, we upload them into our machine and use the
CLI to get data down.

#### `boto3` is a library that talks to AWS for you

Here, we start up jupyter on this machine, and run some boto code, to
automate things