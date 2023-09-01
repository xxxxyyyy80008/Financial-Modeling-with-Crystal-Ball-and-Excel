# Financial Modeling with Crystal Ball and Excel *by John Charnes (2012)*

**Sep 2023**

## Chapter 1: Introduction

### Monte Carlo
The term **Monte Carlo** was motivated by the similarity of the computer-generated results to the action of the gambling devices used at the casinos in the city of Monte Carlo in the principality of Monaco. 
The term caught on and is now widely used in finance, science, and engineering.

### Example
[Download the Excel file](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/Excel%20Models/chapter%2001/Profit.xlsx)

π = SP(1 − V) − F

- π: Profit
- S: sales, follow the Poisson distribution with mean 10
- P: price, is lognormally distributed with mean $50 and standard deviation $10
- V: variable cost percentage, has the beta distribution with parameters minimum = 0%, maximum = 100%, alpha = 2, and beta = 3
- F: fixed cost, is $100

#### @Risk Settings

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch01/2.png)

#### @Risk Input Distribution and Output Set Up


![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch01/1.png)

#### @Risk Simulatino Results

Forecast distribution for the simple profit model. The probability that the profit will be between $0 and $350 is 70.7%; the probability of less than $0 profit is 24.3%.

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch01/3.png)

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch01/4.png)

Sensitivity chart: the input variables (assumptions) V, S, and P are listed from top to bottom in decreasing order of their impact on the output variable (forecast), profit.

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch01/5.png)


### RISK MANAGEMENT

When analyzing risk with the methods presented in this book you will be able to quantify the consequences of uncertainty by answering three main questions:

1. What can happen?
2. How likely is it to happen?
3. Given that it occurs, what are the consequences?

All good managers go through a process by which they consider these questions somehow, even if subconsciously. By taking the time to answer the questions in quantifiable terms, you will develop deeper insight into the problems that you face.

Risk analysis is part of a broader set of methods called risk management, which also seeks to find answers to three main questions:

1. What can be done?
2. What options are available?
3. What are the associated trade-offs in terms of costs, benefits, and risks?



