# Sentiment Analysis of Amazon Alexa Reviews

## Introduction

This project uses Python and Spark to predict the sentiment of Amazon Alexa reviews.

## File Descriptions

***amazon_alexa.tsv***: Data file for the project.

***DataPreprocessing.ipynb***: Clean the data and transforming it for further analysis.

***DataExploration.ipynb***: Explore the dataset with summary statistics, visualizations, and hypothesis tests.

***LDAClustering.ipynb***: Cluster the corpus of words with Latent Dirchlet Allocation. 

***MachineLearning.ipynb***: Build machine learning models that classify reviews into positive or negative.

***AnalyzeResults.ipynb***: Analyze results of the ridge regression model.

## Limitations

The data exploration shows that this dataset is not likely to be a simple random sample of Amazon Alexa reviews. Most reviews were posted on 8/30/2018. Also, there is an uneven spread of observations across variations, although this is unlikely to have a significant effect since the proportion of positive and negative reviews are roughly the same for each group.

## Findings

Exploratory data analysis showed that this is an imbalanced dataset with 1623 positive reviews and 148 negative reviews. Common terms across all reviews included key words related to Amazon Alexas and positive phrases. Positive reviews were typically shorter than negative reviews. 

Latent Dirchlet Allocation did not separate the data into clear topics. However, Mann-Whitney U tests showed statistically significant evidence that the distribution of positive and negative reviews differed in each of these topics.

Since the classes of the dataset are imbalanced, I used statified cross validation with the f1 score metric to select hyperparameters for each machine learning model. The best model was ridge regression, with an f1 score of 0.55 and an accuracy of 0.91 on the test data. 

Correctly classified observations were predicted with greater confidence than misclassified observations. Terms that were common in positive reviews that were correctly classified included generic terms with favorable connotations. Correctly classified negative reviews had a myriad of terms that described specific instances where the Amazon Alexa was unsatisfactory. The unique descriptions in negative reviews may have made it more challenging for the model to correctly classify these observerations.
