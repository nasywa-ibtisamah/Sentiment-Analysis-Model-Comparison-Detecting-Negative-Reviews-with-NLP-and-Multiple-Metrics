# Project Description

Hello there :wave:
I hope this project finds you well!

I will train multiple models that can classify both positive and negative reviews and automatically detect negative reviews. Additionally, I will use accuracy score, F1 score, and AUC ROC as evaluation metrics for the models. In the process, I will perform natural language processing using several libraries to compare the evaluation results of the models.


**Objective**

Determine the best model with a minimum F1 score of 0.85.

**Used Model**
1. Dummy Classifier
2. Linear Regression Model using the NLTK library for NLP task and TF-IDF for tokenization [without hyperparameter tuning and with hyperparameter tuning]
3. Linear Regression Model using the spaCy library for NLP task and TF-IDF for tokenization [without hyperparameter tuning and with hyperparameter tuning] - Models 3 and 4
4. LGBMClassifier model using the spaCy library for NLP task and TF-IDF for tokenization - Model 5

# Steps

1. Data Overview
2. Exploratory Data Analysis
3. Data preprocessing
4. Model Training and Evaluation
5. Testing the trained model on a self-created reviews dataset

## 1. Data Overview

**Features:**

- `tconst` - alphanumeric unique identifier of the title
- `title_type` - the type/format of the title (e.g. movie, short, TV series, TV episode, video, etc.)
- `primary_title` - the more popular title / the title used by the filmmakers on promotional materials at the point of release
- `original_title` - original title, in the original language
- `start_year` - represents the release year of a title. In the case of TV Series, it is the series start year
- `end_year` - TV Series end year. ‘\N’ for all other title types
- `runtime_minutes` - primary runtime of the title, in minutes
- `is_adult` - 0: non-adult title; 1: adult title
- `genres` - includes up to three genres associated with the title
- `average_rating` - weighted average of all the individual user ratings
- `votes` - number of votes the title has received
- `review` - review text
- `rating` - rating
- `ds_part` - train/test for part of the dataset (train/test dataset split)

**Target:**
- `pos` - 0 for negative and 1 for positive.

**Conclusion of Data Exploration Stage**

1. There are missing values in the `average_rating` and `votes` columns with a very small percentage (0.42%).
2. There is no duplicated data.
3. Column names are standardized.

## 2. Exploratory Data Analysis

#### 1. Check the number of movies and reviews over the course of several years
**Findings**

1. From the first graph titled 'Number of Movies Over Several Years,' it can be observed that the year 2016 had the highest number of movies, with a value of nearly 400. This is followed by the year 2005 with a value above 350 and 2003 with a value of 300.
2. From the second graph titled 'Number of Reviews Over Several Years,' it can be observed that the year 2016 had the highest number of reviews per movie, with a value of around 3400 reviews. This is followed by the year 2005 with a value around 3050 and 2003 with a value around 2800.

#### 2. Check the distribution of the number of reviews per movie with accurate counting and KDE (Kernel Density Estimation) (to understand the difference from accurate counting)

**Findings for Bar Plot and KDE plot #Reviews per Movie**
1. From the distribution plot of the number of reviews per movie above, it can be observed that the highest number of reviews per movie is the value 1, with a count of around 1300.
2. From the distribution plot of the KDE for the number of reviews per movie, it can be seen that the value 1 has the highest density value, with a density of around 0.12.
3. As additional information, KDE plots are used to visualize the probability distribution of continuous data. KDE is employed to estimate the probability density function of unknown data.

**Findings for Distribution of Ratings of Train Set and Test Set**

1. From the two graphs above, both the Train Set and Test Set have the same distribution of data.
2. The highest rating is 1, with a count of nearly 5000, followed by rating 10 with a count around 4500.
3. The next rankings are 8 and 4.
4. Rankings 3 and 7 have a difference in order between the train set and test set.
5. In the train set, rating 7 is higher than rating 3, but in the test set, rating 3 is higher than rating 7. Following those, we have rating 2 and lastly, rating 9.


#### 3. Distribution of negative and positive reviews over the years for two dataset portions

**Findings**

  

1. From the comparison graphs of the Train Set and Test Set on the distribution of the number of reviews from different polarities per year, it can be observed that both datasets share a common trend, where negative reviews are more prevalent than positive reviews.

2. However, there are similarities and differences in the graphs depicting the number of reviews from different polarities per year. In the first rank, the year 2006 emerges as the year with the highest number of reviews in both datasets, with a count above 1600. However, the difference is apparent in the second rank, where in the Train Set, the second rank is in the year 2005. On the other hand, in the Test Set, the second rank is in the year 2007.

## 3. Data Preprocessing

The following are data preprocessing steps I did in this project:
1. Normalization

## 4. Model Training and Evaluation

Model 4 and Model 2 have higher evaluation scores than Model 5.

## 5. Testing the trained model on a self-created reviews dataset

In general, the results of model 2 are reasonably accurate, although there are some predictions that are not entirely accurate.

# General Conclusion

We have trained the following models:

- Dummy Classifier - Model 0
- Linear Regression Model using the NLTK library for NLP task and TF-IDF for tokenization [without hyperparameter tuning and with hyperparameter tuning] - Models 1 and 2
- Linear Regression Model using the spaCy library for NLP task and TF-IDF for tokenization [without hyperparameter tuning and with hyperparameter tuning] - Models 3 and 4
- LGBMClassifier model using the spaCy library for NLP task and TF-IDF for tokenization - Model 5

 Out of the five trained models, the best model for predicting negative comments is **Model 2: Linear Regression Model using the NLTK library for NLP task and TF-IDF for tokenization with hyperparameter tuning**.

 The processing time of Model 2 is faster compared to Model 4. When applied to the self-created review dataset, the results of model 2 are reasonably accurate, although there are some predictions that are not entirely accurate.
