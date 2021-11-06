# Project 2 - Ames Housing Data and Kaggle Challenge

## Dillon Koh, DSIF-2 Singapore

## Problem Statement

The problem statement of this project is to find a model to predict housing prices in Ames, IA and to identify key features to help house owners and buyers in their decision to purchase or sell their houses.


## Executive Summary

This project involves the creation and evaluation of models, selection of the best model to predict housing prices in Ames, IA and identify the key features which will greatly impact housing prices. The task is addressed by examining about 80 housing-related variables, sale prices of the houses between 2006 and 2010.

For modeling and performance measurement, the data are separated into a training and a test set. Modelings are built on the training subset of the training data, cross validated with the test subset of the training data before the best model is then fitted on the entire training data set. The selection of the best model is conducted using $R^2$ and MSE scores.

The approach to tackle this project is separated into 2 major parts -

    - Exploratory Data Analysis (EDA) and Data Cleaning
    - Feature Elimination and Modelling

The provided data is explored and cleaned in the following steps -

    - Dropping the variables 'Alley', 'Pool QC', 'Fence' and Misc Feature' because of too many missing values
    - For the below variables, the following approach was employed to fill the missing values instead of dropping the variables
    - Lot Frontage : Missing values most likely means no lot frontage so fill missing values as 0
    - Mas Vnr Type and Area : Missing values most likely means no Masonry Veneer so fill type as 'No' and area as 0
    - Bsmt related field: Missing values means "no basement" so fill numerical field as 0 object type as 'No'
    - Fireplace Qu: Missing values means "no fire place" so fill missing values as 'No'
    - Garage related fields: Missing values means garage feature is "no garage" so fill numerical field as 0 object type as 'No'
    - Cleaning of outliers
    - Creating new variables/features such as age of the home at sale and age of the remodelled house (if applicable) using the yr_built and yr_remodel features

Subsequently, I use sklearn.preprocessing package, PolynomialFeatures to create more features with higher order terms. In this case, I use a degree of 2. This resulted in having a dataset with a total of 1592 columns/features to explore. Before doing any modelling, I will fit and transform the training subset and transform the test subset. Then, I created a Linear Regression model with all 1592 features as a baseline to have a sensing of how the model perform. 

After which, I use 2 different techniques - SelectKBest and recursive feature elimination (RFE) to select the best 20 features from each technique, consolidate the 20 best features from each technique into a list and removing duplicated feature. Finally, I use correlation with the Sale Price (Y-variable) to futher select 10 best features for further modelling.

Subsquently, I created 4 more models - 1 Linear Regression model with the 10 best features, Lasso and Regularization models on this Linear Regression model. Lastly, I created 1 more Linear Regressions with 10 distinct features (which does not have duplicated features as a component of degree 2 features or even as standalone feature) in the hope of removing multicollinearity issue which I observed during evaluation of my model. Then, I evaluated the model and choose the best model with explanation to predict the sale prices of the test dataset.

## Analysis and Conclusions.

A wide range of models were evaluated and in doing so a trade off between explainability and predictability was observed. With about an initial of 80 variables from the provided datasets, many of which are categorical, there is the possibility to build models that depend on a large number of variables. To improve this situation, I have encoded some features as ordered numbers where possible based on the data dictionary which indicate ordinal. Otherwise, combine the training and test data sets into a single data frame and create dummy variables for each categorical variable (to ensure consistency). Before doing any modelling, I will scaled the data to ensure that the scale of the data is consistent.

Introducing more features/variables can improve explanatory power especially with the training data, but it does present the risk of overfitting resulting in prediction weakness in data not seen by the model as shown in my initial Linear Regression model of 1592 features. Building large variable set models also presents other challenges. Such models are likely to suffer from problems of multicollinearity since it is likely that many of the independent variables are correlated. This turned out to be a particular problem with these data since many housing characteristics are related. For example, a larger house is likely to have more bedrooms than a smaller one. Even after reducing the number of features to 10 and selecting 10 distinct features, the multicollinearity issue remains. 

**Analysis of the first Linear Regression Model with all 1592 features**

Based on the MSE and $R^2$ score, my model is performing far worse on the test subset than on the training set and it is very clear that the model is overfit to the data.

This is expected as there are many features used (about 1500 features) and from these features, it was explored during data cleaning and EDA for just 70 features, there is multicollinearity issue. Furthermore, quite a number of features do not have a linear relationship with the sale prices.

**Analysis of the Linear Regression Model with 10 best features**

Based on the evaluation charts and OLS summary, the evaluation of the model is as follows -

The MSE and $R^2$ score for Linear Regression (10 selected features) is the best as compared to lasso and ridge regulatization. This is likely because of the feature elimination techniques I have used to further select the recommended features. The 10 selected features have a linear relationship with the target variable - Sale Price. There seems to be a strong multicollinearity between the features - My analysis is that there are 2 prominent features which have strong correlation with sale price - over_qual and gr_liv_area based on these 2 appearing in the polynomial features. Hence, these features have the effect from gr_liv_area and over_qual which could have led to strong multicollinearity Normality of the residuals (errors) - Histogram seems to show that it is normally distributed Variance of the residuals (errors) seem to show that it is equal. Though, there seem to be some anomalies for test subset model - which probably require further work to fine tune and improve the model.

As mentioned above, the model seems to have strong multicollinearity issue and despite creating another model with 10 distinct features, I cant seem to eliminate the multicollinearity issue and i believe that it is because many housing characteristics are related in one way. For example, a larger house is likely to have more bedrooms than a smaller one.

**Key Features from the Model which will affect Housing Prices**
The recommended model incorporated the following key features which affect the housing price and hence shall be used to predict housing prices in Ames, IA:

    - Overall Quality of the house (Strong Feature)
    - Gr Living Area (Strong Feature) - Above grade (ground) living area square feet
    - Kitchen Quality
    - Garage Cars - Size of garage in car capacity
    - Garage Area - Size of garage in square feet
    - Bstm Qual - Refers to the height of the basement
    - 1st Flr SF - First Floor Square Feet

## Some Thoughts

    - More time and effort can be spend to select good features and also investigate if multicollinearity issue can really be resolved. Otherwise, using other algorithms may be more appropriate 
    - It might be a better idea of not separating the sale price from the dataframe as it creates some inconveniences in further cleaning the data of evaluation of models and features
    - Can look into removing more outliers or create different models for the outliers to better improve the performance of the model
    - To look deeper to understand how the coefficient of the features for unscaled and scaled data differ and also some parameters such as p-value are the same.

## Data

Data sources: http://jse.amstat.org/v19n3/decock/DataDocumentation.txt

Training and test datasets were provided as a part of project materials. The variable listing can be found in the dictionary below. Details and descriptions of the data/features can be obtained from the above link.

### Data Dictionary

| **Feature**  | **Description**  |
| :-|:-|
| MS SubClass  | The type of dwelling involved in the sale  |
| MS Zoning   | Identifies the general zoning classification of the sale  |
| Lot Frontage  | Linear feet of street connected to property  |
| Lot Area   | Lot size in square feet  |
| Street  | Type of road access to property  |
| Alley   | Type of alley access to property  |
| Lot Shape  | General shape of property  |
| Land Contour | Flatness of the property  |
| Utilities  | Type of utilities available  |
| Lot Config  | Lot configuration  |
| Land Slope  | Slope of property  |
| Neighborhood  | Physical locations within Ames city limits  |
| Condition 1  | Proximity to various conditions such as arterial street, feeder street, railroad  |
| Condition 2  | Proximity to various conditions such as arterial street, feeder street, railroad (if more than one is present)  |
| Bldg Type   | Type of dwelling  |
| House Style |  Style of dwelling |
| Overall Qual  |  Rates the overall material and finish of the house |
| Overall Cond  | Rates the overall condition of the house |
| Year Built  | Original construction date  |
| Year Remod/Add  | Remodel date (same as construction date if no remodeling or additions) |
| Roof Style  | Type of roof |
| Roof Matl  | Roof material  |
| Exterior 1st  |  Exterior covering on house |
| Exterior 2nd  | Exterior covering on house (if more than one material)  |
| Mas Vnr Type  | Masonry veneer type |
| Mas Vnr Area  | Masonry veneer area in square feet  |
| Exter Qual  | Evaluates the quality of the material on the exterior   |
| Exter Cond  | Evaluates the present condition of the material on the exterior  |
| Foundation  | Type of foundation  |
| Bsmt Qual  | Evaluates the height of the basement  |
| Bsmt Cond   | Evaluates the general condition of the basement  |
| Bsmt Exposure  | Refers to walkout or garden level walls  |
| BsmtFin Type 1  | Rating of basement finished area  |
| BsmtFin SF 1  | Type 1 finished square feet  |
| BsmtFin Type 2  | Rating of basement finished area (if multiple types)  |
| BsmtFin SF 2   | Type 2 finished square feet  |
| Bsmt Unf SF  | Unfinished square feet of basement area  |
| Total Bsmt SF | Total square feet of basement area  |
| Heating  | Type of heating  |
| Heating QC  | Heating quality and condition  |
| Central Air  | Central air conditioning  |
| Electrical | Electrical system |
| 1st Flr SF  | First Floor square feet  |
| 2nd Flr SF  | Second floor square feet  |
| Low Qual Fin SF  | Low quality finished square feet (all floors)  |
| Gr Liv Area   | Above grade (ground) living area square feet  |
| Bsmt Full Bath  | Basement full bathrooms  |
| Bsmt Half Bath  | Basement half bathrooms  |
| Full Bath  | Full bathrooms above grade  |
| Half Bath   | Half baths above grade  |
| Bedroom AbvGr  | Bedrooms above grade (does NOT include basement bedrooms)  |
| Kitchen AbvGr  | Kitchens above grade  |
| Kitchen Qual  | Kitchen quality  |
| TotRms AbvGrd  | Total rooms above grade (does not include bathrooms)  |
| Functional  | Home functionality (Assume typical unless deductions are warranted)  |
| Fireplaces  | Number of fireplaces  |
| Fireplace Qu  | Fireplace quality  |
| Garage Type  | Garage location  |
| Garage Yr Blt  | Year garage was built  |
| Garage Finish  | Interior finish of the garage  |
| Garage Cars  | Size of garage in car capacity  |
| Garage Area  | Size of garage in square feet  |
| Garage Qual  | Garage quality  |
| Garage Cond   | Garage condition  |
| Paved Drive  | Paved driveway  |
| Wood Deck SF  | Wood deck area in square feet  |
| Open Porch SF  | Open porch area in square feet  |
| Enclosed Porch  | Enclosed porch area in square feet  |
| 3-Ssn Porch   | Three season porch area in square feet  |
| Screen Porch  | Screen porch area in square feet  |
| Pool Area   | Pool area in square feet  |
| Pool QC  | Pool quality  |
| Fence  | Fence quality  |
| Misc Feature  | Miscellaneous feature not covered in other categories  |
| Misc Val  | $Value of miscellaneous feature  |
| Mo Sold   | Month Sold  |
| Yr Sold  | Year Sold   |
| Sale Type  | Type of sale  |
| SalePrice  | The property's sale price in dollars |
