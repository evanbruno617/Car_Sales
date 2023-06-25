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

Given the data the variable that has the best linear relationship with SCPI is the average used car price. It has a R^2 value of 0.37 with a standardized coefficient of correlation of 0.57. When predicting the future average used car price in the next month the equation is : price = SCPI * 1493.5 + 6615.38 will be used. Increasinf inflation by 1% will increase the overall price of a used car by 1493 in the following month.

### Unemployment Rate
Using the money supply Linear regression was performed on each of variable in determining how the U/N of the previous month affects the variable of the current month.

![image](https://github.com/evanbruno617/Car_Sales/blob/main/Resources/Univariate/Stick_CPI_2.png)

Given the data the variable that has the best linear relationship with U/N is the avergar used car price. It has a R^2 value of 0.45 with a standardized coefficient of correlation of -0.67. This indicates a nergative correlation between the two. When predicting the future Ratio of Used to New car sales in the next month the equation is : price = U/N * -0.009454 + 0.371 will be used. 

---

## Multivariate











