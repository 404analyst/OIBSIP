#  OIBSIP Level 2   — Task 5: Autocomplete and Autocorrect Data Analytics

## Project Overview

This project analyses the performance of **autocomplete and autocorrect algorithms using Natural Language Processing (NLP)** techniques.

The project uses *Alice's Adventures in Wonderland* by Lewis Carroll from Project Gutenberg as the text corpus. The text was preprocessed and used to build frequency-based n-gram models for autocomplete and edit-distance-based methods for autocorrect.

## Objective

* Preprocess a real-world text corpus using NLP techniques.
* Analyse word frequencies and common language patterns.
* Build a frequency-based Bigram autocomplete model.
* Build a Trigram autocomplete model for comparison.
* Test autocomplete using multiple input prefixes.
* Implement autocorrect using Custom Levenshtein distance.
* Implement autocorrect using PySpellChecker.
* Compare the performance of different approaches.
* Calculate accuracy, precision, and recall.
* Visualise word frequencies and autocorrect results.
* Discuss the limitations of simple NLP models compared with modern production systems.

## Dataset

**Dataset:** *Alice's Adventures in Wonderland*
**Author:** Lewis Carroll
**Source:** Project Gutenberg
**Book ID:** 11

Dataset link: https://www.gutenberg.org/ebooks/11

The original corpus contained:

| Metric                          |   Value |
| ------------------------------- | ------: |
| Total Characters                | 163,950 |
| Words Before Preprocessing      |  29,569 |
| Tokens After Tokenisation       |  38,626 |
| Words After Punctuation Removal |  29,822 |
| Words After Stopword Removal    |  13,568 |
| Unique Vocabulary Words         |   2,922 |

## Technologies Used

* Python
* Pandas
* NLTK
* PySpellChecker
* Scikit-learn
* Matplotlib
* Collections
* Jupyter Notebook

## NLP Preprocessing

The following preprocessing steps were applied:

1. Lowercasing
2. Tokenisation
3. Punctuation removal
4. Removal of non-alphabetic tokens
5. Stopword removal

After preprocessing, **13,568 meaningful words** remained for analysis.

## Autocomplete

### Bigram Model

The Bigram model predicts the next word using the previous word as context.

Example predictions included:

* `alice` → and, was, i
* `the` → queen, king, mock
* `a` → little, very, large
* `she` → had, was, said
* `said` → the, alice, to

The model contained **2,922 unique first-word contexts**.

### Trigram Model

The Trigram model uses two previous words to predict the next word. It provided **15,919 unique two-word contexts**, giving the model more contextual information than the Bigram approach.

### Autocomplete Performance

| Model   |  Precision |     Recall |
| ------- | ---------: | ---------: |
| Bigram  |     21.56% |     21.56% |
| Trigram | **22.66%** | **22.66%** |

The Trigram model slightly outperformed the Bigram model, showing that additional context can improve next-word prediction.

## Autocorrect

Two approaches were implemented and tested using **20 deliberately misspelled words**.

### 1. Custom Levenshtein Distance

The custom method calculates the minimum number of edits required to transform a misspelled word into a vocabulary word.

**Result:**

* Accuracy: **60%**
* Precision: **100%**
* Recall: **60%**
* Correct corrections: **12 out of 20**

### 2. PySpellChecker

PySpellChecker was used as a second approach for spelling correction.

**Result:**

* Accuracy: **80%**
* Precision: **100%**
* Recall: **80%**
* Correct corrections: **16 out of 20**

### Autocorrect Comparison

| Algorithm          | Accuracy | Precision |  Recall |
| ------------------ | -------: | --------: | ------: |
| Custom Levenshtein |      60% |      100% |     60% |
| PySpellChecker     |  **80%** |  **100%** | **80%** |

PySpellChecker performed better by correctly correcting **16 of the 20 tested spelling errors**, compared with 12 for the custom Levenshtein approach.

## Visualisations

The project includes:

* Bar chart of the **Top 20 most frequent words**
* Autocomplete performance comparison
* Autocorrect accuracy comparison
* PySpellChecker confusion matrix
* Custom Levenshtein confusion matrix

The most frequent meaningful words included **"said" (460 occurrences)** and **"alice" (402 occurrences)**.

## Confusion Matrix

The confusion matrices were used to compare successful and unsuccessful spelling corrections.

PySpellChecker produced:

* 16 correct corrections
* 4 incorrect corrections

Custom Levenshtein produced:

* 12 correct corrections
* 8 incorrect corrections

The test set contained only words that were expected to be corrected. Therefore, there were no true-negative or false-positive cases, meaning the confusion matrices mainly show successful versus unsuccessful corrections rather than a complete binary classification evaluation.

## Final Findings

The main findings of the project are:

* The **Trigram model performed slightly better than the Bigram model** for autocomplete.
* The Trigram model achieved **22.66% precision and recall**, compared with **21.56%** for Bigram.
* **PySpellChecker outperformed the Custom Levenshtein method** for autocorrect.
* PySpellChecker achieved **80% accuracy and recall**, compared with **60%** for the custom method.
* Both autocorrect approaches achieved **100% precision** on the selected test dataset.
* Additional context and word-frequency information can improve NLP-based text prediction and spelling correction.

## Limitations

The implemented models are simplified compared with modern production systems such as Google Keyboard.

Main limitations include:

* The corpus is based on a single book.
* The dataset is relatively small compared with modern language-model training data.
* Bigram and Trigram models use limited context.
* The models do not understand the meaning of sentences.
* Unseen word combinations can result in poor predictions.
* The custom Levenshtein method depends heavily on the available vocabulary.
* The autocorrect test contains only 20 deliberately selected spelling errors.
* Keyboard layout, user behaviour, personal vocabulary, and sentence-level context are not considered.

Modern autocomplete and autocorrect systems use much larger datasets, contextual language models, neural networks, and personalised user information to provide more accurate results.

## Conclusion

This project demonstrates how basic NLP techniques can be used to build and evaluate autocomplete and autocorrect systems. The **Trigram model achieved better autocomplete performance**, while **PySpellChecker achieved better autocorrect performance**.

Although the results are useful for demonstrating fundamental NLP concepts, more advanced models and larger datasets would be required to achieve the accuracy and contextual understanding of modern production systems.

## Project Structure

```text
DataAnalytics-L2-Autocomplete_AutocorrectDataAnalytics/
│
├── alice.txt
├── Autocomplete_Autocorrect.ipynb
└── README.md
```

