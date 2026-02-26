# LAB3-emailsEDA
Exploratory Data Analysis (EDA) performed on a dataset of emails to understand its structure and prepare for building a spam classification model.

**Dataset**
The dataset (emails.csv) contains 5,172 emails, each represented by the frequency of 3000 different words or characters. The goal is to predict whether an email is spam (1) or ham (0).

**Objectives**
**This project applies basic Exploratory Data Analysis (EDA) techniques to:**

-Data structure examination

-Handling missing values

-Removing duplicates

-Data visualization

-Correlation analysis

-Feature engineering (preparation for modeling)

-Extracting insights

**Files Included**

EMAILS-1.ipynb → Jupyter Notebook containing the full EDA process

emails.csv → Dataset used for analysis

**Key Findings**

-Data Structure and Quality: The dataset is a well-structured, numeric matrix with 5,172 rows and 3,002 columns. The first column, Email No., is an identifier, and the last column, Prediction, is the binary target variable (0 = Ham, 1 = Spam). An initial check confirmed no missing values and no duplicate rows, indicating a clean dataset ready for analysis.

-Target Variable Distribution: The analysis reveals a significant class imbalance. Ham emails make up the majority (71%, 3672 emails), while spam emails constitute only 29% (1500 emails). This imbalance is a critical consideration for future model training to avoid a model that is biased towards predicting "ham".

-Nature of Features: A key insight from the word frequency analysis is that the top 20 most frequent "words" across all emails are actually single letters (e.g., 'e', 't', 'a') and common bigrams (e.g., 'th'). This strongly suggests the dataset has already undergone text pre-processing (like tokenization and vectorization) where individual characters were treated as features. The high average word count per email (1165) also supports this.

-Word Correlation with Spam: A correlation analysis identified words with the strongest (anti-)correlation with the target variable. Notably, the word 'hpl' (a computer brand) shows the strongest negative correlation with spam, meaning its presence is a strong indicator of a legitimate (ham) email. Conversely, words like 'more' and 'our' show a positive correlation, suggesting they are more common in spam messages. This provides immediate, actionable insights into the language distinguishing the two classes.

-Data Preparation: The final steps successfully separated the features (X) from the target (y) and performed a stratified train-test split (80/20). This ensures the model will be evaluated on unseen data while maintaining the same proportion of spam/ham in both training and testing sets, which is crucial given the class imbalance.

**Conclusion**

This EDA successfully uncovered the underlying structure of the dataset, revealing it to be a clean, pre-processed, and imbalanced text dataset. The analysis highlighted that the predictive features are individual characters and bigrams, and identified specific words most indicative of both spam and ham emails. The insights gained and the prepared train/test split provide a robust foundation for the subsequent development and evaluation of a machine learning model for spam classification. This analysis demonstrates a practical and thorough application of EDA techniques.
