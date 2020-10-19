# Level Up Lab Workshop: Introduction to Natural Language Processing


**Date: Tuesday, October 20, 2020, 12:00 PM PST**


This tutorial is a gentle introduction to Natural Language Processing (NLP) for those who have not used NLP methods and techniques before or have some minimal experience with them. 


We will start with a brief introduction to NLP concepts and terminology and then, we will walk you through some of the text preprocessing steps to prepare the provided dataset for further NLP modeling. If time permits, we will also show you a complete implementation of a sentiment analysis model. 


## Spark NLP

We will introduce an NLP library, named **[Spark NLP](https://github.com/johnsnowlabs/spark-nlp)**, and explain some of the concepts that shape the most recent and advanced NLP methods that are widely used today. More specifically, we will (very) briefly talk about what **pretrained models** and **transfer learning** mean, as well as how these concepts are integrated into Spark NLP. 

We will also walk you through how we can do sentiment analysis with this library. By the end of this session, you will have a better understanding of the more recent techniques and libraries used in NLP. 


Spark NLP is a self-contained library. It does not require you to download any other NLP library. Spark NLP is built on top of [Apache Spark](https://spark.apache.org/docs/latest/), which is a general-purpose in-memory distributed data processing engine, which makes Spark NLP a highly efficient NLP tool. If you would like to learn more about Spark NLP, please read [this](https://towardsdatascience.com/introduction-to-spark-nlp-foundations-and-basic-components-part-i-c83b7629ed59) and [this](https://medium.com/spark-nlp/introduction-to-spark-nlp-installation-and-getting-started-part-ii-d009f7a177f3) blog posts from one of the members of Spark NLP core dev team.


**Please follow the installation/setup steps below before the tutorial:**

+ Clone this repo into your machine by running `git clone https://github.com/ftarlaci/anitab-nlp-workshop` in your command line. 
+ Do a `git pull` before the workshop if you would like to follow along with us as we will be adding some of the workshop code files prior to the workshop. 

### Option 1: Setup by Using Google Colab 

We will be using Google Colab during the session. If you have not used Colab before, please follow the steps to set it up for the tutorial. 

1. If you don't have a gmail account, you will need to create one to be able to use Google Colab.
2. Login to your Google drive by going to drive.google.come, then click on `My Drive`. Inside My Drive, you will find a folder, named "Colab Notebooks". Click on this folder.  
    + If you don't see `Colab Notebooks` in your drive, on the left side of the screen, click on `New`, scroll down to `More`, and select `Google Colaboratory`. 
    + Note: you may need to click on `Connect more apps` if you do not see `Google Colab` listed.  You will then search for `colab` and install it into your google drive.  
3. Upload the "anitab-nlp-workshop" folder from inside this repository to Google Drive. This will upload the files you need for the tutorial on Colab. 
4. Navigate to the "anitab-nlp-workshop" folder that you have uploaded on Google Drive. To open up any notebook in Google Colab, right click on the notebook file and select "open with", then select Google Colab.



### Option 2: Setup by Using Jupyter Notebook

You can choose to use Jupyter Notebook, if you prefer to do so. If you do, install Spark NLP by following the installation steps below: 

You can install Spark NLP either with `pip` or `conda`

### Install Spark NLP from PyPI

`pip install spark-nlp==2.5.3`


### Install Spark NLP from Anaconda/Conda

`conda install -c johnsnowlabs spark-nlp`

+ If you would like to install spark-nlp into a conda environment (recommended), follow the steps below. In your terminal, type:

`java -version  #should be Java 8 (Oracle or OpenJDK)`  (If Java in your machine needs to be updated, see [this page](https://www.java.com/en/download/help/update_runtime_settings.xml))

`conda create -n sparknlp python=3.6 -y`

`conda activate sparknlp`

`pip install spark-nlp==2.5.3 pyspark==2.4.4`


After the installation, please make sure the following lines of code run in your Jupyter Notebook without any errors:

```yaml
import sparknlp
spark = sparknlp.start()
print("Spark NLP version")
sparknlp.version()
print("Apache Spark version")
spark.version
```

For more details about how to install Spark NLP on your machine, check out ths [blog post](https://medium.com/spark-nlp/introduction-to-spark-nlp-installation-and-getting-started-part-ii-d009f7a177f3).