# OIBSIP Level 1   — Task 4: Sentiment Analysis

## Objective
Build a machine-learning model that classifies Twitter text into **Positive, Negative, or Neutral** sentiment.

## Dataset
This project uses Kaggle's **Twitter and Reddit Sentimental Analysis Dataset**, specifically:

```text
Twitter_Data.csv
```

The Twitter dataset contains approximately 163K tweets. Its relevant columns are:

- `clean_text` — cleaned tweet text
- `category` — sentiment label:
  - `-1` = Negative
  - `0` = Neutral
  - `1` = Positive

Source:
https://www.kaggle.com/datasets/cosmos98/twitter-and-reddit-sentimental-analysis-dataset

## Tech Stack
- Python
- pandas
- NumPy
- scikit-learn
- NLTK
- matplotlib
- seaborn
- WordCloud
- Jupyter Notebook

## Project Workflow
1. Load `Twitter_Data.csv`
2. Inspect dataset shape, columns, missing values and duplicates
3. Convert numeric sentiment labels to Positive/Negative/Neutral
4. Plot sentiment distribution
5. Preprocess text
6. Split data 80/20 using stratification
7. Extract TF-IDF features
8. Train Multinomial Naive Bayes
9. Train Logistic Regression
10. Compare accuracy, precision, recall and F1-score
11. Generate confusion matrices
12. Generate Positive, Negative and Neutral WordClouds
13. Display five misclassified examples
14. Discuss common classification errors
15. Select the best model using weighted F1-score
16. Explain real-world applications

## Text Preprocessing
The notebook performs:
- Lowercasing
- URL removal
- User-mention removal
- Hashtag symbol removal
- Punctuation removal
- Number removal
- NLTK tokenisation
- Stopword removal

Negation words such as `not`, `no`, and `never` are retained because they can change sentiment meaning.

## TF-IDF
TF-IDF (Term Frequency–Inverse Document Frequency) converts text into numerical features. It gives more importance to informative terms and reduces the influence of words that occur very frequently throughout the corpus.

The notebook uses:
- Unigrams
- Bigrams
- `min_df=2`
- `max_df=0.95`
- Maximum 30,000 features

## Models

### Multinomial Naive Bayes
A fast probabilistic classifier commonly used as a baseline for text classification.

### Logistic Regression
A strong linear classifier for sparse TF-IDF features.

Both models are trained using exactly the same train/test split and TF-IDF features.

## Evaluation
Each model is evaluated using:
- Accuracy
- Weighted Precision
- Weighted Recall
- Weighted F1-score
- Confusion Matrix

The model with the highest weighted F1-score is selected as the best model.

## Visualisations
The notebook contains:
- Sentiment distribution bar chart
- Naive Bayes confusion matrix
- Logistic Regression confusion matrix
- Positive WordCloud
- Negative WordCloud
- Neutral WordCloud

## Error Analysis
Five incorrectly classified examples are displayed. The notebook discusses:
- Sarcasm
- Mixed sentiment
- Context dependence
- Short/factual statements
- Slang and social-media language

## Real-World Applications
Possible applications include:
- Customer feedback monitoring
- Social-media opinion tracking
- Brand reputation analysis
- Product/service review analysis
- Complaint and satisfaction monitoring

## Project Structure

```text
OIBSIP/
└── DataAnalytics-Level2-Task4-SentimentAnalysis/
    ├── data/
    │   └── Twitter_Data.csv
    ├── sentiment_analysis_Twitter_Data.ipynb
    └── README.md
```


## References
- Kaggle: https://www.kaggle.com/datasets/cosmos98/twitter-and-reddit-sentimental-analysis-dataset
- scikit-learn: https://scikit-learn.org/stable/modules/feature_extraction.html
- NLTK: https://www.nltk.org/
- TextBlob: https://textblob.readthedocs.io/
