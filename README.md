# Bank_Fraud_Detection

## 1.Project Overview

### 1.1 Issues to be addressed in this project
<div align="justify">
 
This project builds a credit card anti-fraud prediction model by utilizing historical credit card transaction data for machine learning to detect incidents of customer credit card theft in advance.

</div>
 
### 1.2 Modeling Ideas
![Building a predictive model for credit card anti-fraud](https://github.com/user-attachments/assets/8125d0e1-fe87-4e0e-a32c-2489aaf5bbc1)

### 1.3 Project background
<div align="justify">
 
The dataset contains transactions made by credit cards in September 2013 by European cardholders.

This dataset presents transactions that occurred in two days, where we have 492 frauds out of 284,807 transactions. The dataset is highly unbalanced, the positive class (frauds) account for 0.172% of all transactions.

It contains only numerical input variables which are the result of a PCA transformation. Unfortunately, due to confidentiality issues, we cannot provide the original features and more background information about the data. Features V1, V2, … V28 are the principal components obtained with PCA, the only features which have not been transformed with PCA are 'Time' and 'Amount'. Feature 'Time' contains the seconds elapsed between each transaction and the first transaction in the dataset. The feature 'Amount' is the transaction Amount, this feature can be used for example-dependent cost-sensitive learning. Feature 'Class' is the response variable and it takes value 1 in case of fraud and 0 otherwise.

</div>

## 2.Scenario Analysis

### 2.1 Algorithm selection
<div align="justify">
 
First of all, the data we got is the credit card transaction data of the cardholder in two days, this data contains many dimensions and the problem to be solved is to predict whether the cardholder will experience credit card theft or not. There are only two possibilities of whether a credit card holder will experience skimming, skimming or no skimming. Because this data is labeled (the field class is the target column), it is a supervised learning scenario. Thus, we decided that whether credit card holders will experience skimming is a binary classification problem, which means that a specific solution can be found through binary classification related algorithms, and the algorithm chosen for this project is Logistic Regression.

</div>

### 2.2 Data analysis
<div align="justify">
 
The data is structured data and does not need to do feature abstraction (it is for ordered and unordered text subtype features that are processed using different methods to numericalize their class attributes). Features V1 to V28 are processed by PCA, while the data specifications of features Time and Amount are quite different from other features, and it is necessary to do feature scaling on them to scale the features to the same specifications. In terms of data quality, no data with garbled or empty characters can be identified as the target column for the field Class, and the other columns are considered as feature columns.

</div>

### 2.3 Model Evaluation
<div align="justify">
 
This data is all labeled data and can be evaluated by Cross-Validation method for the models generated from the training set. 80% of the data is trained and 20% of the data is predicted and evaluated.

</div>
  
## Dataset is from Kaggle
### [https://www.kaggle.com/datasets/anurag629/credit-card-fraud-transaction-data/data](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud/data)

## 3. Conclusion
<div align="justify">

Precision and recall are a contradictory set of variables. From the above confusion matrix and PRC curve, ROC curve can be seen, the smaller the threshold value, the larger the recall value, the model can find out the number of credit card theft is also with the terrier, but the price is the number of miscarriage of justice is also larger, with the increase of the threshold value, the recall value is gradually reduced, the precision value is also gradually increased, the number of miscarriage of justice is also reduced. By adjusting the model threshold, the strength of the model against credit card fraud is controlled, if you want to find out more credit card theft, set a smaller threshold, and vice versa, set a larger threshold.

In actual business, the choice of threshold depends on the comparison of marginal profit and marginal cost of the company's business. When the model threshold is set to a smaller value, it does find out more credit card holders with stolen credit cards, but with the increase in the number of misjudgments, it not only increases the workload of the post-loan team, but also reduces the consumption experience of the customers who are misjudged as stolen credit card holders, which leads to a decrease in customer satisfaction. If a certain model threshold can make the business marginal profit and marginal cost to reach a balance, then the threshold value of the model is the optimal value. Of course there are exceptions, when there is a financial crisis, it is often accompanied by an increased chance of loan default or credit card theft, and financial institutions will be more willing to hold the line on risk at all costs.

</div>
