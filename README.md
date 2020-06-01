# predicting-mental-health-reddit
**Individual Capstone Project (5 weeks)**

The goal of this project was to predict four mental health disorders (anxiety, depression, bipolar & suicide) from Reddit posts using Natural Language Processing.  

**Visualise the results in /Visuals/All_Visuals.md**

## Table of Contents
- [Introduction](#introduction)
- [Data Collection & Pre-Processing](#data-collection---pre-processing)
- [Natural Langauge Processing & Modelling](#natural-langauge-processing---modelling)
- [Lime Implementation](#lime-implementation)
- [Future Work](#future-work)
- [Notebook Order](#notebook-order)

## Introduction
Mental Health is becoming more and more of a prominent issue - one in four people will be affected by a mental or neurological disorder at some point in their life. And yet, it is still a difficult subject for many to talk about. 

Because Reddit facilitates annonomous posting, authors don't hold back about their mental health struggles; and so Reddit provides a large amount of accurate data to analyse. 

## Data Collection & Pre-Processing
There is a large dataset of Reddit posts on Google BigQuery (fh-bigquery/reddit_posts) going back until 2015 from which over one million data points were taken from a four-year period. 

The cleaning of these posts was acheived using the following steps:
- Removing 'deleted/removed' posts  
- Removing symbols, numbers, blank lines etc.  
- Spell checking the corpus  
- Lemmentisation  

After cleaning, around 800,000 datapoints were left; the majority class (depression) had 53% of the total datapoints whereas the minority class (bipolar) had 9%. 

Sub-Reddit | Distribution
------------ | -------------
r/depression | ~53%
r/SuicideWatch | ~20%
r/Anxiety | ~18%
r/bipolar | ~9%

## Natural Langauge Processing & Modelling
Part of Speech tagging and Sentiment Analysis (Vader) were implemented and the models were trained using both tfidf and Word2Vec on several classifiers. All models beat the baseline of 53%.

<img src = "/Visuals/png/results_bar.png" width="700">

## Lime Implementation
Lime shows how the tfidf model came to its prediction. The following post is interesting as the model is very close to predicing the post as r/SuicideWatch but correctly classifies it as r/depression. 

<img src = "/Visuals/png/lime.png" width="750">

## Future Work
- Oversampling using SMOTE (NC)
- Only use posts with a minimum number of words in it (the more words a post has the more sure the model is of its classification)
- Try Doc2Vec implementation with sentance structure
- Clustering
- Predict likelyhood of an author posting on r/SuicideWatch given what they have posted in the other three subreddits. 

## Notebook Order
1. Pre-Processing.ipynb  
2. NLP.ipynb  
3. tfidf Model.ipynb / Word2vec model.ipynb  
4. Lime_tfidf.ipynb