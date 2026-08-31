# OIBSIP Level 1   — Task 1: Exploratory Data Analysis on Retail Sales Data

### Project Overview

This project was completed as part of the OIBSIP Data Analytics Internship, Level 1 Task 1.

The main objective of this project is to perform Exploratory Data Analysis (EDA) on a retail sales dataset to understand customer behaviour, product performance, sales patterns, and other useful business insights.

The analysis was performed using Python, Pandas, NumPy, Matplotlib, Seaborn, and Jupyter Notebook.

## Objective

The objectives of this project are:

* Inspect and understand the retail sales dataset
* Check the dataset structure, data types, missing values, and duplicate records
* Calculate descriptive statistics for numerical variables
* Analyze monthly and quarterly sales trends
* Analyze customer age groups and gender distribution
* Identify the top 10 best-selling products
* Analyze revenue by product category
* Study relationships between numerical variables using correlation analysis
* Create additional visualizations to identify useful patterns
* Provide actionable business recommendations based on the findings

## Tech Stack

Python

Pandas

NumPy

Matplotlib

Seaborn

Jupyter Notebook

## Dataset

The project uses the Store Sales Dataset uploaded by Hassan Jameel Ahmed on Kaggle.

The dataset contains information about customers, products, purchases, payment methods, ratings, discounts, and previous purchases.

The main columns are:

| Column             | Description                  |
| ------------------ | ---------------------------- |
| CustomerID         | Customer identifier          |
| Age                | Customer age                 |
| Gender             | Customer gender              |
| Category           | Product category             |
| ItemPurchased      | Purchased product            |
| Amount             | Purchase amount              |
| Season             | Season of purchase           |
| PaymentMethod      | Payment method used          |
| ItemRating         | Item rating                  |
| DiscountApplied(%) | Discount percentage          |
| PreviousPurchases  | Number of previous purchases |

## Date Information

The original dataset did not contain a transaction date. Since monthly and quarterly sales analysis is part of the task requirements, TransactionDate, Month, and Quarter columns were added to the dataset.

The dates are synthetic and were generated for the purpose of demonstrating the time-series analysis. They are not the original historical transaction dates.

The original customer, product, category, amount, and other source information was not changed.

Because the dates are synthetic, the monthly and quarterly trends should not be considered actual historical sales performance.

## Exploratory Data Analysis

### 1. Initial Dataset Inspection

The dataset was checked for its number of rows and columns, column names, data types, missing values, and duplicate records.

The dataset contains 5,000 purchase records and no missing values or duplicate rows.

### 2. Descriptive Statistics

Mean, median, mode, and standard deviation were calculated for the numerical variables.

The purchase amount has a mean of approximately 285.09 and a median of approximately 122.49. The higher mean compared with the median indicates that some high-value purchases increase the average purchase amount.

### 3. Monthly Sales Analysis

Monthly sales were calculated by grouping the purchase amount by month and visualized using a line chart.

The chart demonstrates how monthly sales can be compared over time. However, the dates are synthetic, so the monthly pattern should not be interpreted as actual historical sales performance.

### 4. Quarterly Sales Analysis

Quarterly sales were calculated and visualized using a line chart.

This provides a broader view of sales across the year. The results are also based on the synthetic transaction dates.

### 5. Customer Age Analysis

Customers were divided into the following age groups:

* 20-24
* 25-34
* 35-44
* 45-54
* 55-64
* 65+

The 55-64 age group is the largest customer segment in the dataset.

### 6. Gender Analysis

The dataset contains:

* Female: 2,504 purchase records
* Male: 2,496 purchase records

The distribution is therefore almost evenly balanced between the two genders.

### 7. Top 10 Best-Selling Products

The top 10 products were identified based on the number of purchase records.

Products such as Sandals, Formal Shoes, and Sneakers are among the most frequently purchased products.

These products should receive proper inventory attention because they have high purchase volume.

### 8. Revenue by Product Category

Total revenue was calculated for each product category.

Electronics generates the highest revenue by a large margin compared with the other categories.

This makes Electronics an important category for inventory planning and revenue management.

### 9. Correlation Analysis

A correlation matrix and heatmap were used to study relationships between numerical variables.

The strongest positive relationship is between DiscountApplied(%) and PreviousPurchases, with a correlation of approximately 0.73.

However, correlation does not mean that one variable causes another. Further analysis would be required to understand the reason behind this relationship.

### 10. Additional Analysis

An additional visualization was created to examine revenue by product category and gender.

This analysis shows that differences in revenue between genders are strongly affected by the product categories associated with each gender.

Therefore, gender alone should not be used to conclude that one group spends more than another.

## Key Findings

The main findings from the analysis are:

1. The dataset contains 5,000 purchase records and has no missing values or duplicate rows.
2. The mean purchase amount is much higher than the median, suggesting the presence of some high-value purchases.
3. The 55-64 age group is the largest customer segment.
4. The number of male and female purchase records is almost equal.
5. Footwear products such as Sandals, Formal Shoes, and Sneakers have high purchase volume.
6. Electronics generates the highest revenue among the product categories.
7. Discount percentage and previous purchases have a relatively strong positive correlation.
8. Product category composition has a strong influence on the observed revenue differences between genders.

## Business Recommendations

### 1. Focus on Electronics Inventory

Electronics generates the highest revenue. The business should maintain sufficient stock of high-value electronic products and monitor stockouts.

### 2. Maintain Stock for Popular Products

Frequently purchased products such as footwear should have appropriate inventory levels to avoid losing sales because of stock shortages.

### 3. Use Behaviour-Based Customer Segmentation

Customer segmentation should consider age, previous purchases, product category, purchase amount, and purchasing behaviour instead of relying only on gender.

### 4. Test Discount Strategies

The relationship between discounts and previous purchases should be investigated further. The business can run targeted discount campaigns and compare the results to determine whether discounts increase repeat purchases.

### 5. Collect Actual Transaction Dates

Future datasets should include real transaction dates. This would allow the business to perform accurate monthly, quarterly, yearly, seasonal, and sales forecasting analysis.

## Project Structure

```text
Data-Analytics-Level-1-Task-1-EDA-on-Retail-Sales-Data/
|
|-- store_sales.csv
|-- store_sales.ipynb
|-- README.md
|-- requirements.txt
```

## Data Limitation

The original dataset did not contain transaction dates. Synthetic dates were added only to demonstrate the monthly and quarterly analysis required for this task.

The synthetic dates should not be considered real historical transaction information.

For future analysis, a dataset containing genuine transaction dates should be used.

## Conclusion

The exploratory data analysis provides several useful insights into the retail sales data. Electronics is the strongest revenue-generating category, while footwear products have high purchase volume. The 55-64 age group represents the largest customer segment, and the gender distribution is almost balanced.

The correlation analysis also shows a relatively strong relationship between discount percentage and previous purchases. However, this relationship does not prove that discounts cause customers to make more purchases.

The analysis demonstrates how Python and data visualization can be used to understand retail data and support business decisions. Future analysis would be more reliable if actual transaction dates were available.

## Project Information

Internship: OIBSIP Data Analytics Internship

Level: Level 1

Task: Task 1 - EDA on Retail Sales Data

Tools: Python, Pandas, NumPy, Matplotlib, Seaborn, Jupyter Notebook
