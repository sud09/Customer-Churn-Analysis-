# Customer Churn Analysis

### Dashboard Link : https://app.powerbi.com/groups/me/reports/49077f6f-6aad-4b54-8d48-bdd301caad0b/ReportSection?experience=power-bi

## Overview 

Customer churn, also referred to as churn rate or customer attrition, is the rate at which customers stop doing business with a company over a specified period. It is calculated by dividing the number of customers lost during that period by the total number of active customers at the beginning of the period.

## Project Objective

The objective of this analysis is to identify the key factors contributing to the increased customer churn rate at the bank. By providing these insights to the business users, they can make informed decisions and develop strategies to enhance customer retention and reduce churn rate.

## About the Data

The raw data is provided in a CSV file containing 10,000 rows. It was sourced from a commercial bank aiming to enhance its customer churn rate.

## Tools Used

 Power BI and Power Query.

## Analytical Steps


- **Data Preparation:** Cleaning and preparing the raw data for analysis.

        1. Importing Data: Imported the data into Power BI.
        2. Renaming Data: Renamed the data from "customer_churn_data" to "Customer Data" for clarity.
        3. Header Adjustment: Promoted the first row of the data to become the header to eliminate auto-generated headers.
        4. Removing Irrelevant Data: Eliminated the "estimated_salary" column as it was deemed irrelevant for analysis. 
           This column contained estimated values, and another column with actual account balance information was considered more useful.

- **Data Categorization and Grouping:** Organizing data into categories and groups for better analysis.

       1.  Products Number Column: Utilized the "Replace Values" option to clearly label the data in the "products_number" column. 
           Replaced product numbers 1, 2, 3, and 4 with "Prod 1," "Prod 2," "Prod 3," and "Prod 4," respectively. 
           Deleted the original column after replacement.
       2. Age, Credit Score, and Balance Columns: Observed a wide range between the minimum and maximum values in these columns.

         - Age Column: Had 60 distinct values with a minimum of 18 and a maximum of 82.
         - Credit Score Column: Had 354 distinct values with a minimum of 376 and a maximum of 850.
         - Balance Column: Had 649 distinct values with a minimum of 0 and a maximum of 213146.20.

       3. Grouped each of these columns using the conditional column function. 
- **Formatting:** Ensuring data is in the correct format for analysis.

        1. Churn, Active Member, and Credit Card Columns: Formatted these columns to improve clarity.
           - Active Member Column: Changed values from 0 to "Inactive" and from 1 to "Active."
           - Churn Column: Changed values from 0 to "Not Churned" and from 1 to "Churned."
           - Credit Card Column: Changed values from 0 to "Not Owned" and from 1 to "Owned."
- **Data Transformation** Transforming data to extract useful insights.

        - Created queries to organize data for better analysis and reporting.
        - Created queries to organize data for analysis and reporting. However, encountered issues with grouping symbols (<, >=, etc.) 
          as they were treated as text, leading to sorting problems.

- **Data Modeling:** Applying statistical models to analyze and predict customer churn.

        - Explored the relationships between tables and arranged them to have all the fact tables at the top of the dimension table for easier visualization. 
          Power BI correctly detected the cardinality of the model relationship as many-to-one.

- **Visualization - Report:** Creating visualizations to present the analysis findings.

        - Started the report by creating several DAX measures for calculations:

        1. Customers: Number of customers.
           DAX : Customers = COUNT('Customer Data'[Customer ID])

        2. Churn Rate: Percentage of customers who have churned.
           DAX : Churn Rate = 'Customer Data'[Customer Lost] / 'Customer Data'[Customers]

        3. Customers Churned: Number of customers who have churned.
           DAX : Customer Churned = CALCULATE(COUNT('Customer Data'[Churn Status]),'Customer Data'[Churn Status] = "Churned")

                        Customers: 10K
                        Customers Churned: 2037
                        Customers Not Churned : 7963
                        Churn Rate: 20.4%


     Finally , built a report focusing on key factors such as account balance, age group, activity status, gender, and credit score, analyzing their effects on the churn rate. This provided insights into areas where the bank could make necessary improvements.

 ![Customer_Churn_Anslysis_Snap](https://github.com/sud09/Power-Bi-Projects-/assets/36404812/939c53ae-e218-40ba-8dde-3d04cb61aeba)"


- **Insights:** Extracting key insights from the data analysis.

        1. Gender: The churn rate for male customers is 65%, significantly higher than the overall male churn rate of 25%.

        2. Credit Score and Credit Card: Customers with credit card facility show the highest churn rate among those with a credit score of over 400.

        3. Account Balance: Surprisingly, customers with account balances of <=200k are the most churned in terms of account balance.

        4. Age Group: The churn rate is very high at 56.2% for middle-aged customers between 51–60 years old.


- **Recommendation:** Providing recommendations based on the insights to improve customer retention.

        1. Targeted Products for Seniors: Consider creating products targeted at seniors close to their early retirement age to retain them.

        2. Incentive Program for Long-Term Customers: Implement an incentive program for customers who have
           maintained a longer relationship with the bank to increase retention.

        3. Exclusive Packages for High-Balance Customers: Offer exclusive packages such as travel and
        vacation packages, subsidized investment portfolios, etc., for customers with account balances >200k to reduce churn rate in this group.

        4. Investigation into Prod 2 Churn Rate: Investigate the reasons for the 100% churn rate among Prod 2 customers with account balances of 1k-10k and devise strategies to re-engage them.

        In summary, focus on these recommendations to  retain customers in the age group of 51–60, those with low credit scores, and those with high account balances (>200k), to reduce churn rate.

- **Conclusion:** Summarizing the findings and the impact of the recommendations. 
  
  In this Power BI analysis, I followed a comprehensive data analysis process from raw data to cleaned data and report building, ensuring data quality throughout. The analysis provided valuable insights into major factors contributing to customer churn at the bank.

  Stakeholders can use this report to manage churn, especially for salaried customers, by focusing on key factors and evaluating the results of their changes periodically.  
  
 



