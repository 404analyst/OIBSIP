 Unveiling the Android App Market — Google Play Store Analysis

### OIBSIP Data Analytics — Level 2 — Task 4

This project explores the Google Play Store ecosystem using real-world app and user-review data. The analysis focuses on data cleaning, category distribution, ratings, installations, app size, pricing, estimated revenue, and review sentiment.

## Objective

The main goals of this project are to:

- Clean and prepare Google Play Store app data
- Explore app categories and market saturation
- Analyse app ratings and installations
- Examine the relationship between app size and installs
- Compare free and paid applications
- Estimate potential revenue for paid apps
- Analyse user review sentiment using TextBlob
- Compare sentiment across app categories
- Create an interactive visualization of ratings and installations

## Datasets

Two datasets are used:

1. **`googleplaystore.csv`**
   - App information
   - Category
   - Rating
   - Reviews
   - Size
   - Installs
   - Type
   - Price
   - Content Rating
   - Genres
   - Last Updated
   - Current Version
   - Android Version

2. **`googleplaystore_user_reviews.csv`**
   - App
   - Translated Review
   - Sentiment
   - Sentiment Polarity
   - Sentiment Subjectivity

Initial dataset sizes:

- Apps dataset: **10,841 rows × 13 columns**
- Reviews dataset: **64,295 rows × 5 columns**

## Tools & Libraries

- Python
- Jupyter Notebook
- pandas
- NumPy
- Matplotlib
- Seaborn
- TextBlob
- Plotly

## Project Workflow

### 1. Data Loading & Inspection

The datasets were loaded with pandas and examined for:

- Dataset shape
- Column structure
- Data types
- Missing values
- Duplicate records

### 2. Data Cleaning

The apps dataset was cleaned by:

- Removing duplicate records
- Removing a malformed category row (`Category = 1.9`)
- Converting ratings to numeric values
- Removing rows with missing ratings
- Converting review counts to numeric values
- Cleaning install counts such as `10,000+`
- Converting app sizes from MB/KB into MB
- Removing `$` from prices and converting prices to numeric values

After cleaning, the apps dataset contained **8,892 records**.

### 3. Category Analysis

The number of apps in each category was analysed to identify highly competitive and less saturated areas of the market.

**Top saturated categories:**

- FAMILY — **1,718 apps**
- GAME — **1,074 apps**
- TOOLS — **734 apps**

### 4. Ratings Analysis

The project examines the overall distribution of app ratings and average ratings by category.

The highest average-rated categories were:

- EVENTS — **4.44**
- EDUCATION — **4.38**
- ART_AND_DESIGN — **4.36**
- BOOKS_AND_REFERENCE — **4.35**
- PERSONALIZATION — **4.33**

### 5. App Size vs. Installs

A scatter plot was used to investigate whether larger apps tend to receive more installations.

The calculated correlation was approximately **0.167**, indicating a **very weak positive relationship** between app size and installs.

This suggests that app size alone is not a strong factor affecting installation numbers.

### 6. Pricing Analysis

The analysis compared free and paid applications.

- Free apps: **8,279**
- Paid apps: **613**

Paid-app prices were found to be highly right-skewed, with most paid apps at relatively low prices and a small number of high-price outliers.

### 7. Estimated Revenue

For paid applications, estimated revenue was calculated as:

**Estimated Revenue = App Price × Number of Installs**

The highest estimated revenue categories were:

- FAMILY — approximately **$185.8 million**
- LIFESTYLE — approximately **$57.6 million**
- GAME — approximately **$41.0 million**
- FINANCE — approximately **$25.7 million**
- PHOTOGRAPHY — approximately **$8.9 million**

> These figures are simplified estimates based on listed price and reported installs. They should not be treated as actual developer earnings.

### 8. Sentiment Analysis

TextBlob was used to calculate review polarity and classify reviews into:

- **Positive** — polarity > 0
- **Neutral** — polarity = 0
- **Negative** — polarity < 0

The resulting sentiment distribution was:

| Sentiment | Reviews | Share |
|---|---:|---:|
| Positive | 23,997 | 64.1% |
| Negative | 8,272 | 22.1% |
| Neutral | 5,158 | 13.8% |

Overall, positive reviews were the largest group, while negative reviews still represented a significant amount of user feedback.

### 9. Sentiment by Category

The review data was merged with the cleaned app data using the `App` column so that sentiment could be analysed by category.

Categories with high positive sentiment rates included:

- COMICS — **90.0%**
- AUTO_AND_VEHICLES — **81.66%**
- EVENTS — **79.11%**
- EDUCATION — **78.30%**
- HEALTH_AND_FITNESS — **76.26%**

The GAME category had the highest absolute number of negative reviews, with **6,542**, followed by FAMILY with **1,452**.

Absolute review counts should be considered together with total review volume when comparing categories.

### 10. Interactive Visualization

A Plotly scatter plot was created to interactively explore:

- App ratings
- Installation counts
- App categories
- Review counts
- App type
- Price

The installation axis uses a logarithmic scale to make differences in installation volume easier to explore.

## Key Insights

### Market Competition
FAMILY, GAME, and TOOLS are highly saturated categories. New apps entering these areas may need clear differentiation and a well-defined target audience.

### User Satisfaction
EVENTS, EDUCATION, and ART_AND_DESIGN have some of the highest average ratings. COMICS and AUTO_AND_VEHICLES also show strong positive sentiment rates.

### Revenue Potential
FAMILY, LIFESTYLE, and GAME have the highest estimated revenue in the analysed paid-app data. However, free applications greatly outnumber paid applications.

### App Size
The weak correlation between app size and installs suggests that download performance depends on factors beyond application size.

### User Feedback
Positive sentiment dominates the analysed reviews, but negative reviews provide useful signals about areas where app developers may improve user experience.

## Conclusion

The analysis shows that choosing an app category requires balancing **competition, user satisfaction, demand, and monetization potential**.

A highly saturated category may offer strong demand but also intense competition. At the same time, categories with high ratings or positive sentiment may indicate strong user satisfaction and expectations.

For a new developer, the most practical approach is to identify user needs and gaps through market data and reviews, then build a high-quality, user-focused app with a suitable monetization strategy.

## Files

```text
Google-Play-Store-Analysis/
│
├── googleplaystore.ipynb
├── googleplaystore.csv
├── googleplaystore_user_reviews.csv
└── README.md
```

## How to Run

1. Clone or download this project.
2. Place both CSV datasets in the same folder as the notebook.
3. Open `googleplaystore.ipynb` in Jupyter Notebook or VS Code.
4. Install the required libraries if necessary:

```bash
pip install pandas numpy matplotlib seaborn textblob plotly
```

5. Run the notebook cells from top to bottom.