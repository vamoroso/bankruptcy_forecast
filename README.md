# bankruptcy_forecast
Repo containing code and analysis to forecast Canadian bankruptcy rates.

### Introduction
One of the main interests of businesses across the world is to be able to accurately predict into the future. A
business owner may want to predict what their sales will be for the next month so they can plan appropriate
expenditures. A Wall Street analyst wishes to predict the rise and fall of stock prices. A weatherman hopes
to predict when the next storm will occur and where it will fall, to ensure the safety of communities. All
of these applications involve looking at data and trends from the past, and using that past data to make
predictions into the future. When a set of data depends on time, it forms what is called a time series, and
the science of making predictions and estimations into the future is known as forecasting.

### Problem Description and Data
The problem we are dealing with at hand is to precisely and accurately forecast bankrupty rates for Canada.
To do this, we are given four data points to consider: Unemployment Rate, Bankruptcy Rate, Population, and
Housing Price Index. The unemployment rate is a measure of the prevalence of unemployment, calculated by
dividing the number of unemployed individuals by all individuals currently in the labor force. The bankruptcy
rate, which is the variable we wish to predict, refers to the rate of people who cannot repay the debts they
owe to creditors and have had to file for bankruptcy. Population is the current number of people living in
Canada, and housing price index measures the price changes of residential housing during a given time.
For each of these variables, we have monthly data from January 1987 to December 2010. 

### Goal
Our goal is to use this data to create a time series model that will allow us to forcast into the future or make precise predictions
about what the bankruptcy rates in Canada will be from January 2011 to December 2012.

### Methods and Results
The available methods that were used in this project to determine the best model included Classical Decomposition, SARIMA, SARIMAX, Holt-Winters, VAR. After trying each approach, the model that we found to make the most accurate and precise predictions was a
SARIMAX model. Recall that in a SARIMAX model, we acknowledge that external variables are influencing our primary variable of interest, though initially we are not sure which ones. Plotting these three external variables it was clear that the trends of all three variables over time were related to bankruptcy rate, though it was questionable whether the rising population was actually affecting bankruptcy, or just happened to have a similar trend over time.  Since we had three external variables, we created a variety of SARIMAX models including different variables of different orders. Out of these models, the best model that we found which included the use of all three external variables, house price index, unemployment rate, and population, was SARIMAX(1,1,5)x(2,1,3). This model gave us an RMSE of 0.002840527. The best model we found that did not include population, but still included house price index and unemployment rate was SARIMAX(4,1,5)x(5,1,3). This model gave us an RMSE of .002766579.  Taking the model complexity into account and comparing the orders of these two models it was apparent that the model that did not include population had higher values for both p and P. A value of p = 4 compared to p = 1, means that in order to make predictions into the future, we would need to use the previous four days worth of observations as opposed to one day. Thus, even though this second model not including population produced a slightly lower RMSE of .0027 as compared to .0028, we decided taking complexness into consideration the SARIMAX(1,1,5)x(2,1,3) was the best model.  This model would not only produced accurate and precise predictions, but also be significantly simpler and easier to interpret.  With the model and order chosen, With our model and order chosen, we were then able to to use all of the original data on bankruptcy rates, from January 1987- December 2010, to forecast the January 2011 – December 2012 bankruptcy rates. The results of these predictions in graphical and tabular form are included in the conclusion section of the included pdf.

