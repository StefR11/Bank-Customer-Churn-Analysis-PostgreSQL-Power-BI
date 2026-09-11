# Bank-Customer-Churn-Analysis-PostgreSQL-Power-BI
In this project, I analysed customer churn for a bank using PostgreSQL and Power BI

The project started as a Power BI project, using a raw CSV file containing 10,000 bank customer records. As I developed the analysis, I decided to extend the project by carrying out the data cleaning, categorisation and analysis in PostgreSQL as well. This allowed me to reproduce and compare some of the calculations and analysis before creating the final Power BI dashboard.

The overall process was:
Raw CSV → PostgreSQL → Data Preparation → SQL Analysis → Power BI → DAX → Dashboard → Business Insights

What is Customer Churn?

Customer churn refers to customers who leave a business. The churn rate measures the proportion of customers who have left compared with the total customer base.
Analysing churn against different customer characteristics can help a business identify segments with higher levels of customer attrition and provide information that can support customer-retention strategies.

Dataset

The dataset contains 10,000 bank customer records and includes information such as:
Customer ID
Credit score
Country
Gender
Age
Tenure
Account balance
Number of products
Credit-card ownership
Active/inactive status
Churn status

Data Preparation & Analysis

I used PostgreSQL and Power Query to clean and transform the raw data.
The main preparation steps included:
Removing unnecessary columns
Renaming columns and changing data types
Creating product categories
Creating age groups
Creating credit-score groups
Creating account-balance groups
Creating reference tables to control the order of categories
Creating customer and churn KPIs
In PostgreSQL, I also reproduced key Power BI calculations and analysed churn across different customer segments using SQL. The SQL work includes CTEs, CASE WHEN, ROW_NUMBER(), PARTITION BY, joins and aggregate calculations.

Power BI Dashboard

I created an interactive Power BI dashboard to analyse the customer base and identify patterns in customer churn.
Main KPIs
KPI	Result
Total Customers	10,000
Customers Lost	2,037
Churn Rate	20.4%
Target Churn Rate	15%
The dashboard includes customer breakdowns by gender, activity status, credit-card status, country and products.
It also analyses customer numbers and churn rate by:
Age group
Credit-score group
Account-balance group
A Churn Status slicer allows the report to be filtered between churned and non-churned customers, while a gauge chart compares the actual churn rate against the 15% target.

Key Findings

The main findings from my analysis were:
The overall churn rate is 20.4%, which is above the 15% target.
The 51–60 age group shows particularly high churn in several of the analyses.
Customers in the lowest credit-score category show a very high observed churn rate.
Customers with account balances above £200K show elevated churn.
Product 1 has an observed churn rate of approximately 27.7%.
Inactive customers have an observed churn rate of approximately 26.9%.
These findings show associations within the dataset and would require further investigation to understand the reasons behind the higher churn rates.

Business Insights

Based on the analysis, I identified several areas that could be investigated further:
Why is churn particularly high among customers aged 51–60?
What factors may be contributing to the higher churn among inactive customers?
Why do customers with higher account balances show elevated churn?
Is there something about Product 1 that could be contributing to customer attrition?
What are the characteristics of customers with very low credit scores who have churned?
The purpose of these questions is not to assume that these factors cause churn, but to identify areas where further customer and business analysis could be useful.

DAX Measures
The main DAX measures used in the Power BI report were:
Total Number of Customers =
COUNT('Customer Data'[Customer ID])
Number of Customers Lost =
CALCULATE(
    [Total Number of Customers],
    'Customer Data'[Churn Status] = "Churned"
)
Churn Rate =
[Number of Customers Lost] /
[Total Number of Customers]
The PostgreSQL analysis also reproduced these key calculations in SQL.

Tools Used

PostgreSQL / SQL — data preparation, transformation and analysis
Power Query — data cleaning and transformation
Power BI — data modelling and dashboard development
DAX — KPI and churn calculations
CSV — raw data source

Dashboard

Bank Customer Churn Dashboard
<img width="1138" height="650" alt="image" src="https://github.com/user-attachments/assets/74fef4f3-46f1-4a41-9fdf-7590e05fab9f" />

