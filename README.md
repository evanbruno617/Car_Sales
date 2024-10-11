# Car Sales
---
# Purpose
The purpose of this analysis is to analyze car sales data to find trends and predict future trends of prices and demand of cars. The data being analyzed is car sales of each month used and new from the state of Maryland.

# Trends
---
In order to analyze trends of cars a histogram is produced of each category being analyze by month.

## Total Sales

![image](https://github.com/evanbruno617/Car_Sales/blob/main/Resources/Total%20Sales%20New.png)

![image](https://github.com/evanbruno617/Car_Sales/blob/main/Resources/Total%20Sales%20Used.png)

The differences in total sales dont differ too much between used and new cars. The months that rank in the most sales are seen to Typically be the summer months with the slower months being the winter months. This information can be useful to seller in order to know which months to decrease or increase their supply of cars. 

## Average Car Price

The Average car price was taken by taken the ratio of sales to number of cars sold. 

![image](https://github.com/evanbruno617/Car_Sales/blob/main/Resources/Avg_Used.png)

![image](https://github.com/evanbruno617/Car_Sales/blob/main/Resources/Avg_New.png)

Given these two graphs the data is relatively similiar for both used and new cars. The winter months look as if they are when prices are more expensive whereas the summer months have realtively cheaper prices.

## Ratio of Used to New Cars
The ratio of the number of used cars sold to new cars are seen in this graph here.

![image](https://github.com/evanbruno617/Car_Sales/blob/main/Resources/Ratio_Used_New.png)

While the difference between months is slight it still depicts how in Late Spring and Early Summer months the demand for used cars increases relative to new cars and vice versa for February and March. 

---
# Predictions using Linear Regression

Predicting car prices with Linear regression using Economic Data. The Economic Data being used is M2, money supply, 10 year interest rates, Unemployment rates, Sticky CPI rates, and Median CPI rates. Using these factors linear regression is performed to predict future car prices. The variables being tested are: Total Sales of New Cars, Total Sales of Used Cars, Average New Car Prices, Average Used Car prices, The ratio between Used and New cars, and the Ratio between used and new car sales.

## Univariate

### Money Supply
Using the money supply Linear regression was performed on each of variable in determining how the money supply of the previous month affects the variable of the current month.

![image](https://github.com/evanbruno617/Car_Sales/blob/main/Resources/Univariate/M2_2.png)

Given the data the variable that has the best linear relationship with M2 is the average price of new cars. It has a R^2 value of 0.93 with a standardized coefficient of correlation of 0.96. When predicting the future average price of a new car in the next month the equation is : price = M2 * 0.0000000012097 + 18388.33 will be used. 

### Median CPI
Using the money supply Linear regression was performed on each of variable in determining how the median CPI of the previous month affects the variable of the current month.

![image](https://github.com/evanbruno617/Car_Sales/blob/main/Resources/Univariate/Median_CPI_2.png)

Given the data the variable that has the best linear relationship with MCPI is the Ratio of Used to New car sales. It has a R^2 value of 0.562 with a standardized coefficient of correlation of 0.749. When predicting the future Ratio of Used to New car sales in the next month the equation is : price = MCPI * 0.0125 + 0.283 will be used. 

### Sticky CPI
Using the money supply Linear regression was performed on each of variable in determining how the sticky cpi of the previous month affects the variable of the current month.

![image](https://github.com/evanbruno617/Car_Sales/blob/main/Resources/Univariate/Stick_CPI_2.png)

Given the data the variable that has the best linear relationship with SCPI is the average used car price. It has a R^2 value of 0.37 with a standardized coefficient of correlation of 0.57. When predicting the future average used car price in the next month the equation is : price = SCPI * 1493.5 + 6615.38 will be used. Increasing inflation by 1% will increase the overall price of a used car by 1493 in the following month.

### Unemployment Rate
Using the money supply Linear regression was performed on each of variable in determining how the U/N of the previous month affects the variable of the current month.

![image](https://github.com/evanbruno617/Car_Sales/blob/main/Resources/Univariate/Stick_CPI_2.png)

Given the data the variable that has the best linear relationship with U/N is the average used car price. It has a R^2 value of 0.45 with a standardized coefficient of correlation of -0.67. This indicates a nergative correlation between the two. When predicting the future Ratio of Used to New car sales in the next month the equation is : price = U/N * -0.009454 + 0.371 will be used. 

---

## Multivariate
Using multivariate linear regression model, 4 factors are chosen that are used to find the best model to predict: Average cost of a new car, Average cost of a used Car, Ratio of used to new cars sold, Ratio of used to new car sales, Total sales of new cars, and Total sales of used cars.

## Average Price of New Cars

![image](https://github.com/evanbruno617/Car_Sales/blob/main/Resources/Multivariate/Avg_New.png)

As seen with the image above the variables that produce the highest R^2 value are:  10 year interest rate, Money Supply, Median CPI, and Sticky CPI. Given these variables are inputed into the multivariate linear regression it produces a R^2 value of 0.945 with a standardized coefficient of 0.98.

## Average Price of Used Cars

![image](https://github.com/evanbruno617/Car_Sales/blob/main/Resources/Multivariate/Avg_Used.png)

As seen with the image above the variables that produce the highest R^2 value are:  10 year interest rate, Money Supply, Median CPI, and Sticky CPI. Given these variables are inputed into the multivariate linear regression it produces a R^2 value of 0.81 with a standardized coefficient of 0.98.

## Ratio of Used to New Cars Sold

![image](https://github.com/evanbruno617/Car_Sales/blob/main/Resources/Multivariate/Ratio_Used_New.png)

As seen with the image above the variables that produce the highest R^2 value are:  10 year interest rate, Money Supply, Median CPI, and Unemployment. Given these variables are inputed into the multivariate linear regression it produces a R^2 value of 0.63 with a standardized coefficient of 1.09.

## Total Sales of New Cars

![image](https://github.com/evanbruno617/Car_Sales/blob/main/Resources/Multivariate/Total%20Sales%20Used.png)

As seen with the image above the variables that produce the highest R^2 value are: 10 year interest rate, Money Supply, Median CPI, and Sticky CPI.. Given these variables are inputed into the multivariate linear regression it produces a R^2 value of 0.60 with a standardized coefficient of 0.933.

# Caveat
---

Even though these predictions are good with a high R^2 there is an important caveat to acknowledge and that is the assumption of independence. Because this data is taken in recorded during a different time these variables are no longer independent. This violates the assumption of inependence of linear regression however this can be dealt with by converting the model into time series. 

## Time Series

In order to run time series analysis on the data it is imperative to make sure both the dependent and independent variables are stationary. Using the Dickey-Fuller Test it is found that all of the dependent variables looking to be evaluated and the independent variables are stationary with order of integration of 1. Afterwards the regression was run again with these new variables and checked for serial correlation and heteroskedaticity. 

## Total Sales of Used Cars

![image](https://github.com/evanbruno617/Car_Sales/blob/main/Resources/Screenshot%202024-10-10%20at%201.32.05%E2%80%AFPM.png)

As seen in the image above the total sales of Used cars does not seem to be stationary and it fails the Dickey-Fuller test if integration of 0. However when testing for the integration of 1 it is validated. The change of total sales of used cars is seen below as stationary. 

![image](https://github.com/evanbruno617/Car_Sales/blob/main/Resources/Screenshot%202024-10-10%20at%201.32.25%E2%80%AFPM.png)

Afterwards the new regression is ran with the I(1) indepdent variables. 

![image](https://github.com/evanbruno617/Car_Sales/blob/main/Resources/Screenshot%202024-10-10%20at%209.35.36%E2%80%AFPM.png)

After estimating the model the RMSE is extremely high therefore showing that this model is not a good prediction of change of total sales of used cars. 

## Total Sales of New Cars

Regression is ran with the I(1) indepdent variables. 

![image](https://github.com/evanbruno617/Car_Sales/blob/main/Resources/Screenshot%202024-10-10%20at%209.34.43%E2%80%AFPM.png)

After estimating the model the RMSE is extremely high therefore showing that this model is not a good prediction of change of total sales of new cars. 

## Average Price of New Cars

Regression is ran with the I(1) indepdent variables. 

![image](https://github.com/evanbruno617/Car_Sales/blob/main/Resources/Screenshot%202024-10-10%20at%209.36.37%E2%80%AFPM.png)

After estimating the model the RMSE was found to be 498. When looking at the range there are outliers at around -1000 so eliminate those data points and then find NRMSE by dividing RMSE by the total range coming out to be 25%. While not the best result it shows that the model is acceptable. 

## Average Price of Used Cars

Regression is ran with the I(1) indepdent variables. 

![image](https://github.com/evanbruno617/Car_Sales/blob/main/Resources/Screenshot%202024-10-10%20at%209.36.16%E2%80%AFPM.png)

After estimating the model the RMSE was found to be 172. When looking at the range there are outliers at around -1000 and 1000 so eliminate those data points and then find NRMSE by dividing RMSE by the total range coming out to be 16%. This indicates that the model is good estimator in predicting the change in averagr price of used cars. 

## Ratio of Used to New Cars

Regression is ran with the I(1) indepdent variables. 

![image](https://github.com/evanbruno617/Car_Sales/blob/main/Resources/Screenshot%202024-10-10%20at%209.37.45%E2%80%AFPM.png)

After estimating the model the RMSE was found to be 0.063. When looking at the range there weren't any significant outliers so the NRMSE was calculated at 0.15. This indicates that the model is good estimator in predicting the change in ratio in used to new cars. 

![image](https://github.com/evanbruno617/Car_Sales/blob/main/Resources/Screenshot%202024-10-10%20at%201.33.02%E2%80%AFPM.png)

However when testing for serially corelation it was found that there was correlation at lag 2. In order to deal with this lag 1 and 2 were added to the original model to get rid of the serial correlation. 

![image](https://github.com/evanbruno617/Car_Sales/blob/main/Resources/Screenshot%202024-10-10%20at%209.57.14%E2%80%AFPM.png)

After testing the RMSE again it stayed relatively the same but decreasing slightly. 




# Conclusion
---
Given this detailed analysis of trends and predictions of car sales there is a lot of data to base suppliers and buyers strategies from. For supplies they can review the trends in Car Prices and demand to strategize their prices and supply for those given months to maximize profit. Given the same data buyers can use it to their advantage as well to know when prices are at their lowest to buy and when to avoid purchasing. 

Given the predictions portion of this analysis the economic data in the U.S. provides a good indicator that the car market will look like. Even though the linear predictions look good there is the assumption of indepdence being validated which no longer makes the model the best. 

By implementing the time series model it should give the best forecasting predictions for buyers and sellers to use. The models that turned out successful were predicting change in average used and new car prices as well as the change in the ratio of used to new cars. By being able to predict the change in average price of used cars consumers can plan their purchases accordingly and buyers can better manage their supplies and focus on certain months. This same logic works for new cars as well. As for change in ratio of used to new cars this can predict when there is a change in demand. When it predicts the ratio going up that means it will predict there will be a higher demand for used than new cars in that given month. Sellers can use this data to price their cars accordingly given the change in demand and buyers can use this information as well to plan their purchases.  








