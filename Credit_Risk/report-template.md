# Credit Risk Classification Report

## Overview of the Analysis

The analysis consisted on generating supervised machine learning models to predict high-risk loans, based on a provided dataset of financial information that included loan size, interest rate, borrower income, dept-to-income, number of acounts, derogatory marks and total debt. The variable we were trying to predict was whether the loan was healthy or high-risk. The data contained 75036 cases of healthy loans and 2500 high-risk loans. 

The machine learning process included splitting the data in training and testing sets, generating and fitting a logistic regression model using the training data, using the testing data to generate predictions and evaluating the model by examining its accuracy, as well as the precision and recall for each of the target labels. 

Due to the unbalanced nature of the data (i.e. a lot more cases of helathy loans vs high-risk loans), I generated two models. The first using the regular data and a second one using a random oversampling model to resample the training data and balance the target labels.


## Results

* Machine Learning Model 1:

  * Balanced accuracy score: 94.4%

    * Predicting Healthy loans:

      * Precision: 100% (Out of 18746 predicted, 18679 were really healthy loans)

      * Recall: 100% (Out of 18759 healthy loans in the data, 18679 were correctly identified)

    * Predicting High-risk loans:

      * Precision: 87% (Out of 638 predicted, 558 were really high-risk loans)

      * Recall: 89% (Out of 625 high-risk loans in the data, 558 were correcly identified)

* Machine Learning Model 2:

  * Balanced accuracy score: 99.6%

    * Predicting Healthy loans:

      * Precision: 100% (Out of 18670 predicted, 18668 were really healthy loans)

      * Recall: 100% (Out of 18759 healthy loans in the data, 18668 were correctly identified)

    * Predicting High-risk loans:

      * Precision: 87% (Out of 714 predicted, 623 were really high-risk loans)

      * Recall: 100% (Out of 625 high-risk loans in the data, 623 were correcly identified)

## Summary

Both models are good at predicting healthy loans. Although the second one missed slightly more of them and incorrectly classified them as high-risk, they both have the same rounded precision (100%) and recall (100%) for healthy loans. The second model, which was fitted with resampled data to account fot the imbalanced target categories, was better at predicting high-risk loans. It only mislabeled 2 as healthy, resulting in a recall of 100%, compared to 89% for the first model, which only found 558 cases out of 625. They both have similar precision 87%, which means that there is a number of actually healthy loans being mislabeled as high-risk. These differences result in the second model having a higher balanced accuracy score (99.6% vs 94.4%). Therefore, if the use-case is to identify high-risk loans, I would recommend the second model. It is a good first model for narrowing down the data, but I would add a note of needing to put other measures in place if we want to be sure that all the ones identified as "high-risk" are really high-risk and not mislabeled as such.
