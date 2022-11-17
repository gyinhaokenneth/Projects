# Project 2 - Ames Housing Data and Kaggle Challenge

## Problem Statement
Many property owners often rely on their agents to advise them on the selling price of their property. Sometimes, these advise may not be in the favour of the property owners. Agents may rush sellers into closing a deal at a lower price so that they can earn commissions quickly at the expense of their clients. On the flipside, agents may also upsell properties to earn higher commissions.

Ames Property Group, a brokerage agency for residential properties in Ames, Iowa aims to help buyers and sellers buy or sell their properties at the right price. This will help to ensure that our customers do not overpay for a property, or sell a property below their market value, so that customers will put their trust in us to broker the transaction.

As a data analyst within the agency, I am tasked to create a property price prediction calculator that uses past sales data and characteristics of the properties sold to predict the market value of a property based on inputs of selected property features. The calculator should be able to provide a predicted price with low RMSE and low Coefficent of Variance (CV) of less than 20%. The model will be proposed to the senior management team of agency for approval.

## Data Cleaning and Exploratory Data Analysis (EDA)

 - Total number of data entries available: 2051
 - Data related to properties categorised as Agriculture, Industrial and Commercial Zone were dropped.
 - Variables with high number of null values (more than 1000) were excluded from cleaning and the model
 - The distribution of continuous variables was examined. Variables with poor distribution were excluded from the model. From the selected variables, outliers that fall beyond 3 standard deviations were dropped.
 -  Total number of data entries after cleaning: 1952
 - For categorical variables, boxplots were used to examine the variance with the target variable 'saleprice'. Barplots were used to examine the representativeness of each level within the variable. Variables that do not show significant variances in sale price across the scale, or those with under-represented scales/levels will be excluded.
 - Three new variables were engineered from existing variables by combining related information together into single variables.
 - A correlation heatmap was used to assess for multicollinearity between variables. For each variable-pair with high collinearity, one of them will be dropped from the selection.
 -  Scatterplot was used to assess the linear correlation between the continuous variables and 'saleprice'.
 ## Run Models
 - In Model 1, lasso regression was used as it was the best performing.  There is a total of 17 variables, but 4 of them were deemed less impactful as they had coefficients of less than 3000. As such, they were dropped from the model.
 - 13 variables remained for Model 2 - the final model.
### Selected Features for Model 2
|Selected Feature |Type| Output| Description|
|--|--|--|--|
|gr liv area|Continuous|sqft|Total living area of the house|
|overall qual|Ordinal|1-10|Overall material and finish of the house. 1: Very Poor; 10: Very Excellent|
|property_age|Continuous|yrs|Derived by subtracting year built from year of sale|
|total bsmt sf v2|Continuous|sqft|Total area of basement area|
|heat_quality|Ordinal|1-10|Combined ratings of heating quality and fireplace quality. 1: Very Poor; 10: Very Excellent|
|lot area|Continuous|sqft|Lot size|
|overall cond|Ordinal|1-10|Overall condition of the house. 1: Very Poor; 10: Very Excellent|
|garage area v2|Continuous|sqft|Size of garage|
|bedroom abvgr|Discrete|Counts|Number of bedrooms above ground - does not include basement rooms|
|neighborhood_NridgHt|Nominal|1 or 0|Is the property located in NridgHt neighborhood?|
|central_air_scale_1|Nominal|1 or 0|Does the property has central air-conditioning?|
|transport1_0|Nominal|1 or 0|Is the property located near transportation routes (e.g. railway, main roads)?|
|kitchen abvgr|Discrete|Counts|Number of kitchens above ground|

- For Model 2, lasso regression was also the best performing model. The coefficients for all the variables were derived using the lasso regression model. 
- The model was assessed to be a good model as majority of the predicted 'saleprice' values are close to the actual values. It also has a low RMSE of $24000.

|Model Type |R-sq (cross-val)| R-sq (train)|R-sq (test)| Difference (train - test)| RMSE (test)|CV (test)|No. of Features|
|--|--|--|--|--|--|--|--|
|Linear|0.8697|0.8732|0.8583|0.0149|24316.42|0.139|13|
|Lasso|0.8697|0.8732|0.8583|0.0149|24314.05|0.139|13|
|Ridge|0.8697|0.8732|0.8582|0.0150|24323.28|0.139|13|
*Coefficient of Variation = CV*

- The SHAP plot was used to visualise the relative importance of all 13 variables. The top 3 most impactful variables on 'saleprice' are 'gr live area', 'overall qual', and 'property_age'.

## Recommendations and Conclusion
In summary, Model 2 (lasso) has demonstrated to be a good model with high R-sq value of at least 0.85 when run on train and test datasets. With the model, we have also managed to achieve a moderately low RMSE of $24000 and low CV value of 13.9%, indicating that the model could offer predictions that are close to the actual values. The top 3 features that are strong predictors of the sale price are ground living area, overall quality of the property, and the age of the property.

With the completion of the property price prediction model for Ames, we would like to suggest the following recommendations:

1.  To launch the property price estimator on our property listing websites for clients who are buying/selling properties in Ames, Iowa.
2.  Our agents should assess/evaluate their clients' property based on the features selected in the model. Sale price should also be recorded.
3.  Replicate the model with data collection from other cities in Iowa and other states to increase outreach and market share.