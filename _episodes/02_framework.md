---
title: "Cloud adoption framework"
teaching: 20
exercises: 0
questions:
- "What do we mean by 'Data Intensive Science'?"
- "What are Web Apps, Clients and Servers?"
- "What is cluster computing?"
- "Where does this course get us? (hint: Not carte blanche!)"
- "What does this course cover? *not* cover?"
- "What is the post-course strategy for filling in and building up cloud skills?"
objectives:
- "In 15 minutes get a sense of where we are going today and what my post-today strategy should be."
- "Level set on cloud pillars, providers and platforms"
- "Understand the cloud adoption framework (awareness to instance to abstraction)"
keypoints:
- Cloud adoption is a matter of awareness, learning, matching the tech to your work and implementation.
  - 'matching the tech to your work' we abbreviate as 'mode'
- The five cloud pillars are compute, store, manage, web and services
  - Compute means 'instance and then...' 
    - **instance** just means 'a computer'
    - **and then** is often abstracted out (by vendors) into services
    - ...and *services* can extend to things like web frameworks and other '98% solutions'
- You the researcher have a pie chart of time 
  - We are here to maximize the **research** slice 
  - You are busy and you do both perfunctory and exploratory computations on your data
    - Cloud tech has something to offer you inside the realm of what you already do
    - The eScience Institute probably has something to offer you outside the realm of what you do
    - We will try and touch on both of these today
- The cloud is cost-competitive with traditional **buy and maintain** (**BAM**)
  - But the cloud *crushes* **BAM** on time
  - So 'Should I move to the cloud?' depends on
    - the value of your time in relation to your research budget
    - your team's capacity to learn cloud tech for your work
- Final part of the framework is a (humans-versus-nature) play metaphor
  - You are the protagonist
  - Other actors: Funding agencies, cloud vendors, third party providers
  - Finally there is your community and there is the open source development community
---

### cloud101 is *open*

![red queen](/cloud101_intro/fig/redqueen.png)

The course can accommodate only a limited number of participants.  We are committed to 
providing our materials openly through a public website. Our call to action: 
Share awareness of this course and the eScience Institute with your colleagues.

### Your way foreward after today's coursework 

- Bookmark this course so you will have the rest of this list available
- Share this course with colleagues
- Visit the Data Science Studio
- Bookmark [http://cloudmaven.org](http://cloudmaven.org), a **link reference site**
- Remember search engines, YouTube and KB resources like StackOverflow
- Remember that the vendors are highly motivated to help you: Online and in person
- Know about help@uw.edu
- Learn GitHub and Jupyter if you haven't already; and know what Django is
- Triage your research computing: Cloud? Mode? Platform? 
- Apply for research computing credits on the platform of your choice

### What this course is / isn't

#### Is

A description of how you choose a cloud platform... 

Some elements of how you approach implementing your research on the cloud

An overview of security, cost, account management and processing power

Hands-on: Build your web app

Hands-on: Build a compute cluster

Researcher advocacy

Get to know about the eScience Institute

#### Isn't

- A comprehensive overview of managing a public cloud account 
- A license to jump onto the public cloud and start creating massive compute jobs
- An advertisement for AWS or some other cloud vendor 
- Comparisons with **BAM** or UW HPC computing 

There is considerable detail to learn and the cloud can quickly become expensive if 
you accidentally allocate utility resources and allow them to keep running. They will 
run up your bill. Cloud instances can be turned off without losing state/progress.

A good way of getting some bad news is to publish **and then delete** your cloud 
access credentials on GitHub. GitHub supports versioning: Someone who is not your 
friend can roll back your public repository to the version where the key was 
present, grab that key, and start using your cloud account at your expense.  

### Markdown 

text based, so you can write exactly what you intend to say.

If you want to introduce a block of code into your lesson, write a block
fenced by triple-tilde. Here is an example of that

~~~
import nibabel as nib
img = nib.load('my_file.nii.gz')
affine = img.affine
~~~
{: .python}

```
On the other hand I was taught triple back-apostrophes work.
I wonder what this syntax means (outside the block quote): 

{: .python}
```

Images can be embedded into the lesson plan, by using the following syntax:

![an image]({{site.root}}/fig/ghw-logo.jpg)

To embed images, you will also want to copy the image file into the
`fig` folder of the repo, and add that.

> ## Exercises and challenges (click on the arrow to the right to open)
>
>  Boxes with "challenges" can be interleaved with the lesson materials.
>  Consider adding a challenge every 15 minutes or so.
>    - This helps participants stay engaged.
>    - It surfaces questions that learners have as they go along.
>    - It breaks up the instruction, providing a bit of a diversion.
>    - It gives people a chance to engage in peer instruction, which is
>      is [known to help learning](https://en.wikipedia.org/wiki/Peer_instruction).
{: .challenge}


> ## Callouts
> If you want to introduce a box with a "callout", use this syntax
> This is useful for materials that you think of as explanatory asides
> I usually use this for extra material that is "optional".
{: .callout}
