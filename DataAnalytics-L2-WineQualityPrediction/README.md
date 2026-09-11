# OIBSIP Data Analytics – Level 2 Task 2: Wine Quality Prediction

### Project Overview

This project focuses on predicting wine quality using machine learning classification algorithms.

The Wine Quality dataset contains physicochemical properties of wine, such as acidity, residual sugar, chlorides, density, pH, sulphates, and alcohol. These properties are used to predict the overall quality category of the wine.

The original quality scores were grouped into three categories:

* **Low:** Quality scores 3–4
* **Medium:** Quality scores 5–6
* **High:** Quality scores 7–8

Three classification models were trained and compared:

* Random Forest Classifier
* Stochastic Gradient Descent (SGD) Classifier
* Support Vector Classifier (SVC)

---

## Objective

The main objectives of this project are to:

* Explore and understand the Wine Quality dataset
* Analyze the distribution of wine quality scores
* Identify class imbalance
* Explore relationships between physicochemical features
* Create meaningful wine quality categories
* Train multiple classification models
* Compare model performance
* Identify important features using Random Forest
* Select the most suitable model based on the evaluation results

---

## Dataset

The project uses the **Wine Quality dataset** from the UCI Machine Learning Repository.

Dataset:
https://archive.ics.uci.edu/dataset/186/wine+quality

The red wine dataset contains:

* **1,599 observations**
* **11 physicochemical features**
* **1 quality score column**

### Features

* Fixed acidity
* Volatile acidity
* Citric acid
* Residual sugar
* Chlorides
* Free sulfur dioxide
* Total sulfur dioxide
* Density
* pH
* Sulphates
* Alcohol

The original target variable is `quality`.

---

## Tools and Technologies

* Python
* Jupyter Notebook
* pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn

### Machine Learning Models

* Random Forest Classifier
* SGD Classifier
* Support Vector Classifier (SVC)

---

## Project Workflow

### 1. Data Loading and Inspection

The dataset was loaded using pandas and inspected to understand its structure, data types, statistical characteristics, missing values, and duplicate records.

### 2. Exploratory Data Analysis

The following analysis was performed:

* Dataset structure inspection
* Statistical summary
* Missing-value analysis
* Duplicate-value analysis
* Wine quality distribution
* Distribution plots for chemical features
* Correlation heatmap

### 3. Class Imbalance Analysis

The original quality scores are not evenly distributed.

Most wines have quality scores of 5 and 6, while very low and very high quality scores are less common.

This imbalance can cause a model to favor the majority classes. Therefore, class distribution was considered during model development and evaluation.

### 4. Feature Engineering

The original quality scores were grouped into three categories:

| Quality Score | Category |
| ------------- | -------- |
| 3–4           | Low      |
| 5–6           | Medium   |
| 7–8           | High     |

This grouping reduces the problem caused by very small individual quality classes while maintaining meaningful quality groups.

### 5. Feature and Target Preparation

The original `quality` and newly created `quality_category` columns were excluded from the input features.

```python
X = df.drop(columns=["quality", "quality_category"])
y = df["quality_category"]
```

The physicochemical properties were used as input features, while `quality_category` was used as the target.

### 6. Train-Test Split

The dataset was divided into:

* 80% training data
* 20% testing data

Stratification was applied to preserve the class distribution in both datasets.

### 7. Feature Scaling

StandardScaler was used to standardize the features.

Scaling was especially important for the SGD and SVC models because these algorithms are sensitive to differences in feature scale.

### 8. Model Training

Three classification models were trained:

**Random Forest**

An ensemble model capable of capturing nonlinear relationships between the chemical properties and wine quality.

**SGD Classifier**

A linear classification model trained using stochastic gradient descent.

**SVC**

A Support Vector Classifier using an RBF kernel to capture nonlinear relationships.

### 9. Model Evaluation

The models were evaluated using:

* Accuracy
* Precision
* Recall
* F1-score
* Classification report
* Confusion matrix

Macro F1-score was also considered because the quality categories are imbalanced.

### 10. Feature Importance

Random Forest feature importance was analyzed to identify the physicochemical properties that contributed most to the model's predictions.

---

## Model Comparison

The final model comparison was based on accuracy and F1-score.

| Model          |   Accuracy | Weighted F1 |   Macro F1 |
| -------------- | ---------: | ----------: | ---------: |
| Random Forest  | 83% |  0.83 | 0.67 |
| SGD Classifier | 74% |  0.77 | 0.55 |
| SVC            | 71% |  0.75 | 0.57 |
 

TRandoh Forest me model with the strongest overall and balanced performance was selected as the preferred model.

---

## Key Findings

* Wine quality scores are unevenly distributed.
* Quality scores 5 and 6 represent the majority of the dataset.
* Low- and high-quality wines are less represented.
* The physicochemical features have different distributions and numerical scales.
* Alcohol shows a noticeable relationship with wine quality.
* The three classification models produced different levels of predictive performance.
* Random Forest feature importance helped identify the most influential physicochemical properties.

---

## Conclusion
Exploratory data analysis showed that the wine quality classes are imbalanced, with Medium-quality wines being considerably more common than Low- and High-quality wines. Because of this imbalance, stratified train-test splitting and class balancing techniques were used, and model performance was evaluated using accuracy as well as precision, recall, F1-score, and confusion matrices.

The three models—Random Forest, SGD Classifier, and SVC—showed different levels of predictive performance.

Based on the experimental results, **Random Forest** model achieved the strongest overall performance, with an accuracy of 82.7% a macro F1-score of **0.668034**.

Therefore, **Random Forest Model** is the most suitable model among the three for this project because it provides the best balance between overall predictive accuracy and performance across the different wine quality categories.

The Random Forest feature importance analysis also provided insight into which physicochemical properties were most useful for prediction.

However, the model should be further validated using cross-validation and additional wine samples before being considered forore real-world deployment.

---

## Project Files

```text
DataAnalytics-Level2-Task2-WineQuality/
│
├── winequality-red.csv
├── WineQualityPrediction.ipynb
└── README.md
```




