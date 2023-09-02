# Financial Modeling with Crystal Ball and Excel *by John Charnes (2012)*

**Sep 2023**

##  Chapter 11: Simulating Financial Time Series

[Download TenYearTreasuryYields2010.xlsx](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/Excel%20Models/chapter%2011/TenYearTreasuryYields2010.xlsx)


### Mean-Reverting Model

The mean-reverting model has the characteristic that its level tends to fluctuate around the mean value, μ. One type of mean-reverting model is the autoregressive model, which takes advantage of the autocorrelation in a time series to predict future values from past values of the series.

#### AR(1) Process

An autoregressive (AR) model of order 1, known as an AR(1) model, is

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch11/7_1.png)

where ![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch11/7_2.png) is a white noise series with mean zero and variance ![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch11/7_3.png)
The above equation is in the same form as a simple regression model, so we can use Excel’s Data Analysis tool to find estimates of the parameters, ![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch11/7_4.png), ![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch11/7_5.png), and ![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch11/7_3.png), then use these estimates to simulate future values of the time series.

The below figure shows the market yield on 10-year U.S. Treasury bonds for 2010.

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch11/7_6.png)


In order to use Excel’s regression capabilities, the data in cells B4:B252 were copied into cells C5:C253. The values in Column C are then called the Lag1 values simply because for each value of the series in Rows 5:254 of Column B, the previous value of the series is in the same row of Column C.

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch11/7_7.png)

To estimate the parameters of the AR(1) model, mouse to Data > Data
Analysis. . . > Regression in Excel.

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch11/7_8.png)

By specifying B5:B254 as the Y Range and C5:C254 as the X Range, and checking the box next to Residuals, we generated a New Worksheet Ply named "AR(1)" containing the output shown in below figures.

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch11/7_9.png)

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch11/7_10.png)


To simulate future values of the time series, we use the model:

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch11/7_11.png)

where ![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch11/7_12.png) is normal with mean zero and standard deviation 0.065. The values 0.041, 0.987, and 0.065 are taken from cells B17, B18, and B7, respectively.

To check whether the residuals appear to be white noise, their autocorrelation is found in cell D25 to be −0.092, which gives a rule of thumb value of −1.458 (less than 2 in absolute value) in cell E25.

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch11/7_13.png) 

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch11/7_17.png) 

Furthermore, using @Risk's Distribution Fitting feature, we found that a normal (0,0.065) distribution fit the residuals well.

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch11/7_14.png) 

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch11/7_15.png) 

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch11/7_16.png) 

For the AR(1) model specified in here ![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch11/7_11.png) , the mean is μ = φ0/(1 − φ1). Therefore, the mean to which our simulated data will revert is estimated as 0.041/(1 − 0.987) = 3.05. Although we can use this model to simulate future values for an indefinite period, it may be best to re-estimate the model parameters periodically as new data become available.
