# Financial Modeling with Crystal Ball and Excel *by John Charnes (2012)*

**Sep 2023**

##  Chapter 10: Value at Risk

[Download PortfolioVaR.xlsx](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/Excel%20Models/chapter%2010/PortfolioVaR.xlsx)

[Download CVaR.xlsx](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/Excel%20Models/chapter%2010/CVaR.xlsx)

### VaR

The concept of Value at Risk (VaR) was devised to obtain a risk measure that associates a severe loss with a probability level of reasonable interest to the decision maker, such as 1 percent or 5 percent. 

In practice, we can think of a potential loss L as the worst that can happen if the probability of losing L or more during a selected time period is a specified amount such as 5 percent. In that case, L is called the "5 percent VaR." More precisely, let R denote the total return (in dollars) on an investment, I, and let c denote the α percentile of the distribution of R. Then the α percent VaR is defined as L = I − c.

The potential loss from investing in the portfolio, I − R, is simply the difference between the initial investment and the final value of the portfolio. 

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch10/3.png)

Because the certainty is 95 percent that portfolio loss is between −Infinity and $821, we say that the 5 percent VaR for one year is $821.

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch10/5.png)

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch10/6.png)

**@Risk Simulation Settings**

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch10/1.png)

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch10/2.png)

Note that when we find the α percent VaR from the loss (I − R) distribution, we use the (1 − α) percentile in the upper tail rather than the α percentile, c, in the lower tail of the distribution of R.

VaR is used by regulators to compute capital requirements for financial institutions, and by managers as an input to risk-management decisions. VaR can also be used by managers to assess the quality of their models. 

For example, if a model provides that there is a 5 percent chance that a bank’s trading operations will lose $1 million over a one-day horizon, then on average the trading operation should lose $1 million or more on 5 percent of the days in a randomly selected period.

If there are many more losses, it implies that the model assigns too little risk to the situation. If there are many fewer losses, it implies that the model assigns too much risk. In this sense, VaR can therefore be used to check the validity of a model.


### Shortcomings of VaR

VaR provides no information about the extent of losses that might occur beyond
the threshold level. In that sense it is very optimistic because it gives a lower bound on potential loss at the α percent level. Further, it is not always subadditive, which means that the VaR of the combination of two or more investments can exceed the sum of the individual VaR for each investment. This is contrary to the basic principle of diversification, which holds that risk will decrease when more assets are held, not increase. This failure to reward diversification is perceived as the greatest shortcoming of VaR. An alternate risk measure, CVaR, overcomes these shortcomings.


### CVaR

CVaR is the expected value of losses beyond the threshold level.

Investments with high CVaR will necessarily have high VaR as well. CVaR, which is also called Conditional Tail Expectation, Expected Tail Loss, Mean Excess Loss, Mean Shortfall, or Tail VaR, is considered to be a more "coherent" measure of risk than VaR. 

A simulation model of a three-asset portfolio. Assets 1, 2, and 3 have mean returns of 10 percent, 12 percent, and 13 percent, respectively, with variance-covariance matrix.

The model simulates returns from a portfolio with weights 0.30, 0.25, and 0.45, invested in Assets 1, 2, and 3, respectively. Asset rates of return are normally distributed, but truncated at −100 percent. 

The model has four forecast cells: Total Value, Asset1 Value, Asset2 Value, and Asset3 Value. Run 50,000 Trials with LHS and Seed = 820.

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch10/2_1.png)

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch10/2_2.png)

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch10/2_3.png)

Set a filter on the forecast values to include values in the range−Infinity to the 1st percentile (entered as a number) of each forecast. The means of the filtered values are used to compute the α = 1 percent CVaR for each asset and the portfolio.

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch10/2_4.png)

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch10/2_7.png)

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch10/2_5.png)

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch10/2_6.png)

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch10/2_8.png)

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch10/2_9.png)

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch10/2_10.png)

CVaR is preferred by some analysts because it is subadditive, which means that the CVaR of the portfolio is always less than or equal to the sum of the individual CVaRs of the portfolio components. VaR is not always subadditive (although it is so in this example), which means that the risk of a portfolio can be larger than the sum of the stand-alone risks of its components when measured by VaR. The CVaR is also less sensitive to changes in the defining percentile α than is VaR.

