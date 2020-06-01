# predicting-mental-health-reddit
**General Assembly Capstone Project (6 weeks)**


## Introduction
Mental Health is becoming more and more of a prominent issue - one in four people will be affected by a mental or neurological disorder at some point in their life. And yet, it is still a difficult subject for many to talk about. People tend to try and hide this side of them from the rest of the world which is rediculous, you wouldn't be embarassed about going to the doctor after breakng your leg right?

Because Reddit facilitates annonomous posting, most people don't hold back when posting about their mental health struggles and so this gives us a large amount of accurate data to analyse. 

The goal of this project was to predict four mental health disorders (anxiety, depression, bipolar & suicide) from Reddit  posts using Natural Language Processing.


## Data Collection

One option would be to scrape Reddit using PRAW - however, this is quite time consuming... Luckily, there is a large dataset on Google BigQuery (fh-bigquery/reddit_posts) going back until 2015. Over a million rows were taken over a four year period

## Pre-Processing

The cleaning of these posts was acheived using the following steps:

Removing 'deleted/removed' posts
Removing symbols, numbers, blank lines etc.
Spell checking the corpus 
Lemmentisation

After the text had been cleaned, around 800,000 datapoints were left, the majority class (depression) had 53% of the total datapoints whereas the minority class (bipolar) had 9%. 

Sub-Reddit | Distribution
------------ | -------------
r/depression | ~53%
r/SuicideWatch | ~20%
r/Anxiety | ~18%
r/bipolar | ~9%

## Natural Langauge Processing & Modelling

Part of Speech tagging and Sentiment Analysis (Vader) were implemented and then the models were trained using both tfidf and Word2Vec. All models beat the baseline of 53%.

<img src = "results_bar.png" width="750">

<img src = "ROC.png" width="600">

## Results

