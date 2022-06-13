# Bike Sharing Assignment
> A bike-sharing system is a service in which bikes are made available for shared use to individuals on a short term basis for a price or free. Many bike share systems allow people to borrow a bike from a "dock" which is usually computer-controlled wherein the user enters the payment information, and the system unlocks it. This bike can then be returned to another dock belonging to the same system.

## Table of Contents
1. [Problem Statement](#section1)<br>    
2. [Data Loading and Description](#section2)<br>
3. [Data cleaning](#section3)<br>
4. [Exploratory Data Analysis](#section4)<br>
5. [Training linear regression model](#section5)<br>
    - 5.1 [Splitting data into trainset and testset](#section501)<br>
    - 5.2 [Rescaling the features](#section502)<br>
    - 5.3 [Splitting into X_train and y_train on training dataset](#section503)<br>
    - 5.4 [Building Linear Model using Statsmodel](#section504)<br>
         - 5.4.1 [Selecting features and model training using RFE](#sectionrfe)<br>
         - 5.4.2 [Stats model 1](#sectionmodel1)<br>
         - 5.4.3 [Stats model 2](#sectionmodel2)<br>
         - 5.4.4 [Stats model 3](#sectionmodel3)<br>
         - 5.4.5 [Stats model 4](#sectionmodel4)<br>
         - 5.4.6 [Stats model 5](#sectionmodel5)<br>
         - 5.4.7 [Stats model 6](#sectionmodel6)<br>
         - 5.4.8 [Stats model 7](#sectionmodel7)<br> 
    - 5.5 [Line Equation of the model](#section505)<br>
    - 5.6 [Validating the model](#section506)<br>
6. [Testing Linear regression model](#section6)<br>
    - 6.1 [Rescaling features on Testdata](#section601)<br>
    - 6.2 [Splitting into X_test and y_test](#section602)<br>
    - 6.3 [Performing predictions on Testset](#section603)<br>
7. [Model evaluation](#section7)<br>
    - 7.1 [Model Evaluation using R-squared value.](#section701)<br>
    - 7.2 [Model Evaluation using Adjusted R-squared value](#section702)<br>
    - 7.3 [Model Evaluation using RMSE](#section703)<br>
8. [Conclusion](#section8)<br>

## General Information
> __Problem Statement:__
> A US bike-sharing provider __BoomBikes__ has recently suffered considerable dips in their revenues due to the ongoing Corona pandemic. The company is finding it very difficult to sustain in the current market scenario. So, it has decided to come up with a mindful business plan to be able to accelerate its revenue as soon as the ongoing lockdown comes to an end, and the economy restores to a healthy state. 

> __Business Goal:__
>You are required to model the demand for shared bikes with the available independent variables. It will be used by the management to understand how exactly the demands vary with different features. They can accordingly manipulate the business strategy to meet the demand levels and meet the customer's expectations. Further, the model will be a good way for management to understand the demand dynamics of a new market.

## Analysis of the problem
  - They want to understand the factors affecting the demand for these shared bikes in the American market
    -  Which variables are significant in predicting the demand for shared bikes.
    -  How well those variables describe the bike demands
  - Approach in finding demand for US BoomBikes   
    - Performed Exploratory Data Analysis on independent variables to understand the patten in our data.
    - Performed Linear Regression model
    - Training our model using RFE
    - Multiple Linear regression using OLS statsmodel
    - Calculated Variance Inflation Factor
   - Validating Assumptions of Linear regression
    - Normality of Error
    - Linear relationship between our independent and dependent variable
    - Checking for Homoscedasticity
    - Absence of Multicollinearity
    - No autocorrelation of errors

## Conclusions
- We have obtained a good model which predicts the most important factors that influence renting a bike from BoomBikes.
- Equation of the model comes out to be
  - __cnt = 0.1910 + 0.2341 `*` Year + 0.0909`*`Month_sep - 0.0551`*`season_spring + 0.0610`*`season_summer + 0.0959`*`season_winter - 0.2860`*`weathersit_Light Snow - 0.0801`*`weathersit_Mist -0.0969`*`holiday + 0.4782`*`temp - 0.1482`*`windspeed__
  
- Evaluating our model with test data gave us good values for 
  - __*R-Squared          : 0.8035441330582012*__
  - __*Adjusted R-squared : 0.7931044493076708*__
  - __*RMSE               : 0.0965962223188116*__
  
- We could find that the count of __bike rentals increases with__  
  - __Temperature(temp)__ plays an __important role__ in renting a bike, its coefficient __0.4782__ is highest compared to other features.
  - __Year__ has a good coefficient of __0.2341__. So, there is high chance that people will prefer renting bike in comming years.

- Some other pattern when __bike rentals are not preferred__
  - During __season_Spring__, its coefficient __-0.0551__ says bike rentals are less.
  - When the weathere is __Light Snow__, bike rentals are highly affected.
  - __windspeed__ also affects the bike rental count.
  
- __BoomBikes__ can consider the following suggestions to increase their revenue
  - During __September__ there are high chances of people renting bike, so we can increase the number of bikes in their dock.
  - During __Fall and Summer__ people prefer to rent bikes than other season. So, we can increase number of dock in places where the distance between our next dock is high.

## Technologies Used
- Coding Language
   - Python 3.0
- libraries and packages used 
   - Numpy
   - Pandas
   - seaborn
   - matplotlib
 - libraries used for model building
   - scikit-learn 

## Acknowledgements
Give credit here.
- This project was inspired by...
- References if any...
- This project was based on [this tutorial](https://www.example.com).
