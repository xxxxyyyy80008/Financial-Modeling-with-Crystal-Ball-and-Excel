# Financial Modeling with Crystal Ball and Excel *by John Charnes (2012)*

**Sep 2023**

##  Chapter 12: Financial Options

[Download PrincipalProtectedInstrument.xlsx](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/Excel%20Models/chapter%2012/PrincipalProtectedInstrument.xlsx)


### Principal-Protected Instrument

While not strictly an option, the analysis of principal-protected instruments (PPIs) is included here to demonstrate how to model another derivative security recently introduced in the marketplace.

Principal-protected instruments (PPIs) are sold to risk-averse investors who wish to contractually guarantee that they will not lose any of their initial investment, but also wish to participate to some extent in upward movements of the price of a financial investment. They are hybrid securities that combine a fixed-income instrument with a series of derivative components. PPIs have been engineered for assets such as equities, currencies, interest rates, or commodities.

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch12/7_5.png)

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch12/7_6.png)

The above figures show a model for valuing a PPI with the following characteristics: For every quarter of its five-year life, the PPI quarterly return tracks the quarterly return on the underlying asset XYZ. However, if the quarterly rate of return on XYZ exceeds 15 percent for any quarter, the PPI return for that quarter is capped at 15 percent. At the end of five years, the PPI will deliver a final amount determined by the 20 quarterly returns specified in the contract.

Denote the initial investment as I, the final value of XYZ as ![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch12/7_3.png), the final value of PPI as ![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch12/7_4.png), and the quarterly rate of return on XYZ stock as Ri for i = 1, 2, . . . , 20. The final value of XYZ is

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch12/7_1.png)

while the final value of PPI is

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch12/7_2.png)

The simulation model generates quarterly values for asset XYZ using geometric Brownian motion with parameters μ = 12 percent and σ = 30 percent. 

##### Distribution of the difference in annualized rates of return on a PPI and the underlying asset.

![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch12/7_7.png)

Figure above shows the difference in annualized rates of return when holding the PPI and XYZ alone. The risk-averse investor pays 2.88 percent on average to guarantee that the principal is not lost.


![png](https://github.com/xxxxyyyy80008/Financial-Modeling-with-Crystal-Ball-and-Excel/blob/main/img/ch12/7_8.png)

Figure above also shows that the probability is about 70 percent that the investor would realize a greater return by holding XYZ alone than by holding the PPI.
