# Financial Modeling with Crystal Ball and Excel *by John Charnes (2012)*

**Sep 2023**

## Chapter 9: Portfolio Models


### Single-Period Model

[Download Portfolio.xls](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/tree/main/Excel%20Models/chapter%2009/Portfolio.xlsx)

#### Overview

Assume that you have four asset classes from which to choose for an investment portfolio. These classes are listed in Table 9.1 along with their historical mean total returns, and standard deviations. The Pearson correlations for the four asset classes are in Table 9.2. 

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch09/5.png)

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
Batch Fit was limited to considering only normal or lognormal distributions for the historical returns. The normal distributions used for LCS and SCS were truncated at zero to reflect the limited liability of investing in equities. Batch Fit found that lognormal distributions fit better to CB and GB. Lognormal distributions are bounded by zero from below by definition, so needed no truncation. 

The batch fit process are show in the below table.

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch09/1.png)

The batch fit results are shown in the following table.

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch09/2.png)

#### Decision variables

Each decision variable in cells (AA9:AD9 represents the percent of the initial investment allocated to the corresponding asset class. Each decision variable is defined with a lower bound of 0 percent, an upper bound of 100 percent, and a step size of 1.0 percent. By assuming a lower bound of 0 percent we are precluding the possibility of selling short any of the asset classes. The upper bound of 100 percent precludes borrowing to buy on margin or selling short. The step size of 1 percent is specified to make the optimization converge on a solution more quickly than with a smaller step size. The allocations must sum to 100 percent, so once the allocations are made to LCS, SCS, and CB, the allocation to GB is determined by the formula in cell AD9, =1−AA9−AB9−AC9.

#### @Risk RiskOptimizer Setup

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch09/5.png)

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch09/6.png)

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch09/7.png)

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch09/8.png)

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch09/9.png)

#### Optimization Results

This is an Optimization Model using @Risk RiskOptimizer to find the solution to the following mathematical programming problem:

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch09/3.png)

- E(P) is the expected return on the portfolio
- σ(P) is the standard deviation of the portfolio return, αi is the portfolio weight allocated to asset i = 1, 2, 3, 4 for the ordering of assets (LCS, SCS, CB, GB)
- and ri is the mean rate of return for asset i

The RiskOptimizer in the working

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch09/10.png)

The results shown here were found when using @Risk RiskOptimizer to maximize the mean of the portfolio value forecast in cell AA12, with the additional requirement that the standard deviation of total return be no more than $1,000.

The optimal allocations are (18 percent, 17 percent, 7 percent, 58 percent) for (LCS, SCS, CB, GB). For these allocations, the mean Portfolio Value is $10,849 with a standard deviation of $1,000. 

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch09/11.png)

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch09/12.png)

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch09/15.png)

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch09/16.png)

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch09/17.png)

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch09/18.png)

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch09/19.png)

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch09/20.png)

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch09/21.png)


