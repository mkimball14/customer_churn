# Telecom Customer Churn Analysis: Project Overview 
* Created a tool that estimates data science salaries (MAE ~ $ 11K) to help data scientists negotiate their income when they get a job.
* Scraped over 1000 job descriptions from glassdoor using python and selenium
* Engineered features from the text of each job description to quantify the value companies put on python, excel, aws, and spark. 
* Optimized Linear, Lasso, and Random Forest Regressors using GridsearchCV to reach the best model. 
* Built a client facing API using flask 

## Code and Resources Used 
**Python Version:** 3.7  
**Packages:** pandas, numpy, sklearn, matplotlib


## Data Cleaning
After scraping the data, I needed to clean it up so that it was usable for our model. I made the following changes and created the following variables:

*	Parsed numeric data out of salary 
*	Made columns for employer provided salary and hourly wages 
*	Removed rows without salary 
*	Parsed rating out of company text 
*	Made a new column for company state 
*	Added a column for if the job was at the company’s headquarters 
*	Transformed founded date into age of company 
*	Made columns for if different skills were listed in the job description:
    * Python  
    * R  
    * Excel  
    * AWS  
    * Spark 
*	Column for simplified job title and Seniority 
*	Column for description length 

## EDA
I looked at the distributions of the data and the value counts for the various categorical variables. Below are a few highlights from the pivot tables. 

## Model Building 

First, I transformed the categorical variables into dummy variables. I also split the data into train and tests sets with a test size of 20%.   

I tried two different models and evaluated them using Mean Absolute Error. I chose MAE because it is relatively easy to interpret and outliers aren’t particularly bad in for this type of model.   

I tried two different models:
*	**Logistic Regression** – Baseline for the model
*	**Decision Tree Classification** – Because of the sparse data from the many categorical variables, I thought a normalized regression like lasso would be effective.

## Decision Tree Classification

This decision tree shows that this telecom company has a very low customer retention rate with Senior Citizens as nearly half of them leave the company

![alt text](https://github.com/mkimball14/customer_churn/blob/main/images/SeniorCitizenTree.png "Senior Citizenship Decision Tree")

This decision tree shows that Telecom has a much lower customer retention rate with customers who do not have dependents. Telcom can potentially gain loyal customers by creating family plans.

## Model performance
The Decision Tree Classificaiton model far outperformed the other approaches on the test and validation sets. 
*	**Logistic Regression** : MAE = 11.22
*	**Decision Tree Classification**: MAE = 18.86

## Regression Analysis

![alt text](https://github.com/mkimball14/customer_churn/blob/main/images/Regression1.png "Classification Report")
![alt text](https://github.com/mkimball14/customer_churn/blob/main/images/Regression2.png "Confusion Matrix Plot")

## Heat Map with Confusion Matrix
![alt text](https://github.com/mkimball14/customer_churn/blob/main/images/Heatmap1.png "Heatmap")
![alt text](https://github.com/mkimball14/customer_churn/blob/main/images/ConfusionMatrix.png "Confusion Matrix")
