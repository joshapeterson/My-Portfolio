# My Portfolio

## Table of Contents

- Python Projects
  - [Detecting COVID-19 using Chest X-rays](#detecting-covid-19-using-chest-x-rays)
  - [Detecting COVID-19 Misinformation on Social Media](#detecting-covid-19-misinformation-on-social-media)
  - [Text Analysis and Mining Example](#text-analysis-and-mining-example)
- R Projects
  - [The History of Nobel Prize Winners](#the-history-of-nobel-prize-winners)

---

## [Detecting COVID-19 using Chest X-rays](https://github.com/joshapeterson/My-Portfolio/tree/main/image-classification-project)

### Overview

**Goal of Project**: Develop a deep learning model to accurately detect COVID-19 using chest x-ray images

The purpose of this project was to create a deep learning model that accurately detects COVID-19 and types of pneumonia using chest x-rays. Many of the existing models are trained on entire chest x-ray images and perform only a binary classification to detect COVID-19. In this project, we train a model on masked chest x-ray images to remove unwanted artifacts or areas of the x-ray image and perform multiclass classification to label an image as containing evidence of COVID-19 or types of pneumonia. The final developed deep learning model acheived an accuracy of 85%. Error analysis of the model indicated that most confusion arose due to the model misclassifying bacterial and viral pneumonia x-rays more often than other classes. Therefore, future work would involve improving the performance of this model on these classes. 

***Model Results***

This model acheived an accuracy of 85%. The following is a classification report from the model:

<img src="image-classification-project/images/classification-matrix.png" width="400"/>

*Note: 0 = Bacterial Pneumonia, 1 = Healthy, 2 = Viral Pneumonia, 3 = COVID-19*

***Future Work***

When conducting an error analysis of the developed model, it was seen that the most confusion in the model arose when trying to distinguish between viral pneumonia and bacterial pneumonia. This is represented in the confusion matrix below and the lower F1-score for those classes in the classification report.  

<img src="image-classification-project/images/confusion-matrix.png" width="500"/>

Future work would involve exploring ways to improve the performance of this model on these classes. 

### Data Source

V7 Labs. Available from: https://darwin.v7labs.com/v7-labs/covid-19-chest-x-ray-dataset/overview

### Authors

* Joshua Peterson
* Michael Gray
* Mangala Desai

### List of Primary Dependencies 

numpy, pandas, tenserflow, keras, matplotlib, seaborn and imquality

### 🔗 [Link to Project Code](https://github.com/joshapeterson/My-Portfolio/blob/main/image-classification-project/image_classification_project_code.ipynb)

*[Back to Table of Contents](#table-of-contents)*

---

## [Detecting COVID-19 Misinformation on Social Media](https://github.com/joshapeterson/My-Portfolio/tree/main/misinformation-detection-project)

### Overview

**Goal of Project**: Develop a machine learning model to accurately detect COVID-19 misinformation on X (formerly Twitter). 

The purpose of this project was to create a machine learning model that accurately detects COVID-19 misinformation on social media. The final developed deep learning model acheived an accuracy of 95%. This model could be deployed on a platform such as Twitter to detect COVID-19 related misinformation posted on the platform. 

***Model Results***

This model acheived an accuracy of 95%. The following is a classification report from the model:

<img src="misinformation-detection-project/images/results.png" width="400"/>

A confusion matrix shows that the developed model is able to quite accurately detect if the content of a tweet contains misinformation or accurate information. 

<img src="misinformation-detection-project/images/confusion_matrix.png" width="500"/>

***Future Work***

The developed model was saved with the goal of deploying the model in the future. 

### Data Sources

Cui, L., & Lee, D. (2020). CoAID: COVID-19 Healthcare Misinformation Dataset. Retrieved from http://arxiv.org/abs/2006.00885 

Memon, S. A., & Carley, K. M. (2020). Characterizing COVID-19 misinformation communities using a novel Twitter dataset. Retrieved from http://arxiv.org/abs/2008.00791  

Shahi, G. K., Dirkson, A., & Majchrzak, T. A. (2021). An exploratory study of COVID-19 misinformation on Twitter. Online Social Networks and Media, 22(100104), 100104. doi:10.1016/j.osnem.2020.100104 

*Note: These are all datasets containing labeled tweets that I hydrated using the tweet IDs* 

### Author

Joshua Peterson

### List of Primary Dependencies

numpy, pandas, seaborn, matplotlib, nltk, sklearn, xgboost, os, pickle, collections

### 🔗 [Link to Project Code](https://github.com/joshapeterson/My-Portfolio/blob/main/misinformation-detection-project/misinformation_detection_project_code.ipynb)

*[Back to Table of Contents](#table-of-contents)*

---

## [Text Analysis and Mining Example](https://github.com/joshapeterson/My-Portfolio/tree/main/text-mining-and-analysis-example)

### Overview

I was invited to give a talk to the M.S. in Data Science and Business Analytics program's Advanced Business Analytics class to discuss text mining and analysis methods. During the talk, an example of how to apply various text mining and analysis methods to Twitter data was provided. The code from this talk can be found [here](https://github.com/joshapeterson/My-Portfolio/blob/main/text-mining-and-analysis-example/text-analysis-and-mining-example_code.ipynb).

**Topics Covered**

- Text Preprocessing
- Text Cleaning
- Term Frequencies
- Word Clouds
- Sentiment Analysis
- Part-of-Speech Tagging
- Topic Modeling

### Author

Joshua Peterson

### List of Primary Dependencies

pandas, numpy, re, nltk, collections, itertools, sklearn, matplotlib, seaborn, wordcloud and textblob

### 🔗 [Link to Example Code](https://github.com/joshapeterson/My-Portfolio/blob/main/text-mining-and-analysis-example/text-analysis-and-mining-example_code.ipynb)

*[Back to Table of Contents](#table-of-contents)*

---

## [The History of Nobel Prize Winners](https://github.com/joshapeterson/My-Portfolio/tree/main/shiny-application-project)

### Overview

The goal of this project was to build a shiny application that could provide a general overview of previous Nobel Prize winners. Creating a tool that could be used to assist institutions with future decisions regarding who to award the Nobel Prize.

First, a general overview of Nobel Prize winners as well as the journals and organizations associated with those winners was provided. 

![](shiny-application-project/images/shiny-app_overview.png)

Next, an analysis of previous award motivations and titles of winning papers was provided to understand the drivers of previous Nobel Prize awards. 

![](shiny-application-project/images/shiny-app_motivation-and-paper-title.png)

Finally, additional information about Nobel Prize winners was analyized such the number of publications they had, average years of academic experience, and age. 

![](shiny-application-project/images/shiny-app-publication.png)

All of this information can help us better understand previous Nobel Prize award winners.

### 🔗 [Link to Shiny App](https://japeterson.shinyapps.io/updated-app/)

### Authors

* Joshua Peterson
* Dipin Kasana
* Kelly O'Shields

### Data Source

Kaggle. Available from: https://www.kaggle.com/datasets/nobelfoundation/nobel-laureates

### List of Primary Dependencies

shiny, shinydashboard, tidytext, wordcloud, ggplot2 (Developer Version), RColorBrewer, tidyverse, validate, hrbrthemes, waiter and DT

### 🔗 [Link to Project Code](https://github.com/joshapeterson/My-Portfolio/blob/main/shiny-application-project/app.R)

*[Back to Table of Contents](#table-of-contents)*

