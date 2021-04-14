# Take_Home_Test

## 1. Instruction for running script locally
1. Make sure you have installed following packages:
    1. pandas
    2. statsmodels
    3. json
    4. urllib
2. The output message is the result of Linear regression model

## 2. Data Cleansing
1. Data Correction - Look at the format of raw data and perform data correction if necessary
2. Data Completing - Look at the info of DataFrame. If there are null values or missing data, we could use these two methods:
    1. Impute the missing values
        1. Basic - Using mean, median or mean + randomized standard deviation
        2. Intermediate - Basic on specific criteria
        3. Complex - Predict missing values with Machine Learning algorithms
    2. Delete the record

## 3. Decide Covariates
There are a few ways help to decide on the covariates in the model:
1. Correlation analysis between all explanatory variables to detect multicollinearity
2. Use stepwise/backward/forward procedure to add or subtract variables based on p-values
3. Monitor a model fit statistic like AIC or BIC to evaluate the goodness of fit
4. Use sklearn.feature_selection to help with selection

## 4. Interpretation of the Coefficients
The coefficients of surgeries_last_month, service_id=1(cardiothoracic surgery) and service_id=2 (general surgery) are positive while coefficients of age and service_id=3 (orthopedic surgery) are negative.
This means surgeons who have more surgeries last month tend to have more surgeries next month. However, younger surgeons might have more surgeries.
Furthermore, the relation of average number of different surgery categories is general surgery > cardiothoracic surgery > orthopedic surgery 

## 5. Goodness of Fit
The R<sup>2</sup>(0.945) and adj R<sup>2</sup>(0.944)) value are very large, which means the variance is well explained.
The AIC(1785) and BIC(1801) are too high, which means both our model fitting and prediction power need improvement.
The p-value of F-statistic is very small, which means the overall significance in this regression looks great.

## 6. Output of Summary
![image](https://user-images.githubusercontent.com/26566294/114658478-b4fe4900-9ca6-11eb-8a82-5108f6c82f72.png)
