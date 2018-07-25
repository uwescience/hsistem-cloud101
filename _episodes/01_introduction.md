---
title: "Introduction"
teaching: 15
exercises: 0
questions:
- "Why and when should we use the cloud?"
- "Who is / are AWS?"
objectives:
- "Learners will describe advantages and disadvantages of the cloud"
- "Learners will analyze their use-cases for suitability for cloud computing"
keypoints:
- "The cloud provides on-demand access to infinite computational resources"
- "Resources need to be carefully managed, because charges are usually tied to how long resources are held"
- "The cloud is great for bursty, high-volume computing, or for some small services you might want to run"

---

## What is cloud computing?

Cloud computing encompasses a large collection of publicly available services provided by many different companies where you can provision computing on machines that are *only* accessible to you through an intermediated interface (such as a web-browser or through ssh).

These types of services range from things like Google Drive or Dropbox, that provide access to storage through a browser, to services that give you access to a linux-installed bare metal machine ("bare metal" means that you get the entire machine to yourself, you are the "single tenant" of this machine).

This contrasts with buying your own desktop or laptop computer, or cluster of machines, or with buying external storage devices (such as a RAID, redundant array of independent disks). It also contrasts with some services that are not publicly accessible, such as institutional clusters, and the [XSEDE](https://www.xsede.org/) services, that may also only be accessible to you through an intermediated interface.

## Why use the cloud?

### There are about six advantages to using the public cloud as a research platform.

1. You do not wait for compute tasks to go through a queue
    Compute can start as soon as you want it
2. You do not purchase and maintain hardware, operating systems etcetera
    Upgrades just happen
3. You pay for resources you use; and then shut them off
    You don't have to buy into an institutional cluster if the cost calculation doesn't make sense for you.
4. You have huge scale-up potential (reduced processing time)
    In principle, you have near-infinite computing capacity.
5. There is a huge support community rapidly expanding cloud tools and tech
    Because of the public availability of these resources, and substantial buy-in from industry, there is a large eco-system of tools and resources.
6. Storage, reliability, security and many other off-the-shelf services
    They keep making new stuff.

### There are about four reasons to not migrate to the cloud

1. You have already identified an adequate-to-your-needs computing environment like XSEDE
    Sometimes it just doesn't make sense. In some cases, you already have the access to the resources you need.
2. You don't have time to learn how to work on the public cloud
    There is stuff to learn. That's what we're here for! But there will be more to learn after this session is over. If you prefer to learn other things, you might not want to invest your time in learning about the cloud.

![red queen](/cloud101_aws/fig/redqueen.png)

3. You operate your computer(s) at a very high duty cycle (more cost-effective)
    If your computer is constantly computing something, the cloud might end up costing you more.
4. There is too much administrative drag preventing you from using the cloud
    That's a thing. Especially when working with human subject data that is encumbered through regulation (such as HIPAA).
