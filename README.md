# credit-risk-classification

## Overview of the Analysis

The purpose of this analysis was to review historical lending activity from a peer-to-peer lending services company to build a model that can identify the creditworthiness of borrowers.

Our column headers in the data set were:
loan_size - the amount of the loan being requested
interest_rate - percentage of the interest rate on the loan
borrower_income	- the income of the person borrowing
debt_to_income - this is a percentage of the total debt to the income - higher % means a higher debt ratio 
num_of_accounts	- this is the number of borrowing accounts the borrower has open or active
derogatory_marks - these marks refer to any negative instances such as missed payments 
total_debt	- accumulation of all of the debt across all accounts
loan_status - refers to whether the loan is healthy or at risk of defaulting

The goal with this model was to develop a predictive model that would be able to classify loans into the two loan status categories based on the other features in our dataset- whether a loan is healthy or at risk.

- For y, extracted the loan_status column and reshaped it
- For X, created a copy of the original DataFrame and dropped the loan_status column to have features only
- Split the data into training and testing sets with a random state=1
- Used LogisticRegression from sklearn to instantiate a logistic regression model object using a random state=1
- Made predictions using the testing data 

## Results

Our generated confusion matrix gave us the following information:
- 18663 correctly predicted instances for true negatives
- 102 incorrectly predicted instances for false negatives
- 56 incorrectly predicted instances for false positives
- 563 instances predicted instances for true positives


#### Our classification report gave us the following information:
Precision:
- For our healthy loans, we have a 1.00 precision ratio - which means that all predictions were correctly classified under class '0'. There were no false positives for this class.
- For at-risk loans, we have a 0.85 precision ratio - which means that about 85% of the predictions were correctly classified as class '1'.

Recall:
- For healthy loans, the recall was 0.99 - almost all of the healthy loans were correctly identified as class '0'.
- For at-risk loans, the recall was 0.91 - therefore, 91% of the actual at-risk loans were correctly identified as class '1'.

Accuracy:
- 99% of this model's predictions were correct as we are calculating the total number of instances that were predicted correctly compared to the total number of instances

I would recommend this model for use because it performs very well with identifying the two loan classes. Overall, it helps us to make data-driven decisions when it comes to lending to borrowers.
We have very high accuracy, precision and F1-scores which makes the model very reliable. It definitely needs to be re-evaluated over time to monitor for consistent performance. It is however important to consider the potential risks associated with having false positives and false negatives in the model. 
