# Project 3 - Reddit Posts

## Dillon Koh, DSIF-2 Singapore

## Problem Statement

I am a data scientist in Reddit and recently, the operation team discover that there is data corruption resulting in a loss of data for recent subreddit posts for these 2 particular subreddits - Parenting and Relationship Advice and they happen to be subreddits which have many members and active. The operation team managed to recover the some data which are basically the posts and their descriptions but not the subreddits which they belong to i.e. Parenting or Relationship Advice. Hence, they have engaged the data team, in particular myself to help them classify these posts to the respective subreddits for them to restore the data.

For this problem,, my proposed soution will be two-fold:
1. Using [Pushshift's](https://github.com/pushshift/api) API, I will collect posts from the two subreddits - Parenting and Relationship Advice.
2. I will then use NLP to train a classifier on which subreddit a given post came from. This is a binary classification problem.


## Executive Summary

This project involves the use of Natural Language Processing to train a classifier on which subreddit a given post came from. The reason for this project is explained in the problem statement where there is data corruption resulting in a loss of data for recent subreddit posts for these 2 particular subreddits - Parenting and Relationship Advice and they happen to be subreddits which have many members and are active. The operation team require the data science team to help classify these posts to the respective subreddits.

For the first step, I use the Pushshift's API to import reddit posts from both subreddits and then store them in a DataFrame for further processing in the second notebook to prevent unncessary importing when running the notebook. For the second step, I did some data preparation and processing such as using Regex to remove subreddit terms 'Parenting' and 'Relationship' Advice to eliminate target leakage. After which, I use CountVectorizer and TfidfVectorizer with different models/algorithm as shown below:

- Random Forest Algorithm (RandomForestClassifier)
- Naive Bayes Algorithm (MultinomialNB)

I have modelled the following models before coming to choose the best model which is MultinomialNB apart from the RandomForestClassifer -

- Ensemble of all the different classifiers except RandomForestClassifier (i.e. VotingClassifier)
- ExtraTrees Algorithm (ExtraTreesClassifier),
- Naive Bayes Algorithm (MultinomialNB)
- Logistic Regression with Lasso Regularization (LogisticRegression)
- Decision Tree Algorithm (DecisionTreeClassifier)
- K-Nearest-Neighbor Algorithm (KNeighborsClassifier)

To reduce the amount of time to run the pynb, I will just use MultinomialNB model in this notebook as it has the highest accuracy score from the above models and also relatively good sensitivity and specificity score (generally these scores are better than other models' scores too. I will combine the results from the 2 models - RandomForestClassifier and MultinomialNB moels with both CountVectorizer and TfidfVectorizer and choose my best model.

The final model is selected out of these 2 models considering accuracy score (primary metric), ROC curves, sensitivity and specificity. The final combination model is TfidfVectorizer with MultinomialNB as the final combination model. This will be used to predict the unseen data which the operation team will require to classify.

## Analysis and Conclusion

A wide range of models were evaluated to select the final model to be used for the classification of the unseen posts into the 2 subreddits. The analysis and evaluations will be explained below. 

**Analysis of the RandomForest Model with the two different vectorizers**

Based on the evaluation of the 2 RandomForest combination models, the combination of using TfidfVectorizer with RandomForestClassifier seems to produce better accuracy, specificity and sensitivity scores as compared to the CountVectorizer with RandomClassifier. The accuracy scores of using TfidfVectorizer and CountVectorizer with RandomForestClassifier are 0.928 and 0.919 respectively. In general, the differences in the scores between these two vectorizers are minimal. Hence, I have decided to use TfidfVectorizer with RandomForestClassifier as my best RandomForestClassifer combination model.

**Analysis of other Models/Algorithms excluding RandomForest Model**

For the other algorithmns, I have modelled the following models before deciding to choose MultinomialNB considering the list of models below -

1. Ensemble of all the different classifiers except RandomForestClassifier (i.e. VotingClassifier)
2. ExtraTrees Algorithm (ExtraTreesClassifier),
3. Naive Bayes Algorithm (MultinomialNB)
4. Logistic Regression with Lasso Regularization (LogisticRegression)
5. Decision Tree Algorithm (DecisionTreeClassifier)
6. K-Nearest-Neighbor Algorithm (KNeighborsClassifier)

To reduce the amount of time to run the pynb, I have just use MultinomialNB model as it has the highest accuracy score compared to the other models shown above and also achieve relatively good sensitivity and specificity score. I will combine the results from the 2 models - RandomForestClassifier and MultinomialNB with both CountVectorizer and TfidfVectorizer to select my final model

**Selection of Final Model**

Based on the accuracy scores in the sorted dataframe and ROC curves, the best performing model is MultinomialNB with TfidfVectorizer as it has an accuracy score of 0.954. In general, the model with TfidfVectorizer outperform the model with CountVectorizer considering the same model only. Other performance metrics such as sensitivity and specificity scores for the MultinomialNB model also outperform the other model scores with the only exception of sensitivity score which it lost to MultinomialNB with CountVectorizer marginally. Hence, I will be using TfidfVectorizer with MultinomialNB as the final model to predict the data which require classification.


## Some thoughts

- Overall, my final model perform relatively well mainly because the subreddits are quite different and there are alot of features/words that the models can consider to classify the post into the various subreddits. This is evident as all models seem to have relatively good performance metrics too
- With more time and effort, i will also use lemmatizing and stemming before using CountVectorizer and TfidfVectorizer and any modelling to analyze the impact on the model results.
- Subsequently, I will also look to fine tune the stop words or removing some words which doesnt really make sense such as 'didn', 've' which actually refer to 'didn't' and 'have' respectively. With this, I expect the model to perform better in classifying the posts, descriptions into the 2 subreddits.
- It is also good to consider other evaluations metrics like precision, f1-score and etc.
-  I can improve the regex code to remove words which include the subreddits terms - Parenting, Relationship Advice with the possibility of typo errors. Example, i will remove 'ParentingA@' as a whole term


## Data
I used the Pushshift's API to import reddit posts from both subreddit Parenting and Relationship Advice and then store them in a dataFrame for further processing before modelling. There are a total of 72 data fields extracted from the API such as created_utc (creation time), author_fullname (ID of the author) and etc. However, i am only interested in the following fields for my projects. Hence, i created a dataframe to only collect these 3 fields.

### Data Dictionary


| **Column**  | **Description**  |
| :-|:-|
| subreddit  | subreddit category housing this post  |
| selftext   | Text of the post  |
| title  | post title |

