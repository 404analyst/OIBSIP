# OIBSIP Level 2 Task 1 – House Price Prediction

## Project Overview

This project is part of the **Oasis Infobyte Data Analytics Internship – Level 2, Task 1**.

The objective of this project is to build a machine learning model that predicts house prices based on important property characteristics such as overall quality, living area, basement area, garage capacity, number of bathrooms, year built, and neighborhood.

A **Linear Regression** model is developed and evaluated using the `HousePrices.csv` dataset. A **Ridge Regression** model is also implemented as a bonus comparison.

---

## Objective

The main objectives of this project are to:

- Perform Exploratory Data Analysis (EDA)
- Inspect and clean the housing dataset
- Analyze the distribution of house prices
- Select relevant features for prediction
- Analyze correlations between numerical features and house prices
- Handle missing values
- Encode categorical variables using One-Hot Encoding
- Split the dataset into training and testing sets
- Build a Linear Regression model
- Evaluate the model using MSE, RMSE, and R²
- Compare actual and predicted house prices
- Perform residual analysis
- Interpret model coefficients
- Compare Linear Regression with Ridge Regression

---

## Dataset

The project uses the **HousePrices.csv** dataset.

### Dataset Size

- **Rows:** 2,930
- **Columns:** 82
- **Target Variable:** `SalePrice`

The dataset contains information about residential properties, including:

- Overall quality
- Living area
- Basement area
- First-floor area
- Garage capacity
- Number of bathrooms
- Year built
- Neighborhood
- Sale price

---

## Selected Features

The following features were selected for the prediction model:

| Feature | Description |
|---|---|
| `Overall Qual` | Overall quality of the house |
| `Gr Liv Area` | Above-ground living area |
| `Total Bsmt SF` | Total basement area |
| `1st Flr SF` | First-floor area |
| `Garage Cars` | Garage capacity |
| `Full Bath` | Number of full bathrooms |
| `Year Built` | Year the house was built |
| `Neighborhood` | Location/neighborhood of the property |

### Target

`SalePrice`

---

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

---

## Project Workflow

### 1. Data Loading

The dataset is loaded using Pandas and its structure, dimensions, and column names are examined.

### 2. Exploratory Data Analysis

EDA includes:

- Dataset inspection
- Descriptive statistics
- Missing-value analysis
- Target variable analysis
- House price distribution

The house price distribution was found to be **right-skewed**, with most properties concentrated in the lower-to-middle price range and a smaller number of high-priced properties.

### 3. Feature Selection

Features were selected based on their expected relationship with house prices and their relevance to real estate valuation.

### 4. Correlation Analysis

Correlation analysis was performed to identify numerical variables strongly associated with `SalePrice`.

The strongest numerical relationships with `SalePrice` were approximately:

| Feature | Correlation |
|---|---:|
| `Overall Qual` | 0.799 |
| `Gr Liv Area` | 0.707 |
| `Garage Cars` | 0.648 |
| `Total Bsmt SF` | 0.632 |
| `1st Flr SF` | 0.622 |
| `Year Built` | 0.558 |
| `Full Bath` | 0.546 |

`Overall Qual` had the strongest correlation with house price among the selected numerical variables.

### 5. Data Preprocessing

Missing values were handled using:

- **Median imputation** for numerical features
- **Most-frequent imputation** for categorical features

The `Neighborhood` feature was converted into numerical variables using **One-Hot Encoding**.

### 6. Train-Test Split

The dataset was divided using an **80/20 split**:

- Training data: 80%
- Testing data: 20%

A `random_state` of 42 was used for reproducibility.

### 7. Linear Regression

A Linear Regression model was trained using the selected features.

### 8. Model Evaluation

The model was evaluated using:

- Mean Squared Error (MSE)
- Root Mean Squared Error (RMSE)
- R² Score

### 9. Actual vs Predicted Prices

A scatter plot was created to compare actual house prices with predicted prices.

The predictions generally followed the diagonal reference line, indicating that the model captured the overall relationship between property characteristics and sale prices.

### 10. Residual Analysis

A residual plot was used to examine prediction errors.

The residuals were generally distributed around zero, although some larger errors were observed, particularly for certain higher-priced properties.

### 11. Coefficient Analysis

Model coefficients were examined to understand the estimated impact of different features on house prices.

The analysis showed that **property quality and neighborhood/location** were important factors in the model.

---

## Model Performance

### Linear Regression

| Metric | Result |
|---|---:|
| MSE | ≈ 1,303,903,734 |
| RMSE | ≈ 36,110 |
| R² Score | **≈ 0.837** |

The Linear Regression model achieved an R² score of approximately **0.84**, meaning that the selected features explain around **84% of the variation in house prices** on the test dataset.

---

## Bonus: Ridge Regression

Ridge Regression was implemented as a regularized alternative to Linear Regression.

### Comparison

| Model | MSE | RMSE | R² |
|---|---:|---:|---:|
| Linear Regression | ≈ 1.304B | ≈ 36,110 | **≈ 0.837** |
| Ridge Regression | ≈ 1.572B | ≈ 39,653 | ≈ 0.804 |

For the current feature set and configuration, **Linear Regression performed better than Ridge Regression** on the test data.

---

## Key Findings

- `Overall Qual` was the strongest numerical predictor among the selected features.
- Larger living areas were generally associated with higher house prices.
- Garage capacity, basement area, first-floor area, and number of bathrooms also showed positive relationships with price.
- Neighborhood/location had an important influence on predicted house prices.
- House prices were positively skewed, with a small number of high-priced properties.
- Linear Regression achieved an R² of approximately **0.84**.
- Ridge Regression did not outperform Linear Regression with the selected features and `alpha=1.0`.

---

## Project Structure

DataAnalytics-L2-PredictingHousePricing/
│
├── HousePrices.csv
├── HousePricePrediction.ipynb
└── README.md