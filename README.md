# card-credit-default-predection

## Problem Discription 
This project is aimed at predicting the case of customers default payments in Taiwan. From the perspective of risk management, the result of predictive accuracy of the estimated probability of default will be more valuable than the binary result of classification - credible or not credible clients. We can use the K-S chart to evaluate which customers will default on their credit card payments.


## Business Objective
* Objective of our project is to predict which customer might default in upcoming months. Before going any further let's have a quick look on defination of what actually meant by Credit Card Default.

* We are all aware what is credit card. It is type of payment payment card in which charges are made against a line of credit instead of the account holder's cash deposits. When someone uses a credit card to make a purchase, that person's account accrues a balance that must be paid off each month.

* Credit card default happens when you have become severely delinquent on your credit card payments.Missing credit card payments once or twice does not count as a default. A payment default occurs when you fail to pay the Minimum Amount Due on the credit card for a few consecutive months.

* So now we know what a credit card is. Now let's see one of problems faced by companies who provide credit cards. Yes it is the peolpe who do not clear off the credit card debt aka credit card defaulters.

* The research aims at developing a mechanism to predict the credit card default beforehand and to identify the potential customer base that can be offered various credit instruments so as to invite minimum default.

## Data Description
Attribute Information:
This research employed a binary variable, default payment (Yes = 1, No = 0), as the response variable. This study reviewed the literature and used the following 23 variables as explanatory variables:
* X1: Amount of the given credit (NT dollar): it includes both the individual consumer credit and his/her family (supplementary) credit.
* X2: Gender (1 = male; 2 = female).
* X3: Education (1 = graduate school; 2 = university; 3 = high school; 4 = others).
* X4: Marital status (1 = married; 2 = single; 3 = others).
* X5: Age (year).
* X6 - X11: History of past payment. We tracked the past monthly payment records (from April to September, 2005) as follows: X6 = the repayment status in September, * * 2005; X7 = the repayment status in August, 2005; . . .;X11 = the repayment status in April, 2005. The measurement scale for the repayment status is: -1 = pay duly; 1 = payment delay for one month; 2 = payment delay for two months; . . .; 8 = payment delay for eight months; 9 = payment delay for nine months and above.
* X12-X17: Amount of bill statement (NT dollar). X12 = amount of bill statement in September, 2005; X13 = amount of bill statement in August, 2005; . . .; X17 = amount of bill statement in April, 2005.

## Steps Involved :

The following steps are involved in the project

Exploratory Data Analysis :

After loading and reading the dataset in a notebook, we performed exploratory data analysis. The purpose of exploratory data analysis is to identify the variables that impact payment default next month and the correlations between them. We use graphical data exploratory analysis to check every categorical variable. We plot the graph and visualize the data.

Null values Treatment and Outliers:

Dataset contains no null values to disturb the accuracy.

Numerical and categorical Features:

With the help of exploratory data analysis we analyzed the categorical as well as numerical features in the dataset.

Correlation Analysis :

We plot the heatmap to find the correlation between both the dependent variable and independent variables.

Train test Split :

In the train test split, we take x as dependent variables and y take as an independent variable then train the model.

Models :

We use 3 models to train the data and for predicting the accuracy.

Logistic regression
Random forest
SVC
XG boost
Feature Selection

There are 25 columns in this dataset and the target variable is the column is default payment next month. We drop the column ‘ID’ and target variable and save the rest 23 as predictor features. These predictor variables include categorical variables such as sex, age, education marital status along with numerical variables, such as payment status, credit limit, bill amount, etc.

Imbalance data :

An imbalanced dataset will mislead machine learning algorithms and affect their performances so then we apply train test split to balance data.

Split Training and Test Data:

In the train test split, we take two variables ie X and Y where X contains all the independent variables and Y containsthe dependent variable. Here the independent variable is default payment next month and dependent variables areaffecting the default payment next month like age, gender, credit limit, education, bill payment, etc.For the model, we use the ratio for training and test data split by 80% for training, 20% for the test to ensure consistency. After splitting the data, we set the test data aside and leave it for the very end, which is the final testing after hyperparameter tuning

Performance Metrics:

Since this is a classification problem with imbalanced classes, we use performance metrics i.e. accuracy precision and recall is a better choice. However, there is a known trade-off between precision and recall. We can raise recall to arbitrarily high, but the precision will decrease. We use the below metrics to measure model performances.

a. Confusion matrix b. ROC_AUC c. Precision recall curve

SMOTE Oversampling:

In the initial model fitting, we start by using all models’ default parameters. To compensate for the rare classes in the imbalance dataset, we use SMOTE(Synthetic Minority Over-Sampling Technique) method to oversample the minority class and ensure the sampling is not biased. What this technique does under the hood is simply duplicateexamples from the minority class in the training dataset before fitting a model. after SMOTE sampling, the dataset has an equal size of 0s and 1s. To verify if SMOTE improves models’ performance, all 3 models are trained with SMOTE and without SMOTE. The below table shows the ROC_ AUC scores on training data 9 improved significantly with all models after oversampling with SMOTE. This proves SMOTE is an effective method in sampling imbalanced datasets. Models Training AUC Without SMOTE Training AUC With SMOTE Logistic Regression 0.726 0.797 Random Forest 0.764 0.916 XGBoost 0.762 0.899 Table 1: Model ROC_AUC score on training data with default parameters

## Conclusion
XGBoost model has the highest recall, if the business cares recall the most, then this model is the best candidate. If the balance of recall and precision is the most important metric, then Random Forest is the ideal model. Since Random Forest has slightly lower recall but much higher precision than Logistic Regression, I would recommend Random Forest.

Data categorical variables had minority classes which were added to their closest majority class

There were not huge gap but female clients tended to default the most.

Labels of the data were imbalanced and had a significant difference.

Gradient boost gave the highest accuracy of 82% on test dataset.

Repayment in the month of september tended to be the most important feature for our machine learning model.

The best accuracy is obtained for the Random forest and XGBoost classifier.

In general, all models have comparable accuracy. Nevertheless, because the classes are imbalanced (the proportion of non-default credit cards is higher than default) this metric is misleading.

Furthermore, accuracy does not consider the rate of false positives (non-default credits cards that were predicted as default) and false negatives (default credit cards that were incorrectly predicted as non-default).

Both cases have negative impact on the bank, since false positives leads to unsatisfied customers and false negatives leads to financial loss.

From above table we can see that XGBoost Classifier having Recall, F1-score, and ROC Score values equals 82%, 77%, and 86% and Random forest Classifier having Recall, F1-score, and ROC Score values equals 81%, 75%, and 84%.

XGBoost Classifier and Decision Tree Classifier are giving us the best Recall, F1-score, and ROC Score among other algorithms. We can conclude that these two algorithms are the best to predict whether the credit card is default or not default according to our analysis.
