# Sparkify
Udacity Data Science Capstone Project

## Table of Contents

1. [Motivation](#Motivation)
2. [Data](#Data)
3. [Required packages](#Requiredpackages)
4. [Results](#Results)
5. [Acknowledgements](#Licensing)

## Motivation<a name="Motivation"></a>

Sparkify is a music streaming service app (similar to Apple Music and Spotify) where customers can hear their favourite musics. This service can be used for free, but some customers prefer to have a premium (paid) account, which allows to eliminate advertising between songs and other benefits.
The purpose of this project is to predict the customer's churn based on their behavior and previous activities. 
For that purpose it was needed to understand data and then generate meaningfull features that characterize user experience in Sparkify, so that we can use a machine learning model to predict which customers are likely to churn.

The project is organized with the following structure:

1. Loading and cleaning data
   1. Load dataset
   2. Cleaning missing and invalid data
  
2. Exploratory Data Analysis
   1. Define Churn & Downgrades from the original features
   2. Explore data (comparing behaviours between both type of users: those who churned and those who didn't)

3. Feature Engineering
   1. Create new meaningful features for each user
   2. Create a function to perform all ETL tasks at once
  
4. Model training and Prediction
   1. Split data into training and testing data sets
   2. Train several classification models & Hyperparameter tunning with Grid Search
   3. Select best machine learning model based on f1score

## Data<a name="Data"></a>

The available data corresponds to the log of events, measuring every interaction and activity that users perform in the application. 
Every event is a row in the dataset and collects the following information:

root <br/>
 |-- artist: string <br/>
 |-- auth: string <br/>
 |-- firstName: string <br/>
 |-- gender: string <br/>
 |-- itemInSession: long <br/>
 |-- lastName: string <br/>
 |-- length: double <br/>
 |-- level: string <br/>
 |-- location: string <br/>
 |-- method: string <br/>
 |-- page: string <br/>
 |-- registration: long <br/> 
 |-- sessionId: long <br/>
 |-- song: string <br/>
 |-- status: long <br/>
 |-- ts: long <br/>
 |-- userAgent: string <br/>
 |-- userId: string <br/>
 
As an online service, the amount of data collected every minute is huge. 
For this reason, and due to the limitation of computational capacity to work with larger datasets, in this project we only used a medium sample, with about 4GB.

In this repository you can find the following files:

Udacity_Sparkify <br/>
 |-- Sparkify_medium_final.ipynb <br/>
 |-- Sparkify_medium_final.html <br/>
 |-- medium_sparkify_event_data.zip <br/>
 |-- mini_sparkify_event_data.zip <br/>

* Sparkify_medium_final.ipynb: Notebook with all the scripts used to analyse data and to address the churn prediction problem
* Sparkify_medium_final.html: Same notebook in .html format
* medium_sparkify_event_data.zip: meidum subset (4Gb) of the full dataset available (12GB) - must be unzipped!
* mini_sparkify_event_data.zip: small subset (128MB) of the full dataset available (12GB) - must be unzipped!

## Required packages <a name="Requiredpackages"></a>

The project was developed and tested on IBM Watson Studio Lite account (free). It allows to use a Jupyter notebook with Python 3.6 with Spark, which uses one driver with 1 vCPU and 4GB RAM, and 2 executors each with 1 vCPU and 4 GB RAM.

The following packages must be installed:
* Pyspark
* Pandas
* Datetime
* Seaborn 0.9+
* Matplotlib

## Results <a name="Results"></a>

To see in detail all the results and conclusions you can check this [medium post](https://medium.com/@margarida.ampf/how-do-you-know-that-your-customers-will-churn-even-before-they-know-it-1c377fa8adfa).

We trained 5 different classifiers, fine-tuning the hyper-parameters with Grid Search, and then compared 3 performance metrics. This was the outcome:






The best classifier was **Gradient Boosted Trees** with an ensemble of 5 decision trees, because it showed the best F1 score. With this we obtained an accuracy equal to 75,58% and an F1 Score equal to 0.7006.

Then we analyzed the importance of each variable, in order to understand which features have grater influence in user’s churn.



When looking at the feature importance, the **average number of songs per session** stands out. This means that customers who on average listen to less songs are more likely to churn. The second most relevant feature is the **number of thumb downs**. These types of events are good indications of customer dissatisfaction. The third most important feature also seems quite relevant, as it represents the **total number of sessions per user**.


## Acknowledgements <a name="Licensing"></a>

* Thanks to Udacity for all the useful insights and interesting challenges!
