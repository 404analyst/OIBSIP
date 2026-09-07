

# OIBSIP Level 1   — Task 3: Data Cleaning
## Project Overview
This project focuses on cleaning a messy customer sales dataset into an analysis-ready dataset using Python and pandas. The workflow covers data quality assessment, missing value treatment, duplicate removal, standardisation, outlier detection, and data type correction.
The project demonstrates a complete, professional data cleaning workflow with every decision documented and justified.

## Objective
To take a deliberately messy dataset and systematically transform it into a clean dataset, producing a data quality report, a before-vs-after comparison, and a final cleaned CSV file.

## Technologies Used
- Python
- Pandas
- NumPy
- Jupyter Notebook 
## Dataset
The dataset is a synthetic customer sales dataset containing:

- Customer ID
- Name
- Age
- Gender
- Country
- Join Date
- Purchase Amount
- Payment Method
- Email

The raw dataset contains 1,025 records and 9 columns.

## Project Workflow
1. Loaded and inspected the dataset
2. Generated a data quality report (nulls, duplicates, dtype issues, value-range anomalies)
3. Checked data types and identified columns stored with the wrong type
4. Corrected data types (Age and Purchase Amount to numeric, Join Date to datetime)
5. Standardised inconsistent categorical labels (Gender, Country, Payment Method)
6. Handled missing values with a column-specific strategy (median, mode, or row deletion), justified per column
7. Identified and removed 25 exact duplicate rows
8. Detected outliers in Age and Purchase Amount using the IQR method
9. Removed impossible values and capped statistically extreme values
10. Applied a final data type pass to lock in the correct schema
11. Built a before-vs-after summary table (row count, nulls, duplicates, dtype accuracy)
12. Exported the cleaned dataset to a new CSV file

## Cleaning Results
The cleaning pipeline achieved the following results on the dataset:
- Row count: 1,025 → 938
- Missing values: present across 7 columns → 0
- Duplicate rows: 25 → 0
- Columns with correct dtype: 7 / 9 → 9 / 9

## Key Findings
- Missing values required different strategies per column — median imputation suited skewed numeric fields (Age, Purchase Amount), mode imputation suited low-cardinality categoricals (Gender, Country, Payment Method), and row deletion was reserved for fields with no fair substitute (Join Date, Email).
- Duplicate rows and inconsistent category labels (e.g. "Male"/"male"/"M") were the largest sources of noise before cleaning.
- The IQR method distinguished between statistically unusual but plausible values (retained or capped) and biologically/logically impossible values such as negative purchase amounts or ages of 999 (removed as data entry errors).



## Project Structure
```text
TaskDataAnalytics-L1aningData/
│
├── CustomerSales.csv
├── Cleaned_CustomerSales.csv
├── CustomerSales.ipynb
└── README.md
```

## Conclusion
This project demonstrates a complete data cleaning workflow for a customer sales dataset, from data quality assessment and missing value treatment to duplicate removal, standardisation, outlier handling, and final export — resulting in a fully null-free, duplicate-free, correctly typed dataset ready for analysis.