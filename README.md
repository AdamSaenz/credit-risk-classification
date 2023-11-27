# credit-risk-classification

# Overview

The purpose is to analyze a dataset of lending activity from a peer based lending service company that helps to build a model that can identify the creditworthiness of borrowers. The dataset reflected the size of the loan, the interest rate, the income of the borrower, the debt-to-income ratio, the total number of accounts, the negative marks and the total debt of each loan application.

Within the dataset there is a discrepancy between the healthy loans (0) counts and the high-risk loans (1) counts: 75036 healthy loans count vs 2500 high-risk count. To process this analysis, several stages of the machine learning were made, including pre-processing, training and validating and evaluating the model.

I utilized the supervised learning classification model called Logistic Regression to predict the probability of the healthy loans against the high-risk loans. I then utilized the resampling method to generate more data points that could balance the dataset and make a more accurate model.

# Results

Machine Learning Model 1:

Accuracy - how often the model is correct: 95%

Precision - the ratio of the correctly predicted true positives to the total predicted positive observations: the model performs better predicting healthy loans (99%) than high-risk loans (precision 91%).

Recall - the ratio of actual positives identified correctly: the model performs better predicting healthy loans (99%) than high-risk loans (91%).

Support - the number of actual occurrences of the class in the specified dataset: according to the support column, the model is imbalanced in the training data (healthy loans 18759 vs high-risk loans 625), indicating structural weaknesses in the reported scores, in the evaluation process.

Machine Learning Model 2:

Accuracy - how often the model is correct: 99%

Precision - the ratio of the correctly predicted true positives to the total predicted positive observations: the model performs equally well for predicting healthy loans (99%) and high-risk loans (99%).

Recall - the ratio of actual positives identified correctly: the model performs equally well for predicting healthy loans (99%) and high-risk loans (99%).

Support - the number of actual occurrences of the class in the specified dataset: according to the support column, the model is balanced in the training data (healthy loans 56277 vs high-risk loans 56277), indicating structural strength in the reported scores, in the evaluation process.

# Summary

Overall the accuracy within the logistic regression model is high, at 95%. But when it comes to the recall, it is doing it better for the healthy loans which is 99%, but unhealthy loans are 91%. So, that is where the model is not doing as good. The healhty loan applicants will be able to pay back their loans. The issues lies in the risky loans, where we want to make sure that we don't approve those loans by mistake and we lose money for the bank.

With the oversample data, it is doing a better job since the accuracy has increased from 95% to 99%. False negatives have reduced significantly and the recall hasn't changed at all. Recall for high risk applicants has increased from 91% to 99% and we are seeing a high degree of accuracy after we oversample the data.
