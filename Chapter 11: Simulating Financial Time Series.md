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


