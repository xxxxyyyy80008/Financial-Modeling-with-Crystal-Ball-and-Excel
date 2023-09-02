# Financial Modeling with Crystal Ball and Excel *by John Charnes (2012)*

**Sep 2023**

##  Chapter 10: Value at Risk

[Download PortfolioVaR.xlsx](PortfolioVaR.xlsx)

### VaR

The concept of Value at Risk (VaR) was devised to obtain a risk measure that associates a severe loss with a probability level of reasonable interest to the decision maker, such as 1 percent or 5 percent. 

In practice, we can think of a potential loss L as the worst that can happen if
the probability of losing L or more during a selected time period is a specified
amount such as 5 percent. In that case, L is called the “5 percent VaR.” More
precisely, let R denote the total return (in dollars) on an investment, I, and let c denote the α percentile of the distribution of R. Then the α percent VaR is defined as L = I − c.

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

### CVaR

CVaR is the expected value of losses beyond the threshold level. Figure 10.2 shows
a forecast window for the portfolio loss in PortfolioVaR.xls. During the definition
of cell C11 as a forecast, a filter was set on the forecast values to exclude values
in the range −Infinity up to $809.86. That is why “2,500 Trials” appears in
the upper left part of the forecast window, even though 50,000 trials were run.


The mean of these 2,500 largest forecast values is $1,200.17. In general, the α
percent CVaR is the expected value of losses that exceed the α percent VaR level.
Figure 10.3 depicts the 5 percent VaR and CVaR on the loss distribution for a
one-year holding period for the portfolio in PortfolioVaR.xls.
Investments with high CVaR will necessarily have high VaR as well. CVaR,
which is also called Conditional Tail Expectation, Expected Tail Loss, Mean
Excess Loss, Mean Shortfall, or Tail VaR, is considered to be a more “coherent”
measure of risk than VaR. Artzner, Delbaen, Eber, and Heath (1999) describe
subadditivity and other coherent measures of risk in detail. Uryasev (2000) and
Hardy (2006) are good references on the basics of CVaR.


