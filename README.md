# GA DSIF Projects
This folder includes the first 3 projects which I have done in GA Data Science Immersive Project as shown below

## Project 1 - Standardized Test Analysis

For the course of this project, DSIF2-Group1 has decided to support the College Board with an analytical consulting project tackling three major concerns:

(1) How can SAT acceptance be strengthened?
(2) How can the College Board tap into auxiliary revenue streams to support proactive tackling of big challenges
(3) Which measures can be taken to support its long-term license to operate?

DSIF2-Group1 understands that the College Board is a mission-driven not-for-profit organization that connects students to college success and opportunity. Therefore, the College Board does not have much budget for this project.

This subset of the overarching project focuses on (1) and (2), investigating ways to grow SAT participation rate in states with maximized return on investment (ROI). To ensure maximized ROI, the research objective of this notebook is to investigate the latest trend and development of SAT participation in the various states and look to grow SAT participation in the selected states.

The proposal will include the selected states of interest, justification for our selections and recommendations for the following:

Primary focus of growing SAT participation
Other aspects such as improvement of SAT scores (consider the 2 different sections of SAT), supporting the household and students in terms of subsidized cost where possible

## Project 2 - Ames Housing Data and Kaggle 

This project involves the creation and evaluation of models, selection of the best model to predict housing prices in Ames, IA and identify the key features which will greatly impact housing prices. The task is addressed by examining about 80 housing-related variables, sale prices of the houses between 2006 and 2010.

For modeling and performance measurement, the data are separated into a training and a test set. Modelings are built on the training subset of the training data, cross validated with the test subset of the training data before the best model is then fitted on the entire training data set. The selection of the best model is conducted using $R^2$ and MSE scores.

The approach to tackle this project is separated into 2 major parts -

- Exploratory Data Analysis (EDA) and Data Cleaning
- Feature Elimination and Modelling

## Project 3 - Reddit Posts

I am a data scientist in Reddit and recently, the operation team discover that there is data corruption resulting in a loss of data for recent subreddit posts for these 2 particular subreddits - Parenting and Relationship Advice and they happen to be subreddits which have many members and active. The operation team managed to recover the some data which are basically the posts and their descriptions but not the subreddits which they belong to i.e. Parenting or Relationship Advice. Hence, they have engaged the data team, in particular myself to help them classify these posts to the respective subreddits for them to restore the data.

For this problem,, my proposed soution will be two-fold:

Using Pushshift's API, I will collect posts from the two subreddits - Parenting and Relationship Advice.
I will then use NLP to train a classifier on which subreddit a given post came from. This is a binary classification problem.

### For the individual project README files, you can view them in the respective project folder
