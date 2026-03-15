# Intermediate SQL - Sales Analysis

## 📌 Overview

This project analyzes customer behavior using SQL on the Contoso dataset. The analysis focuses on cohort analysis, customer segmentation, and customer retention to understand how customers generate revenue, how their value differs across segments, and how long they remain active.

The project was completed as part of the Intermediate SQL tutorial by [Luke Barousse](https://youtu.be/QKIGsShyEsQ?si=UEBnKrNJhV6hhEG6) to practice advanced SQL analysis techniques such as window functions, CTEs, and cohort analysis.

## 📂 Dataset Description

The analysis uses the **Contoso dataset**, a sample retail dataset that contains transactional sales data across multiple tables.

Key tables used in this project include:

- **sales** – Contains transaction-level sales data including order date, revenue, and product/customer identifiers.
- **customer** – Contains customer information used to track customer purchases and calculate lifetime value.
- **date** – A calendar table used for time-based analysis such as cohort grouping and retention analysis.
- **currencyexchange** – Contains currency exchange rates used for converting sales values across currencies.

These tables are connected through shared keys such as customer key, order date, and product key allowing analysis of customer purchasing behavior over time.   

## 🛠 Tools & Techniques Used 

- SQL
- PostgreSQL
- Window Functions
- Common Table Expressions (CTEs)
- Views
- Cohort Analysis
- Customer Segmentation

## 🎯 Business Questions 

1. **Customer Segmentation:** Who are the most valuable customers?
2. **Cohort Analysis:** How do different customer groups generate revenue?
3. **Retention Analysis:** Which customers have become inactive or churned?


## 🔍 Analysis & Insights

**1. Customer Segmentation Analysis :**

- Calculates Customer Lifetime Value (LTV) by summing total revenue for each customer.
- Segments customers into Low, Mid, and High value groups using 25th and 75th percentile thresholds.
- Analyzes total LTV, customer count, and average LTV for each customer segment.

💻 **Query :** [1_customer_segmentation.sql](/1_customer_segmentation.sql)

📊 **Key Findings :**

• High-Value Customers generate the largest share of revenue (66%) with the highest average LTV.

• Mid-Value customers represent the largest customer group and contribute 32% of total revenue.

• Low-Value customers contribute only 2% of total revenue and have the lowest lifetime value.

💡 **Business Insights :**

• High-Value Customers: Focus on retention strategies like loyalty programs and exclusive offers to keep these high-spending customers.

• Mid-Value Customers: Target this group with upselling and cross-selling strategies to convert them into high-value customers.

• Low-Value Customers: Use promotions or personalized offers to increase their spending or engagement.

**2. Cohort Analysis :**

- Counted customers and total revenue for each cohort year.
- Grouped customers based on their first purchase year to analyze cohort performance.
- Calculated average revenue per customer for each cohort.

💻 **Query :** [2_cohort_analysis.sql](/2_cohort_analysis.sql)

📊 **Key Findings :**

- Revenue per customer is decreasing over time, meaning newer customers spend less.
- Cohorts from 2022–2024 perform worse than earlier cohorts in average revenue per customer.
- Total revenue is increasing, but mainly because there are more customers, not because each customer spends more.

💡**Business Insights :**

- The business should focus on improving customer retention and increasing spending from new customers.
- Since newer cohorts generate lower revenue per customer, strategies like loyalty programs, promotions, or personalized offers could help increase customer value.
- Although total revenue is growing due to more customers, the company should focus on improving revenue per customer for long-term growth.

**3. Customer Retention :**

- Identifies each customer’s most recent purchase using a window function.
- Classifies customers as Active or Churned based on whether they made a purchase in the last 6 months.
- Calculates the number and percentage of active vs churned customers for each cohort year.

💻 **Query :** [3_retention_analysis.sql](/3_retention_analysis.sql)

📊 **Key Findings :**

- High churn across cohorts: Around 90–92% of customers are churned across most cohort years.
- Low active customer rate: Only about 8–10% of customers remain active after the initial purchase period.
- Consistent pattern across cohorts: The churn pattern is similar across all cohort years, indicating a systemic retention issue rather than a cohort-specific problem.

💡**Business Insights :**

- Improve customer retention strategies: The company should focus on post-purchase engagement such as loyalty programs, email follow-ups, or rewards.
- Encourage repeat purchases: Introduce discounts, bundles, or personalized recommendations to motivate customers to buy again.
- Analyze reasons for churn: Investigate factors such as product satisfaction, pricing, or customer experience to understand why customers stop purchasing.
