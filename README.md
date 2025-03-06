# Fraud Detection in Python

## Project Overview
Financial transaction integrity is a critical concern for financial institutions and credit card companies. The ability to classify the legitimacy of a transaction helps protect clients, offering peace of mind while reducing financial losses. In 2016, according to CNBC, consumers lost more than $16 billion due to fraudulent transactions.

## Project Goals
Can historical transaction data be used to predict whether a transaction is fraudulent or legitimate?

## Data Overview
The dataset used for this project is sourced from Kaggle and consists of 594,643 rows of transaction data:
- 587,443 normal payments
- 7,200 fraudulent transactions
- 10 features

The data is synthetically generated using BankSim transaction simulation software.

## Data Manipulation
- Removed extraneous apostrophes from all string columns.
- Converted columns to their appropriate data types: categorical for most features, except the amount spent.
- Removed ZIP code columns (both customer and merchant), as they contained only one unique value.
- Used `pandas.get_dummies` to convert categorical columns into binary columns.

## Model Results

| Model                | Precision     | Recall   | FP    | FN    |
| :------------------: |:------------: | :------: | :--:  | :--:  |
| Naive Bayes          | 0.1957        | 0.9993   | 2     | 11695 |
| Logistic Regression  | 0.8887        | 0.7236   | 796   | 261   |
| Neural Network       | 0.8721        | 0.7624   | 684   | 322   |
| Decision Tree        | 0.9027        | 0.7212   | 803   | 224   |
| Random Forest        | 0.8845        | 0.7462   | 1096  | 421   |

## Analysis
- **Naive Bayes** has the highest recall and lowest FP rate but also the lowest precision and highest FN rate. Although the FN rate is high, in practice, flagged transactions can be reviewed and resolved, making low FP more desirable.
- **Neural Network** has high precision and recall with the second-lowest FP score, making it one of the most effective models for fraud detection.

## Conclusion
Based on the results, the most effective models for fraud detection are the **Naive Bayes** (for its low FP rate) and the **Neural Network** (for its balanced precision and recall). These models can help improve fraud detection accuracy and minimize financial losses for consumers and institutions alike.

