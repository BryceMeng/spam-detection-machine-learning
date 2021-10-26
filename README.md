# Spam detection using ML

Hao Meng 2020.7

Rewrite in the notebook in 2021.10


## Introduction

In my previous notebook, I analyzed how to detect malware using Supervised learning of machine learning. In this notebook, I will discuss how to detect spam emails using machine learning. 

Detection of email is different from malware as email only has some words. 

In research from Graham (2002), he got a high accuracy of spam email detection by Naive Bayesian filter. I will briefly explain the principle of the Naive Bayesian filter. 

**1. Bayesian Inference**

In general, it is conditional probability. For example. In total, the probability of rain in tomorrow is 0.3. However, if many clouds appear in today's evening, the probability of rain in tomorrow will increase to 0.5. The condition is that colouds appear in the evening of previous day.

In spam email detection, we assume the probability of the spam email is 0.5. However, if "sex" appears in email, the probability of the spam email will increase to 0.8. We can statstic the probability of some key words similar to "sex" from all samples emails.

**2. Naive Bayesian**

It can't just judge whether it is a spam email by one word. There are more keywords like "Gamble," "smoke," and so on. If every word's conditional probability is independent, the Bayesian Inference method will be transferred to the Naive Bayesian Inference method. And the function of the combine probabilities is:

![Combine Probabilities](https://chart.googleapis.com/chart?cht=tx&chl=P%3D%5Cfrac%7BP_%7B1%7DP_%7B2%7D%5Ccdot%20%5Ccdot%20%5Ccdot%20P_%7B15%7D%7D%7BP_%7B1%7DP_%7B2%7D%5Ccdot%20%5Ccdot%20%5Ccdot%20P_%7B15%7D%2B(1-P_%7B1%7D)(1-P_%7B2%7D)%5Ccdot%20%5Ccdot%20%5Ccdot%20(1-P_%7B15%7D)%7D&chs=70)

The P with a subscript represents one word's condition probability, and in the function, there are 15 words to calc the spam probability together. Later more words can be added to the function.

### Dataset

This notebook will use Ling-Spam Dataset provided by Ion Androutsopoulos(https://www.kaggle.com/mandygu/lingspam-dataset?rvi=1).


### Reference Materials

In this notebook, I will use the feature engineering method mainly from the notebook(https://www.kaggle.com/surekharamireddy/spam-detection-with-99-accuracy).

### Flow

1. Feature engineering
2. Vectorlize
3. Analysing by some models
4. Analysing by Naive Bayesian model


**Reference**
Graham, P. (2002, August). A Plan for Spam. Paul Graham. http://www.paulgraham.com/spam.html
