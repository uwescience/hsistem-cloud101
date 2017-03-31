---
title: "Cloud adoption framework"
teaching: 20
exercises: 0
questions:
- "What is our cloud framework?"
- "How does this map to my research?"
objectives:
- "Understand the cloud framework we present"
- "Map your personal perspective and objectives to this course"
keypoints:
- "There is a framework for the cloud that includes { yourself, colleagues, vendors, stacks, and third parties (open/closed) }"
- "The stack is five components { compute, store, manage, web, service }"
- "'Service' is just providing the other four components free of underlying concerns like VMs ('Dinner with no plates and no table')"
---

### cloud101 is *open*

![red queen](/cloud101_intro/fig/redqueen.png)

The course can accommodate only a limited number of participants.  We are committed to 
providing our materials openly through a public website. Our call to action: 
Share awareness of this course and the eScience Institute with your colleagues.

### Your way foreward after today's coursework 

- Bookmark [cloud maven](http://cloudmaven.org)
- Bookmark [this course](https://cloudmaven.github.io/documentation/rc_cloud101_immersion.html) 
- Share this course with colleagues
- Visit the Data Science Studio: Office hours including cloud vendors
- Search engines, YouTube, StackOverflow, UW Help
- Remember that the vendors are highly motivated to help you: Online and in person
- Know about, even use: GitHub, Jupyter, Django
- Apply for research computing credits on the platform of your choice
- Set up your cloud account, build your environment, get back to your research


### What this course is 

- A description of how you choose a cloud platform
- Elements of implementing your research on the cloud
- Overview of security, cost, account management, processing power and time value
- Hands-on: Build a web app
- Hands-on: Build a compute cluster
- Enthusiasim: Researcher advocacy and the eScience Institute


> ## Challenge (click arrow to the right to open)
>
>  - What is the Google technology called 'TensorFlow' about?
>  - What is the corresponding Microsoft Azure technology?
>  - For AWS?
>
>
>  - Link for [Google Tensor Flow](https://www.tensorflow.org/).
>  - Link for [Microsoft Azure ML Studio](https://studio.azureml.net/)
>  - Link for [AWS ML](https://aws.amazon.com/machine-learning/)
{: .challenge}


### What it isn't


- A comprehensive overview of managing a public cloud account 
- A license to jump onto the public cloud and start creating massive compute jobs
- An advertisement for some particular cloud vendor 
- Extensive comparison with **BAM** or UW HPC computing 


### Two severe weather advisories


> ## The burden of cloud management is on each of us
> There is considerable detail to learn and the cloud can quickly become expensive if 
> you accidentally allocate utility resources and allow them to keep running. They will 
> run up your bill. Cloud instances can be turned off without losing state/progress.
{: .callout}


> ## Lemons from lemonade
> A good way of getting some bad news is to publish **and then delete** your cloud 
> access credentials on GitHub. GitHub supports versioning: Someone who is not your 
> friend can roll back your public repository to the version where the key was 
> present, grab that key, and start using your cloud account at your expense.  
{: .callout}


### Our Public Cloud Framework


This *framework* is the vocabulary and relationships we use to describe using the public
cloud platform for data-driven research. Here comes the jargon storm.


You do perfunctory processing and exploratory processing. The cloud can help you with
both of these at the expense of the time you must invest to learn new methods. We call
this *cloud adoption*.  Cloud adoption is awareness + learning + matching the tech to your 
work and implementation.  Our goal is to reduce your time pie chart slices that detract 
from your research slice.  We can also introduce you to doing things that might be new
like publishing your data and software as an executable paper.


#### The cloud components are compute, store, manage, web and services


  - Compute = VM = 'instance' = a computer = AWS EC2 = Azure VM = Google Compute Engine


    - Compute means 'instance + OS + memory + pre-installed tools + ...'
    - Compute as a service example: AWS Lambda
    - Third parties like GitHub provide 98% solutions: The task is finding them


  - Storage = S3 = Blob = Google Cloud Storage (and Google Drive)


    - 0.024 dollars per GB-month (and x 1/2 and x 1/4 for archival applications)


  - Manage = Databases... SQL, Not Only SQL... Data Warehouses... query machinery


  - Web = Web services, web sites, APIs, Clients, confederation, ...


  - Services = All of the above simplified: Often no Compute involved


#### The cloud facets to learn about are admin, cost, security, scale and time


- Admin is easy to dismiss; but it is always present, even on the cloud


  - When we reconstitute an AWS AMI we habitually run this command:


```
% sudo yum update
```


  - You can keep your cloud environment up-to-date without becoming a sysadmin


- Cost is 'one penny per processor-hour and three pennies per GB-month'
  - ...but there are more details...
  - ...and there are cost calculators... which can be misleading...
  - ...so we recommend these steps, for example for grant writing
    - Do a Back Of The Envelope (use cloudmaven.org or our office hours)
    - Start with a budget total target and work backwards 
    - Use calculators but be prepared to be skeptical of your results
    - Pad your estimate because things may go wrong
    - Remember that the cloud does not 


- The cloud is secure provided you manage your credentials
    - keep them out of GitHub (which can be rolled back)
    - Use MFA
    - Follow other standard procedures
    - If you are going over to PHI / HIPAA there is a whole 'nother level to this


- The cloud is cost-competitive with traditional **buy and maintain** (**BAM**)
  - This in part depends on your percent usage: Machine time / wall clock time
    - Studies indicate the breakeven is currently around 50%
  - The cloud *crushes* **BAM** on your wall clock time
    - Start wait is zero


### Should I move to the cloud?


This really depends on the value of your time in relation to your research budget; and on how 
much of your wall clock time you spend doing computing.  It also depends on your team's capacity 
to assess and learn cloud tech for your work. This might be very fast - which is what we find in
the majority of cases - but if you are getting into sophisticated work e.g. using a web framework
then there could be a substantial bootstrapping effort required. 


  - You are the protagonist in the play
  - The other actors are funding agencies, cloud vendors, third party providers
  - There is your domain-specific community 
  - There is the open source development community. They may have built 98% of what you need.


Our call to action is: 'Learn enough to learn enough to learn enough... to evaluate cloud migration.'
The simplest approach is to visit us by appointment or during drop-in office hours. 


### Which Cloud Should I Use?


"It depends..." and here are some factors.


- In your field of study: Are certain cloud providers in favor? For compelling reasons? 
- What sort of compute power are you looking for? Single machines? cluster? GPU? FPGA? HTC? HPC? 
- Cost: Per machine, en masse, Spot (bidding) market, reserved VMs, dedicated VMs for security, ...
- Compare your compute tasks with case studies at [cloudmaven.org](http://cloudmaven.org)
- Be aware of credit programs: Azure and AWS; Google may follow soon...
- Be aware of cost tracking and billing as a way to validate your cost estimates
- Development tools for the different clouds
- What services do the vendors provide that may make life much simpler?  
- Docker: Your first key to migrating from one cloud to another


|Category|AWS|Azure|Google|
|---------|:--------:|-----:|
|vCPU hour|before|you|ask|
|storage GB-month|the|shadow|knows|
|5900 vCPUs x 53 hours|3400|who|knows|
|something|what|evil|lurks|
|else|in|the|hearts|
|entirely|of|men|????|


### Questions to look over, call out and discuss


- "What do we mean by 'Data Intensive Science'?"
- "What are Web Apps, Clients and Servers?"
- "What is Django?"
- "What is Elastic Beanstalk?"
- "What is cluster computing?"
- "Where does this course get us? (hint: Not carte blanche!)"
- "What does this course cover? *not* cover?"
- "What is the post-course strategy for filling in and building up cloud skills?"



