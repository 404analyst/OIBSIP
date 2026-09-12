# # OIBSIP Data Analytics – Level 2 Task 3: Fraud Detection

### Project Overview

This project focuses on detecting fraudulent credit card transactions using machine learning.

The main challenge is **class imbalance**, because fraudulent transactions are extremely rare compared with legitimate transactions. Therefore, accuracy alone is not a reliable measure of model performance.

The project uses **SMOTE (Synthetic Minority Over-sampling Technique)** to address the imbalance in the training data.

---

## Dataset

The project uses the **Credit Card Fraud Detection** dataset from Kaggle.

* **Transactions:** 284,807
* **Fraudulent transactions:** 492
* **Legitimate transactions:** 284,315
* **Fraud rate:** approximately 0.172%

### Dataset Link

[Kaggle – Credit Card Fraud Detection](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud)

The target variable is `Class`:

* `0` = Legitimate transaction
* `1` = Fraudulent transaction

The dataset contains `Time`, `Amount`, and anonymized features `V1` to `V28`.

---

## Objectives

The main objectives of this project are:

* Analyze the class imbalance.
* Explore transaction amounts for fraud and non-fraud cases.
* Analyze transaction timing.
* Handle class imbalance using SMOTE.
* Split the dataset using stratification.
* Train multiple classification models.
* Evaluate the models using appropriate fraud detection metrics.
* Analyze important features.
* Discuss how the solution could scale to a high-volume transaction system.

---

## Technologies Used

* Python
* Pandas
* NumPy
* Scikit-learn
* Imbalanced-learn
* Matplotlib
* Seaborn
* Jupyter Notebook

---

## Project Workflow

### 1. Data Loading

The dataset is loaded using Pandas and basic information such as shape, columns, data types and missing values is examined.

### 2. Exploratory Data Analysis

The analysis includes:

* Class distribution
* Fraud percentage
* Transaction amount distribution
* Approximate time-of-day analysis

### 3. Class Imbalance

Only about **0.172%** of the transactions are fraudulent.

This makes the dataset highly imbalanced. A model that predicts almost every transaction as legitimate could still achieve very high accuracy while failing to detect fraud.

Therefore, accuracy is not used as the main evaluation metric.

### 4. Train-Test Split

The data is divided into training and testing sets using stratification.

This ensures that fraudulent transactions are represented in both sets.

### 5. Feature Scaling

`Time` and `Amount` are standardized before model training.

The scaler is fitted only on the training data to avoid data leakage.

### 6. SMOTE

SMOTE is applied **only to the training data**.

It creates synthetic examples of the minority fraud class and helps the models learn from the highly imbalanced dataset.

The original test set is kept unchanged for realistic evaluation.

### 7. Machine Learning Models

Two classification models are trained:

1. **Logistic Regression**
2. **Random Forest**

Logistic Regression provides a simple baseline, while Random Forest can capture more complex relationships between the features.

---

## Model Evaluation

The models are evaluated using:

* **Precision**
* **Recall**
* **F1-Score**
* **ROC-AUC**

Accuracy is not treated as the primary metric because of the extreme class imbalance.

### Why Recall Matters

Recall measures how many of the actual fraudulent transactions are successfully detected.

A low recall means that many fraudulent transactions are being missed.

However, precision is also important because a model with too many false positives may incorrectly flag legitimate customers.

Therefore, fraud detection requires a balance between **Recall and Precision**, depending on the cost of missed fraud and false alerts.

---

## Feature Analysis

Random Forest feature importance is used to identify the features that contribute most to the model's predictions.

Logistic Regression coefficients are also analyzed to understand the direction and relative strength of feature contributions.

The `V1`–`V28` features are anonymized PCA components, so their business meaning cannot be directly interpreted.

---

## Scalability

The project also considers how the fraud detection system could handle around **1 million transactions per hour**.

A production system could use:

* Real-time or streaming data processing
* Automated feature engineering
* A trained model kept in memory
* Parallel processing
* Risk-based transaction thresholds
* Continuous model monitoring
* Periodic retraining with newly labeled transactions

SMOTE would be used during model training, not for generating synthetic transactions during real-time prediction.

---

## Key Learning

This project demonstrates that fraud detection is not simply a classification problem. The severe class imbalance requires careful data preparation and appropriate evaluation metrics.

The project also demonstrates the importance of preventing data leakage when applying techniques such as SMOTE.

---

## Project Structure

```text
OIBSIP-DataAnalytics/
│
└── DataAnalytics-L2-Task3-FraudDetection/
    │
    ├── creditcard.csv
    ├── Fraud_Detection.ipynb
    └── README.md
```

---

## References

* Kaggle: Credit Card Fraud Detection Dataset
* Imbalanced-learn Documentation: SMOTE
* Scikit-learn Documentation: Classification Models and Metrics
 3
