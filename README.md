# Telecom Customer Churn Analysis: Project Overview 
* Used logistic regression and decision tree classification models to predict what factors lead to customer churn in a telecommunications company
* Visualized customer data using both Python and Tableau

## Code and Resources Used 
**Tableau Desktop:** 2020.3  
**Python Version:** 3.7  
**Packages:** pandas, numpy, sklearn, matplotlib

## EDA
I looked at the distributions of the data and the value counts for the various categorical variables. Below are a few highlights from the pivot tables. 

## Model Building 

First, I transformed the categorical variables into dummy variables. I also split the data into train and tests sets with a test size of 20%.   

I tried two different models and evaluated them using Mean Absolute Error. I chose MAE because it is relatively easy to interpret and outliers aren’t particularly bad in for this type of model.   

I tried two different models:
*	**Logistic Regression** – Baseline for the model
*	**Decision Tree Classification** – Because of the sparse data from the many categorical variables, I thought a normalized regression like lasso would be effective.

## Decision Tree Classification

**Senior Citizens Retention:** This decision tree shows that this telecom company has a very low customer retention rate with Senior Citizens as nearly half of them leave the company. If Telecom wants to retain these customers, they would need to address their needs more closely.

![alt text](https://github.com/mkimball14/customer_churn/blob/main/images/SeniorCitizenTree.png "Senior Citizenship Decision Tree")

**Dependents Retention:** This decision tree shows that Telecom has a much lower customer retention rate with customers who do not have dependents. Telcom can potentially gain loyal customers by creating family plans.

![alt text](https://github.com/mkimball14/customer_churn/blob/main/images/DependentsTree.png "Senior Citizenship Decision Tree")

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
