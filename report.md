# Module 12 Report Template

## Overview of the Analysis

In this section, describe the analysis you completed for the machine learning models used in this Challenge. This might include:

* Explain the purpose of the analysis.
* Explain what financial information the data was on, and what you needed to predict.
* Provide basic information about the variables you were trying to predict (e.g., `value_counts`).
* Describe the stages of the machine learning process you went through as part of this analysis.
* Briefly touch on any methods you used (e.g., `LogisticRegression`, or any resampling method).

The purpose of this analysis is to build a prediction model to identify credit worthiness of borrowers using a dataset of historical lending activity from a peer-to-peer lending services company. The dataset has 77536 records.

The dataset is characterized by: loan size, interest rate of the loan, borrower income, debt to income ratio,  number of accounts borrower has, number of dereogatory remarks on the borrower's credit report, total debt amount, and loan status. 

The values in the loan status column are either `0` for current loans and `1` for defaulted loans. 2500 of the 77536 records have defaulted loans.

The data was split to separate the loan_status column from the data. Using the train_test_split function, the data was split into training and testing datasets. The training data was then fit to a logisitic regression model which produced a model performance of 95.2% balance_accuracy_score. 

The training data was resampled using the RandomOverSampler module to better test the model predictions. A new logistic regression model was fit using the resampled data. 

## Results

Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model 1:
  * Description of Model 1 Accuracy, Precision, and Recall scores.
  
  * Balanced accuracy score: 0.9520479254722232
  * F1-score accuracy: 0.99
  * Precision:
      * Current loans: 1.00
      * Defaulted loans: 0.85
  * Recall:
      * Current loans: 0.99
      * Defaulted loans: 0.91
     



* Machine Learning Model 2:
  * Description of Model 2 Accuracy, Precision, and Recall scores.
  
  * RandomOverSampler balanced accuracy score: 0.9936781215845847
  * F1-score accuracy: 0.99
  * Precision:
      * Current loans: 1.00
      * Defaulted loans: 0.84
  * Recall:
      * Current loans: 0.99
      * Defaulted loans: 0.99
     

## Summary

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:
* Which one seems to perform best? How do you know it performs best?
* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )

If you do not recommend any of the models, please justify your reasoning.

The results of the machine learning models used both produced high balanced accuracy scores of 95.2% and 99.4%. It is more important to predict the `1`'s than the `0`'s as the `1`'s are the ones at risk for defaulting on a loan. Due to the Logistic Regression using Random Oversampling confusion matrix producing a larger amount of false negatives (125 vs 113), I would suggest using the Logistic Regression with the training data.