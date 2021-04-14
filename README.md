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
<br>
OLS Regression Results                             
================================================================================
Dep. Variable:     surgeries_this_month   R-squared:                       0.945
Model:                              OLS   Adj. R-squared:                  0.944
Method:                   Least Squares   F-statistic:                     842.5
Date:                  Tue, 13 Apr 2021   Prob (F-statistic):          8.39e-122
Time:                          20:23:14   Log-Likelihood:                -887.42
No. Observations:                   200   AIC:                             1785.
Df Residuals:                       195   BIC:                             1801.
Df Model:                             4                                         
Covariance Type:              nonrobust                                         
========================================================================================
                           coef    std err          t      P>|t|      [0.025      0.975]
----------------------------------------------------------------------------------------
age_in_yrs              -0.0247      0.139     -0.177      0.859      -0.300       0.250
surgeries_last_month     1.1997      0.022     55.711      0.000       1.157       1.242
service_id_1             3.1536      7.719      0.409      0.683     -12.069      18.376
service_id_2            34.4692      7.711      4.470      0.000      19.262      49.677
service_id_3           -12.8496      7.521     -1.708      0.089     -27.683       1.984
==============================================================================
Omnibus:                        6.471   Durbin-Watson:                   2.196
Prob(Omnibus):                  0.039   Jarque-Bera (JB):                5.018
Skew:                          -0.278   Prob(JB):                       0.0814
Kurtosis:                       2.459   Cond. No.                     1.31e+03
==============================================================================
