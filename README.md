# My Portfolio

## Table of Contents

- Python Projects
  - [Detecting COVID-19 using Chest X-rays](#detecting-covid-19-using-chest-x-rays)
  - [Text Mining and Analysis Example](#text-mining-and-analysis-example)
- R Projects
  - [The History of Nobel Prize Winners](#the-history-of-nobel-prize-winners)
- Research Papers 
  - [Detecting and Determining the Intentionality of COVID-19 Misinformation on Social Media](#detecting-and-determining-the-intentionality-of-covid-19-misinformation-on-social-media)

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

When conducting an error analysis of the developed model, the most confusion in the model arose when trying to distinguish between viral pneumonia and bacterial pneumonia. This is represented in the confusion matrix below and the lower F1-score for those classes in the classification report.  

<img src="image-classification-project/images/confusion-matrix.png" width="500"/>

Future work would involve exploring ways to improve the performance of this model on the viral and bacterial pneumonia classes. 

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

## [Text Mining and Analysis Example](https://github.com/joshapeterson/My-Portfolio/tree/main/text-mining-and-analysis-example)

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

The goal of this project was to build a shiny application that could provide a general overview of previous Nobel Prize winners.

First, a general overview of Nobel Prize winners as well as the journals and organizations associated with those winners was provided. 

![](shiny-application-project/images/shiny-app_overview.png)

Next, an analysis of previous motivations for awards and titles of winning papers was provided to understand the drivers of prior Nobel Prize awards. 

![](shiny-application-project/images/shiny-app_motivation-and-paper-title.png)

Finally, additional information about Nobel Prize winners was analyized such as the number of publications they had, average years of academic experience, and age. 

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

---

## Detecting and Determining the Intentionality of COVID-19 Misinformation on Social Media

### Abstract

Throughout the COVID-19 pandemic, social media platforms were and continue to be a prevalent method for spreading misinformation related to the pandemic. The need for misinformation detection models and methods was and is necessary to combat this misinformation spread. The purpose of this research is to develop models that are able to detect misinformation on social media platforms. In addition to detecting misinformation, methods for determining the intent of that misinformation are explored so the maliciousness and severity of the detected misinformation can be better understood. This natural language processing task will employ both machine learning and deep learning based models and methods as well as exploring the use of zero-shot classification methods to determine intentionality. Through his research, high performing models for detecting COVID-19 misinformation were identified to be a random forest model and a transformer based neural network model. The random forest model obtained a test accuracy of 94.9% and the transformer based neural network obtained a test accuracy of 95%. A recommended method for determining the intent of misinformation is to utilize a zero-shot classification method to assign predefined intent labels to social media posts. 

### 🔗 [Link to Research Paper](https://github.com/joshapeterson/My-Portfolio/blob/main/Joshua-Peterson_Research-Paper.pdf)

*[Back to Table of Contents](#table-of-contents)*
