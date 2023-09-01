# Financial Modeling with Crystal Ball and Excel *by John Charnes (2012)*

**Sep 2023**

## Chapter 1: Introduction

### Monte Carlo
The term **Monte Carlo** was motivated by the similarity of the computer-generated results to the action of the gambling devices used at the casinos in the city of Monte Carlo in the principality of Monaco. 
The term caught on and is now widely used in finance, science, and engineering.

### Example

π = SP(1 − V) − F

- π: Profit
- S: sales, follow the Poisson distribution with mean 10
- P: price, is lognormally distributed with mean $50 and standard deviation $10
- V: variable cost percentage, has the beta distribution with parameters minimum = 0%, maximum = 100%, alpha = 2, and beta = 3
- F: fixed cost, is $100

#### @Risk Settings

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch1/2.png)

#### @Risk Input Distribution and Output Set Up


![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch1/1.png)

#### @Risk Simulatino Results

Forecast distribution for the simple profit model. The probability that the profit will be between $0 and $350 is 70.7%; the probability of less than $0 profit is 24.3%.

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch1/3.png)

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch1/4.png)

Sensitivity chart: the input variables (assumptions) V, S, and P are listed from top to bottom in decreasing order of their impact on the output variable (forecast), profit.

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch1/5.png)
