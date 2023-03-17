---
title: "Exploring Data Wrangling, EDA, and Feature Engineering Techniques for Better Predictions: A Titanic Dataset Study"
excerpt: "Learn how to improve predictions by performing exploratory data analysis, implementing data wrangling techniques, applying feature engineering, and performing hyperparameter tuning, with the help of titanic dataset."
header:
  teaser: "/assets/images/posts/RMS_Titanic_3.jpg"
date: March 17, 2023
toc: true
subscribe: true
tags:
  - Data Science
  - Feature Engineering
  - EDA
---

## Introduction

Harnessing the power of data wrangling, exploratory data analysis, and feature engineering is critical to building accurate predictive models. In this comprehensive guide, we'll explore how to approach these essential techniques while making predictions on a dataset. Using the Titanic dataset as an example, I'll walk you through the critical thinking required behind ML modeling, providing a clear roadmap for achieving higher accuracy in your predictions. Use my approach as a starting point to develop your own models and achieve high accuracy in your predictions on the Titanic dataset. Make sure to follow along with my [RMS Titanic Competition Notebook](https://github.com/vxsharma-14/my-ds-notebooks/blob/main/kaggle-titanic-prediction.ipynb) for complementary code and explanatory texts.

The code for analysis and predictions was written in Python language in Jupyter Notebook environment.
{: .notice--success}

The data science libraries used in the analysis are pandas, matplotlib, numpy, seaborn, and scikit-learn.
{: .notice--success}

## What is Data Wrangling?

Data wrangling, also known as data cleaning or data pre-processing, is a critical step in the data analysis and machine learning modeling process. This process involves transforming and mapping raw data into a usable format that is suitable for analysis. Data wrangling includes various steps such as cleaning and filtering data, merging multiple data sources, transforming data into a usable format, and handling missing or inconsistent data.

In the context of the Titanic dataset, data wrangling is essential to ensure that the data is accurate and complete, and can be used for effective analysis and modeling. The dataset downloaded from [Kaggle (dataset link)](https://www.kaggle.com/competitions/titanic/data) consists of two separate datasets: a training set and a test set. Here are the steps required for wrangling the data:

**1. Gather dataset information:** Before carrying out data wrangling, it is important to gather initial insights from raw dataset. This step includes getting the count of rows and columns in the dataset, viewing columns and their datatypes, statistical summaries of the columns, identifying missing value counts in columns, and changing the index column, among other things. I have used `pandas` package throughout this analysis.

**2. Addressing of missing values:** Addressing missing values is a critical step in data wrangling. As shown in my notebook, you will see that the count of missing values in `Age`, `Cabin`, and `Embarked` columns is 177, 682, and 2, respectively. I have implemented a comprehensive correlation approach to address these missing values in my analysis. A Kaggler developed a following correlation to identify missing ages of passengers [(read Discussion)](https://www.kaggle.com/competitions/titanic/discussion/384013):

>  "Generally I was looking if passenger has spouse or children - then I could predict that he is an adult and I can approximate his age based on median of other adults. Same goes with children and lastly for remaining passengers with no family relationships."

**3. Transforming string types columns to numeric type:** The `Sex` column contains categorical values 'male' and 'female' and `Embarked` column contains 'C', 'Q', 'S' values. However, the ML models cannot relate to string values in the data during training or testing. Hence, I used `pandas.get_dummies()` or `sklearn.preprocessing.LabelEncoder()` functions to convert the categorical variable into indicator variables.

By following these steps, you can transform the raw data into a usable format that is suitable for analysis and modeling.

## Exploratory Data Analysis

Exploratory data analysis (EDA) is a critical step in understanding the dataset and identifying the features that significantly impacts the prediction. Using `pandas` and visualization packages such as `matplotlib` and `seaborn`, I conducted both univariate and multivariate analyses on the data. In the univariate analysis, I examined the survivor and death counts, correlation between gender and survivor count, socio-economic status and survivor count, age and survivor count, SibSp and survivor count, and Parch and survivor count using bar plots and histograms. For the multivariate analysis, I studied the combined effects of sex and socio-economic status on survival, sex and age on survival, and sex, age, and SibSp on survival using plots. This analysis provides insight into the features that contribute most to survival and is crucial for making informed decisions about feature engineering and model selection.

## Feature Engineering

Feature engineering is a crucial step in preparing data for accurate predictive modeling. I have discussed creation of new features from existing ones, and the interactions of different columns, such as, `SibSp`, `Parch`, `Age`, and `Fare`. The following features are created for the Titanic dataset:

1. `FamilySize` and `IsAlone`: Created from `SibSp` and `Parch` columns.
2. `AgeBin` and `FareBin`: Created from `Age` and `Fare` columns, respectively.
3. `FamilySizeGroup`: Created from the `FamilySize` column.
4. `Title`: Extracted from `Name` column to create a new column.

To convert categorical values into numerical values, **one-hot encoding** method using `pandas.get_dummies()` was applied to the existing and newly created features. This method creates new columns in the dataset with binary values 1 and 0.

By implementing feature engineering techniques, we can enhance the predictive power of our models by generating meaningful predictors from raw data.

## Model Selection & Training

The process of selecting the best algorithm to solve a problem is called model selection. In this section, I compared different models like Logistic Regression, K-Nearest Neighbors, Support Vector Machine, Decision Tree Classifier, Random Forest Classifier, Naive-Bayes, and Gradient Boosting to determine the best model for this problem. I normalized the data and trained it on training dataset using Python's Scikit-learn library. I performed hyperparamter tuning for each model to fine-tune the model for better performance and subsequently, evaluated the accuracy of each model from the best parameters. 

Hyperparameter tuning is performed to find the optimal values for model parameters. This involved selecting the best combination of hyperparameters that maximized the performance of the model. I used a grid search approach to search through different combinations of hyperparameters and selected the best one based on the evaluation metrics.

Based on my evaluation, I selected Random Forest classifier as the best model for this problem.

## Prediction on Test data

In this section, I used the trained model to predict the survival of passengers in the test set. I applied the same preprocessing steps and feature engineering techniques used in the training set to ensure consistency. I then used the predict() method of the trained model to make predictions on the test set.

After obtaining the predictions, the prediction file was submitted on the Kaggle competition that calculated the prediction accuracy.

## Conclusion

Predicting survival on the Titanic is a challenging task that requires a combination of data exploration, feature engineering, and model selection. By following the steps outlined in this blog post, we can improve the accuracy of our survival predictions from an initial baseline model to a more sophisticated and accurate model. The techniques and tools used in this post can be applied to other predictive modeling tasks to help improve the accuracy of predictions.

In summary, I performed exploratory data analysis to gain insights into the data, performed feature engineering to create new features and transform existing ones, selected the best model using various performance metrics, trained the model using cross-validation and hyperparameter tuning, made predictions on the test set, and evaluated the performance of the model. The selected model achieved high accuracy score on both the training and test sets, demonstrating the effectiveness of our approach.