# **Credit Risk Classification Challenge**

## Overview of the Analysis

In this section, describe the analysis you completed for the machine learning models used in this Challenge. This might include:

In this challenge, the primary purpose is to build a model that can identify the creditworthiness of borrowers. The dataset used pertains to historical lending activity from a peer-to-peer lending services company. 

With a shape of **(77536, 8)** , the dataset consists of **77536 samples** with **8 variabes**. The dependent target variable **loan_status** is our **target variable**, taking values of **0(healthy loan)** & **1(high_risk loan)**. And, the independent variables impacting our target variable includes loan_size, interest_rate, borrower_income, debt_to_income, num_of_accounts, derogatory_marks and total_debt. The very binary nature of the target variable is a pointer to use **Logistic Regeression** to build our machine learning model.

As part of the machine learning process, the first step was to understand the data structure i.e the type of data, presence of any null values and value counts. This initial exploratory analysis pointed out an interesting information on the sample size in terms of our target variable i.e the imbalance in terms of the value counts. **Only 6.7% of the total samples belongs to the high-risk loan category**.

Next, the dataset is split into training and testing datasets. This os done to train the model and later test it on unseen data points to reduce the risk of overfitting. And, StandardScaler module is used to standardize the data points in training dataset. This helps in avoiding assiginig higher weight to features with higher absolute values, for example loan_size as against interest_rate.

Finally, after creating instance of the Logistic Regression model, the model is trained on the scaled training dataset and using the actual and predicted values of testing dataset, the model perormance is analysed using a confussion matrix and balanced accuracy scores. 

Further, to reifne the model for better predictions, RadomOverSampling module is used balance the data points for the train data and a new model is trained by fitting the datapoints thus generated.  

## Results

Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model 1:
  * Balanced accuracy score: 98.80%
  * Healty Loans ('0')
      * Precision: 1.00
      * Recall: 1.00
  * High Risk Loans('1')
      * Precision: 0.87
      * Recall: 0.98 

* Machine Learning Model 2:
    * Balanced accuracy score: 99.60%
    * Healty Loans ('0')
      * Precision: 1.00
      * Recall: 0.99
    * High Risk Loans('1')
      * Precision: 0.87
      * Recall: 1.00

## Summary

The first model, wherein the imbalanced datasets in terms of healty and high_risk loans is used as is, the model predicts healthy loans perfectly with precision and recall score of 1.00. However, when it comes to predicting high-risk loans, the model's performance is a touch low. One explanation for this performance could be attributed to the data samples with very high percentage of healthy loan smaples compared to the high-risk ones. 

To address the imbalance, to reifne the model for better predictions, RadomOverSampling module is used balance the data points for the train data and the new model is created by fitting the datapoints generated. On prediction and evaluation, the second model predicts with perfect accuracy. In case of  healthy loans perfectly with precision and recall score of 1.00. And in case of high-risk loans, the model's performance is a perfect 1.00 on recall with similar precision score as with the regular model.

Overall, random over sampling improved the predictability of the Logistic Regression model for the given dataset in terms of better recall for the high risk loans without compromising on its ability to predict healthy loans.Hence, the recommended model. 

However, more often than not, the model's performance is not absolute but relative to the problem the model is trying to solve, in this case, the classification problem of healthy vs high_risk loans. To a large extent, the risk framework of the company (and the individual in peer-to-peer lending) whether risk-averse or reward-seeking is helpful in understanding the importance assigned to prediction accuracy of the two categories, thus aiding in evaluating the models.
