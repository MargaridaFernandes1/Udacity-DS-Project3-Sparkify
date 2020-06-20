# Sparkify
Udacity Data Science Capstone Project

## Table of Contents

1. [Motivation](#Motivation)
2. [Data](#Data)
3. [Required packages](#Requiredpackages)
4. [Results](#Results)
5. [Screenshots](#Screenshots)
6. [Acknowledgements](#Licensing)

## Motivation<a name="Motivation"></a>

Sparkify is a music streaming service (similar to Apple Music and Spotify) where customers can hear their favourite musics. This service can be used for free, but some customers prefer to have a premium (paid) account, which allows to eliminate advertising between songs and other benefits.
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

`root
 |-- artist: string
 |-- auth: string 
 |-- firstName: string 
 |-- gender: string 
 |-- itemInSession: long 
 |-- lastName: string 
 |-- length: double
 |-- level: string 
 |-- location: string 
 |-- method: string 
 |-- page: string 
 |-- registration: long 
 |-- sessionId: long
 |-- song: string 
 |-- status: long 
 |-- ts: long 
 |-- userAgent: string
 |-- userId: string` 
 
As an online service, the amount of data collected every minute is huge. 
For this reason, and due to the limitation of computational capacity to work with larger datasets, in this project we only used a medium sample, with about 4GB.

In this repository you can find the following files:
`Udacity_Sparkify
 |-- Sparkify(IBM).ipynb
 |-- final_data_sparkify.csv.zip
 |-- medium_sparkify_event_data.zip
 |-- mini_sparkify_event_data.zip
 |-- Sparkify(IBM).html

* Sparkify(IBM).ipynb: Notebook with all the scripts used to analyse data and to address the churn prediction problem
* data_final_spark.csv.zip: final data set after feature engineering (in spark format) - must be unzipped!
* medium_sparkify_event_data.zip: meidum subset (4Gb) of the full dataset available (12GB) - must be unzipped!
* mini_sparkify_event_data.zip: small subset (128MB) of the full dataset available (12GB) - must be unzipped!
* Sparkify(IBM).html: .html version of the jupyter notebook

## Required packages <a name="Requiredpackages"></a>

The project was developed and tested on IBM Watson Studio Lite account (free). It allows to use a Jupyter notebook with Python 3.6 with Spark, which uses one driver with 1 vCPU and 4GB RAM, and 2 executors each with 1 vCPU and 4 GB RAM.

The following packages must be installed:
* Pyspark
* Pandas
* Datetime
* Seaborn 0.9+
* Matplotlib

## Results <a name="Results"></a>

## Screeshots <a name="Screenshots"></a>

## Acknowledgements <a name="Licensing"></a>
