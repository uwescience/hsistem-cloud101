---
title: "Doing computations in the cloud"
teaching: 0
exercises: 40
questions:
- "What can we use a cloud machine for?"

objectives:
- "Learn how to install miniconda and related packages on your cloud machine"
- "Learn how to enable the Jupyter Notebook server on your cloud machine and access it from a browser"
- "Learn how to manipulate data stored on an s3 bucket"

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

``` bash Miniconda3-latest-Linux-x86_64.sh ```

Press spacebar to scroll through the manual. Answer yes to the prompts. After miniconda is installed, we want to make sure our conda path is updated. This can be done using:

```source ~/.bashrc```


**Step 2. Create a conda environment and all packages within the environment**

```conda create -n esip python=3.7```

```conda activate esip```

```conda install jupyter notebook```

```conda install matplotlib rasterio boto3```

It will take a while to get through these steps

**Step 3. Get Jupyter Notebook going**

```jupyter notebook --ip="0.0.0.0" ```

You will see something pop up that looks like this:

```
To access the notebook, open this file in a browser:
        file:///home/ubuntu/.local/share/jupyter/runtime/nbserver-2063-open.html
    Or copy and paste one of these URLs:
        http://(ip-172-31-36-8 or 127.0.0.1):8888/?token=90dcf8abfc8e205ff0bdac22c260bce9cb01e2f34d6545a8
  
 ```
 Copy the URL to the address bar of your web browser. Replace "localhost" with the Public IP of your Virtual Machine.      
We are using 0.0.0.0 here as the IP to enable ALL IP addresses to reach the notebook server. 

Step 4. Let's do some fun stuff with Jupyter Notebooks
Once you have Jupyter Notebook going, we will follow the steps outlined in this notebook: 
<https://github.com/amanda-tan/cloud101_aws_esip/blob/gh-pages/landsat_s3_ndvi.ipynb>

We will launch a new Python 3 notebook and do some plotting with rasterio 
