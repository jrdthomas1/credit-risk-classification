# credit-risk-classification
** Credit Risk Analysis Report

** Purpose of the Analysis

The purpose of this analysis was to build and evaluate a machine learning model capable of predicting the creditworthiness of borrowers using historical lending data. By analyzing key financial indicators, we aimed to classify loans as either healthy (0) or high-risk (1), helping lending institutions make better-informed decisions.

** Data Overview

* The dataset consists of financial information about borrowers, including:
- Loan size
- Interest rate
- Borrower income
- Debt-to-income ratio
- Number of accounts
- Derogatory marks
- Total debt
  
* The target variable, loan_status, is a binary classification:
0 = Healthy Loan (low risk)
1 = High-Risk Loan (likely to default)

To understand the distribution of loan statuses, we examined the class balance:
y.value_counts()

- Class 0 (Healthy Loans): Majority of the dataset
- Class 1 (High-Risk Loans): Minority of the dataset (indicating a class imbalance)

** Machine Learning Process

* Data Preprocessing:
  
- Loaded the dataset into a Pandas DataFrame.
- Separated the features (X) and labels (y).
- Split the data into training (80%) and testing (20%) sets.

* Model Selection & Training:
  
- Used Logistic Regression as the primary model due to its effectiveness in binary classification tasks.
- Trained the model on the training set.

* Model Evaluation:

- Made predictions on the test set.
- Evaluated the model using a confusion matrix and classification report.

** Results

* Machine Learning Model 1: Logistic Regression
- Accuracy: 99%
  
Precision & Recall:

- Class 0 (Healthy Loans):
- Precision: 1.00 (Perfect classification)
- Recall: 1.00 (Almost all healthy loans were correctly identified)
  
- Class 1 (High-Risk Loans):
- Precision: 0.86 (86% of predicted high-risk loans were correct)
- Recall: 0.91 (91% of actual high-risk loans were identified)
  
Confusion Matrix:
 [[14926    75]
 [   46   461]]


- False Positives: 75 (healthy loans incorrectly labeled as high-risk)
- False Negatives: 46 (high-risk loans incorrectly labeled as healthy)

** Summary & Recommendation

- The Logistic Regression model performed well, achieving a 99% accuracy.
- It predicted healthy loans (0) perfectly but had slightly lower precision (86%) for high-risk loans (1).
- While it captures 91% of high-risk loans, it misses 9% (false negatives), which could be problematic if the goal is to avoid risky lending.

** Final Recommendation:
  
- If minimizing false negatives (missed high-risk loans) is critical, we might need to adjust the decision threshold or try more advanced models.
- If maintaining high overall accuracy and correctly classifying healthy loans is more important, Logistic Regression is a great choice.
