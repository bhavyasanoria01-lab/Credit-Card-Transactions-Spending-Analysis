# Credit-Card-Transactions-Spending-Analysis - End to End Data Analytics Project
A complete data analytics project covering data cleaning in Python, business analysis using MYSQL, and an interactive dashboard built in Power BI, based on a dataset of 65,000 credit card transactions.

## 🛠️ Tools & Technologies
Python | MYSQL | Power BI | Excel 

## Project Overview
This project analyzes 65,000 real world credit card transactions to uncover spending patterns and detect fraudulent activity. The goal was to go from a raw dataset all the way to a two page interactive dashboard covering both spending behaviour and fraud analysis. Simulating the kind of work done by analysts in banking and fintech companies.

##  📁 Dataset Description
- **Source** - Kaggle
- **Size** - 65,000 rows and 18 columns (after cleaning)
- **Columns** -  trans_date_trans_time, merchant, category, amt, first, last, 
gender, city, state, job, dob, is_fraud, age, age_group, 
year, month, day_of_week, hour

- **Time Period** - 2019 to 2020

##  🧹 Data Quality Issues Found and Fixed
- Removed **13** irrelevant columns including street, zip, 
  unix_time, merch_lat, merch_long to simplify the dataset
- Handled missing values in merch_zipcode, dropped column 
  entirely due to **~58K** null values
- **Converted** trans_date_trans_time from **string** to proper 
  **datetime** format for time based analysis
- Engineered **6** new features like **age, age_group, year, month, 
  day_of_week, hour**, extracted from existing columns
- Categorized customers into **4** age groups for segmentation analysis


##  🔍 SQL Business Analysis 
After cleaning, the data was imported into MySQL and 13 business questions were answered through SQL queries — ranging from basic aggregations to window functions and CTEs.
### Questions - 
- Q1. What is the total transaction amount, total number of transactions and average transaction value overall?
- Q2. Which spending category has the highest total transaction amount? Show all categories ranked.
- Q3. How many transactions were fraudulent vs legitimate? Show count and percentage of total.
- Q4. What is the gender split of our customers — total spend and transaction count by gender?
- Q5. Which state has the highest total spending? Show top 10 states.
- Q6. What is the total spend and fraud rate by category? I want to know which categories are most vulnerable to fraud.
- Q7. What is the average transaction amount for fraud vs non-fraud transactions? Is there a pattern?
- Q8. Who are the top 10 customers by total spend? Show their name, state, job and total amount.
- Q9. What is the spending breakdown by age group? Which age group spends the most?
- Q10. Find the top 3 spending categories per state using window functions.
- Q11. What hour of the day do most fraudulent transactions happen? Show fraud count and fraud % by hour.
- Q12. Find customers who have more than 5 fraudulent transactions — these are either victims or high risk accounts.
- Q13. Show year over year spending growth — compare 2019 vs 2020 total spend and calculate growth %.


##  💡 Key Business Insights
- Most of the revenue comes from **Middle Aged** and **Late Middle Aged** people both contributing $1.06M each
- The category which account for the most transactions is **Grocery**
- **Females** spent more than **Males**
- Most of the frauds occured at **11 P.M.**, which means fraudsters are most active at the night time when people are sleeping or not in their full attention
- Fraud rate percentage is **0.56%**
- Most of the frauds happened with **Seniors** 
- Average fraud amount is **$498.5** which is a lot more than Average Transaction amount, which is **$69**
- Most of the frauds occured in the month of **January**


##  📊 Dashboard Preview

![Dashboard Page 1](https://github.com/bhavyasanoria01-lab/Credit-Card-Transactions-Spending-Analysis/blob/761f3263e2aa6e7ff577cb47e38d206b4f5dd3db/Page%201.png)

![Dashboard Page 2](https://github.com/bhavyasanoria01-lab/Credit-Card-Transactions-Spending-Analysis/blob/237834069f8474e1221444598da056eb83065527/Page%202.png)

##  📝 Learnings & Challenges
This was my second end to end data analytics project and a significant step up from the first one. Working with **65000** rows for the first time taught me the importance of query optimization. I also learned new SQL concepts in this project including the **LAG()** window function for year over year calculations and the **SUM(binary_column)** pattern for counting fraud transactions efficiently. The biggest analytical challenge was correctly calculating fraud rate — my first attempt filtered the data with WHERE is_fraud = 1 which made the percentage always return 100%. Understanding why that was wrong deepened my understanding of how SQL executes queries. On the dashboard side, building a dedicated fraud analysis page taught me how to tell a story with data and not just showing numbers but guiding the viewer from what happened to why it matters.
