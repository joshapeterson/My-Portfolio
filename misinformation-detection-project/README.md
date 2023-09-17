# Detecting COVID-19 Misinformation on Social Media

## Overview

**Goal of Project**: Develop a machine learning model to accurately detect COVID-19 misinformation on X (formerly Twitter). 

The purpose of this project was to create a machine learning model that accurately detects COVID-19 misinformation on social media. The final developed deep learning model acheived an accuracy of 95%. This model could be deployed on a platform such as Twitter to detect COVID-19 related misinformation posted on the platform. 

***Model Results***

This model acheived an accuracy of 95%. The following is a classification report from the model:

<img src="images/results.png" width="400"/>

A confusion matrix shows that the developed model is able to quite accurately detect if the content of a tweet contains misinformation or accurate information. 

<img src="images/confusion_matrix.png" width="500"/>

***Future Work***

The developed model was saved with the goal of deploying the model in the future. 

## Data Sources

Cui, L., & Lee, D. (2020). CoAID: COVID-19 Healthcare Misinformation Dataset. Retrieved from http://arxiv.org/abs/2006.00885 

Memon, S. A., & Carley, K. M. (2020). Characterizing COVID-19 misinformation communities using a novel Twitter dataset. Retrieved from http://arxiv.org/abs/2008.00791  

Shahi, G. K., Dirkson, A., & Majchrzak, T. A. (2021). An exploratory study of COVID-19 misinformation on Twitter. Online Social Networks and Media, 22(100104), 100104. doi:10.1016/j.osnem.2020.100104 

*Note: These are all datasets containing labeled tweets that I hydrated using the tweet IDs* 

## Author

Joshua Peterson

## List of Primary Packages Used

numpy, pandas, seaborn, matplotlib, nltk, sklearn, xgboost, os, pickle, collections

## 🔗 [Link to Project Code](https://github.com/joshapeterson/My-Portfolio/blob/main/misinformation-detection-project/misinformation_detection_project_code.ipynb)

*[Back to Portfolio](https://github.com/joshapeterson/My-Portfolio)*
