# Financial Modeling with Crystal Ball and Excel *by John Charnes (2012)*

**Sep 2023**

## Chapter 9: Portfolio Models

### Single-Period Crystal Ball Model.

[Download Portfolio.xls]()

#### Overview

Assume that you have four asset classes from which to choose for an investment portfolio. These classes are listed in Table 9.1 along with their historical mean total returns, and standard deviations. The Pearson correlations for the four asset classes are in Table 9.2. The data from which these parameters were estimated are in cells B11:E96 of the Stochastic Model tab of Portfolio.xls.

To keep things simple we will assume that you have $10,000 to invest (cell A4) and wish to find the optimal percentage to invest in each of the asset classes (B8:E8). We ignore the effects of inflation for now.

**FIGURE 9.1 Spreadsheet segment from model to simulate a single-period portfolio model.**

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch09/f9_1.png)

**TABLE 9.2 Pearson correlation matrix for annual total returns during the period 1926 to 2010 for four asset classes.**

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch09/t9_2.png)

**TABLE 9.3 Spearman correlation matrix for annual total returns during the period 1926 to 2010 for four asset classes.**

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch09/t9_3.png)

####Forecast

The forecast for this example is the portfolio value in cell F8, the value of the portfolio one year from now.
Stochastic assumptions. The assumptions are defined in cells O12:R12 by using
Batch Fit to find the distributions and Spearman correlations.
The assumptions are referenced in cells B7:E7. Batch Fit was limited
to considering only normal or lognormal distributions for the historical
returns. The normal distributions used for LCS and SCS were truncated
at zero to reflect the limited liability of investing in equities. Batch Fit
found that lognormal distributions fit better to CB and GB. Lognormal
distributions are bounded by zero from below by definition, so needed
no truncation. The Spearman correlation matrix computed by Batch Fit
is shown in Table 9.3.
Decision variables. Each decision variable in cells B8:D8 represents the percent
of the initial investment allocated to the corresponding asset class. Each
decision variable is defined with a lower bound of 0 percent, an upper
bound of 100 percent, and a step size of 1.0 percent. By assuming a lower
bound of 0 percent we are precluding the possibility of selling short any
of the asset classes. The upper bound of 100 percent precludes borrowing
to buy on margin or selling short. The step size of 1 percent is specified
to make the optimization converge on a solution more quickly than with
a smaller step size. The allocations must sum to 100 percent, so once
the allocations are made to LCS, SCS, and CB, the allocation to GB is
determined by the formula in cell E8, =1−B8−C8−D8.
Summary. The results shown here were found when using OptQuest to maximize
the mean of the portfolio value forecast in cell F8, with the additional
requirement that the standard deviation of total return be no more than
$1,000. The optimal allocations are (27 percent, 11 percent, 0 percent,
62 percent) for (LCS, SCS, CB, GB) as shown in cells B8:E8 in Figure 9.1.
For these allocations, the mean Portfolio Value is $10,857 with a standard
deviation of $1,000. By running OptQuest for longer than the
60 minutes used to obtain these results, one may be able to improve
on the results slightly.

### Single-Period Analytical Solution

### Multiperiod Crystal Ball Model
