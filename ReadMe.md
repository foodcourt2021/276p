# Hybrid Recommendation System

## Introduction
This system is used to support Enrole app which is a mobile application for matching job seeker and recruiter in the technical field.
It is very basic version which neglect the accuracy and speed. The main purpose of this project is to present a completed and deployed hybrid recommendation system with preprocessed input data set in one-hot matrix, which can be improved and upgraded in the future.
Our work includes creating an input data frame, preprocessed the raw data, building the content-based filtering model, customizing the collaborative filtering model, deploying the system on the Amazon Segamaker, and build a webpage to visualize it.

## Highlights:

> - Use user profiles and job profiles as content based filtering
> - Use user-job similarity score as collaborative filtering to capture latent features and preferences of users
> - The recommendation system is deployed using Amazon Segamaker and visualization by a temporary webpage.


## Data
User data set are from stack overflow 2018 develop survey on Kaggle.*https://www.kaggle.com/stackoverflow/stack-overflow-2018-developer-survey.*
We choose features such as location, education level, employment, experience,
and skills in several technical fields to mimic the real user profile on a job applying platform.

Job data set are from US technology jobs on Dice.com on Kaggle.*https://www.kaggle.com/PromptCloudHQ/us-technology-jobs-on-dicecom/code.*
We choose extract features from job description to match the features in user data set.



## System Structure
![Hybrid Recommendation System](/assets/images/HybridRecommendationSystem.png)

The hybrid Recommendation system is combined with content-based filtering model and collaborative filtering model.
The data set for training and test is combined with job seekers' profile (user data) and job posting (job data).
Recommendations are generated by both models separately, which means the final recommendations are combined with results from both models.
The content-based filtering model is based on the cosine-similarity model with whole one-hot matrix input files.
The collaborative filtering model is based on the matrix factorization and using the code on *https://albertauyeung.github.io/2017/04/23/python-matrix-factorization.html/*
Because lacking of the user action data or user rating scores, we use the profile similarity score between candidates and jobs as the input.

## How to run the system on Jupyter Notebook
![Hybrid Recommendation System](/assets/images/HybridRecommendationSystem(1).png)

> - The new user profile is in the user_data_0.csv.
> - The existing user profiles are in the user_data_2.csv and user_data_3.csv.
> - The job profiles are in the job_data_2.csv and job_data_3.csv.
> - Run all cells in the HybridRecommendationSystem.ipynb