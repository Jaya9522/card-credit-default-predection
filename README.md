# card-credit-default-predection

##Problem Discription 

In recent years, the credit card issuers in Taiwan faced the cash and credit card debt crisis and the delinquency is expected to peak in the third quarter of 2006 (Chou,2006). In order to increase market share, card-issuing banks in Taiwan over-issued cash and credit cards to unqualified applicants. At the same time, most cardholders, irrespective of their repayment ability, overused credit card for consumption and accumulated heavy credit and cash–card debts. The crisis caused the blow to consumer finance confidence and it is a big challenge for both banks and cardholders.
Steps involved :

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

More credit card defualt for limit balance about 10000. It might mean that credit card might be too easy to be issued for people who have low credit scores. The variance of the default rate for limit balance over 500,000 NTD is higher than other range of limit balance. It is lower default rate for cardholders have higher education level. Moreover, the default rate for clients whose age over 60 was higher than mid age and young people. The best fit algorithm for predicting limit balance is bagging approach. The best fit algorithm for predicting whether a client default next month is classification tree.
