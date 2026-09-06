# OIBSIP Data Analytics - Level 1 Task 2: Customer Segmentation Analysis



### Project Overview

This project performs **Customer Segmentation Analysis** on an online retail transaction dataset. The goal is to group customers according to their purchasing behaviour and generate actionable marketing insights.

The analysis uses **RFM (Recency, Frequency, Monetary) analysis** to create customer-level behavioural features, followed by **K-Means clustering** to identify distinct customer segments.

### Objective

The main objectives are to:

- Inspect and clean the retail transaction data.
- Calculate key customer and order-level statistics.
- Build RFM features:
  - **Recency** – how recently a customer purchased.  

  - **Frequency** – how many distinct orders a customer placed.
  - **Monetary** – how much a customer spent.
- Transform and standardise the RFM features.
- Determine a suitable number of clusters using the Elbow Method and Silhouette Score.
- Apply K-Means clustering.
- Visualise and profile the resulting customer segments.
- Recommend suitable marketing actions for each segment.

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook
- RFM Analysis
- K-Means Clustering

## Dataset

The project uses the **Online Retail** transaction dataset.

The original dataset contains:

- **541,909 rows**
- **8 columns**

Important columns include:

`InvoiceNo`, `StockCode`, `Description`, `Quantity`, `InvoiceDate`, `UnitPrice`, `CustomerID`, and `Country`.

## Data Cleaning

The dataset was checked for missing values, duplicates, cancelled transactions, and invalid prices.

The following cleaning steps were performed:

1. Removed exact duplicate rows.
2. Removed transactions without a `CustomerID`.
3. Filled missing product descriptions with `UNKNOWN ITEM`.
4. Removed cancelled transactions.
5. Removed transactions with non-positive quantity or unit price.
6. Created `LineTotal = Quantity × UnitPrice`.

After cleaning:

- **392,692 genuine purchase lines** remained.
- **4,338 unique customers** remained.

## Descriptive Statistics

The main results were:

| Metric | Result |
|---|---:|
| Average Order Value | £479.56 |
| Median Order Value | £302.57 |
| Average Purchase Frequency | 4.27 orders/customer |
| Median Purchase Frequency | 2 orders/customer |
| Average Customer Lifetime Value | £2,048.69 |
| Median CLV | £668.57 |
| Total Revenue | £8,887,208.89 |

The distributions were strongly right-skewed. Most customers had relatively low purchase frequency and spending, while a smaller group of customers generated substantially higher value.

## RFM Analysis

Customer-level RFM features were calculated using:

- **Recency:** Days since the customer's latest purchase.
- **Frequency:** Number of distinct invoices/orders.
- **Monetary:** Total customer spending.

The analysis used **10 December 2011** as the snapshot date.

To reduce the effect of the highly skewed Monetary feature, `Monetary` was log-transformed using `log1p()` before standardisation.

The three modelling features were:

- `Recency`
- `Frequency`
- `MonetaryLog`

These were standardised using `StandardScaler`.

## Choosing the Number of Clusters

The **Elbow Method** was used to examine K-Means inertia for different values of `k`. The curve showed a major reduction in inertia up to approximately **k = 4**, after which the improvement became more gradual.

A Silhouette Score check was also performed:

| k | Silhouette Score |
|---:|---:|
| 2 | 0.372 |
| 3 | **0.423** |
| 4 | 0.417 |
| 5 | 0.409 |
| 6 | 0.365 |
| 7 | 0.358 |
| 8 | 0.351 |

The highest silhouette score was **0.423 at k = 3**. However, the final notebook used **k = 5** to retain five distinct, business-friendly customer segments identified through the RFM profiles.

## K-Means Clustering Results

The final model used:

`K = 5`

The five resulting clusters were profiled and assigned business-friendly segment labels.

| Cluster | Segment | Customers | % of Customers | Avg. Recency | Avg. Frequency | Avg. Monetary |
|---:|---|---:|---:|---:|---:|---:|
| 2 | Champions | 8 | 0.2% | 1.9 | 121.8 | £80,018.9 |
| 3 | Loyal Customers | 214 | 4.9% | 12.0 | 22.2 | £16,288.8 |
| 1 | Potential Loyalists | 1,542 | 35.5% | 39.2 | 5.5 | £2,399.1 |
| 0 | At Risk / Needs Attention | 1,603 | 37.0% | 55.5 | 1.8 | £416.7 |
| 4 | Hibernating | 971 | 22.4% | 256.8 | 1.5 | £405.6 |

### Key Segment Insights

- **Champions:** A very small group with extremely recent, frequent, and high-value purchases.
- **Loyal Customers:** Recent and highly active customers with strong spending behaviour.
- **Potential Loyalists:** A large active group with potential to develop into more loyal and valuable customers.
- **At Risk / Needs Attention:** The largest segment, with declining recency and relatively low frequency and spending.
- **Hibernating:** Customers with very high recency and low purchase frequency, indicating prolonged inactivity.

The **At Risk / Needs Attention** and **Hibernating** groups together represent **59.4% of the customer base**, making customer re-engagement a major opportunity.

## Visualisations

The notebook includes:

1. Order Value Distribution
2. Purchase Frequency Distribution
3. Customer Lifetime Value Distribution
4. Elbow Method for Optimal `k`
5. Recency vs Frequency
6. Frequency vs Monetary
7. Recency vs Monetary
8. Customers per Cluster

The visualisations show that Recency is particularly useful for separating inactive customers, while Frequency and Monetary value help distinguish the more active and valuable customer groups.

## Recommended Marketing Actions

| Segment | Recommended Action |
|---|---|
| Champions | VIP/loyalty programme, exclusive access, rewards, referrals and reviews |
| Loyal Customers | Upselling, cross-selling and personalised offers to encourage Champion status |
| Potential Loyalists | Personalised recommendations, second/next-purchase incentives and loyalty-building campaigns |
| At Risk / Needs Attention | High-priority win-back campaigns, personalised discounts and re-engagement messages |
| Hibernating | Low-cost reactivation campaigns and limited-time offers without excessive marketing investment |

## Conclusion

The project demonstrates how transactional retail data can be converted into meaningful customer segments using **RFM analysis and K-Means clustering**.

The analysis identified five distinct customer groups with different levels of engagement and value. The results can help businesses focus retention efforts on valuable customers while using targeted re-engagement strategies for inactive and at-risk customers.

## Project Structure

```text
DataAnalytics-L1-CustomerSegmentation/
│
├── CustomerSegmentationAnalysis.csv
├── CustomerSegmentationAnalysis.ipynb
└── README.md
```


