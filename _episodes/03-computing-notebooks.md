---
title: "Doing computations in the cloud"
teaching: 0
exercises: 35
questions:
- "What can we use a cloud machine for?"

objectives:
- "Learn how to get data from S3 onto your machine and what to do once it's there"
- "Set up a Jupyter notebook server on your cloud machine"

keypoints:
- "Anything you can do with your desktop (almost), you can do with your cloud machine"
- "For interactive stuff, you can set up Jupyter to run on that machine"
---

### How to do computations on your cloud machine

Now, we have data inside our cloud machine. Let's see how we can do some
computing with this data.

To install Python-related software, we'll make sure that our machine has the packages required for us to work with. 

**Step 1. Install miniconda**
``` wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh```

Answer Y to the prompts. 


**Step 2. Create a conda environment and all packages within the environment**

```conda create -n esip python=3.7```

```source activate esip```

```conda install matplotlib rasterio boto3```


**Step 3. Get Jupyter Notebook going**

```jupyter notebook```


Step 4. Let's do some fun stuff with Jupyter Notebooks
Once you have Jupyter Notebook going, we will follow the steps outlined in this notebook: 
<https://github.com/amanda-tan/cloud101_aws_esip/blob/gh-pages/rasterio-landsat-aws.ipynb>
