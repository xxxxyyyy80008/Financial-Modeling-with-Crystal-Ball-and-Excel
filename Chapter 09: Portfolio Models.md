# Financial Modeling with Crystal Ball and Excel *by John Charnes (2012)*

**Sep 2023**

## Chapter 9: Portfolio Models


### Single-Period Crystal Ball Model

[Download Portfolio.xls]()

#### Overview

Assume that you have four asset classes from which to choose for an investment portfolio. These classes are listed in Table 9.1 along with their historical mean total returns, and standard deviations. The Pearson correlations for the four asset classes are in Table 9.2. 

To keep things simple we will assume that you have $10,000 (AA4) to invest and wish to find the optimal percentage to invest in each of the asset classes (AA9:AD9). We ignore the effects of inflation for now.

**TABLE 9.1 Means and standard deviations for annual total returns, ![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch09/4.png) ,during the period 1926 to 2010 for four asset classes.**

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch09/t9_1.png)

**TABLE 9.2 Pearson correlation matrix for annual total returns during the period 1926 to 2010 for four asset classes.**

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch09/t9_2.png)

**TABLE 9.3 Spearman correlation matrix for annual total returns during the period 1926 to 2010 for four asset classes.**

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch09/t9_3.png)

#### Forecast

The forecast for this example is the portfolio value in cell AA12, the value of the portfolio one year from now.

#### Stochastic assumptions

The assumptions are defined in cells AA8:AD8 by using Batch Fit to find the distributions and Spearman correlations. 
Batch Fit was limited to considering only normal or lognormal distributions for the historical returns. The normal distributions used for LCS was truncated at zero to reflect the limited liability of investing in equities. Batch Fit found that lognormal distributions fit better to SCS, CB and GB. Lognormal distributions are bounded by zero from below by definition, so needed no truncation. 

The batch fit process are show in the below table.

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch09/1.png)

The batch fit results are shown in the following table.

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch09/2.png)

#### Decision variables

Each decision variable in cells (AA9:AD9 represents the percent of the initial investment allocated to the corresponding asset class. Each decision variable is defined with a lower bound of 0 percent, an upper bound of 100 percent, and a step size of 1.0 percent. By assuming a lower bound of 0 percent we are precluding the possibility of selling short any of the asset classes. The upper bound of 100 percent precludes borrowing to buy on margin or selling short. The step size of 1 percent is specified to make the optimization converge on a solution more quickly than with a smaller step size. The allocations must sum to 100 percent, so once the allocations are made to LCS, SCS, and CB, the allocation to GB is determined by the formula in cell AD9, =1−AA9−AB9−AC9.


#### Summary

This is an Optimization Model using @Risk RiskOptimizer to find the solution to the following mathematical programming problem:

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch09/3.png)

- E(P) is the expected return on the portfolio
- σ(P) is the standard deviation of the portfolio return, αi is the portfolio weight allocated to asset i = 1, 2, 3, 4 for the ordering of assets (LCS, SCS, CB, GB)
- and ri is the mean rate of return for asset i


### Single-Period Analytical Solution.

### Multiperiod Crystal Ball Model.
