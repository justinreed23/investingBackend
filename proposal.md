# Research Proposal: Personal Investing Dashboard

## Big Picture Question: Given certain investment parameters, what is the optimal portfolio for retirement?

By Justin Reed, Maria Maragkelli, Reghan Hesser, Daniel Shin

## Research Questions

1. How do different inheritance goals affect portfolio optimization for retirement?
2. Do different income levels affect the optimal portfolio choice?
    - If yes, then what portfolios are favored at different income levels?

* *research question findings will be reported in a markdown file*

## Necessary Data
1. Our final dataset will consist of monthly returns for 10 portfolios that are ETFs representative of certain securities(U.S stocks, International Stocks, bonds, bills, etc)
2. Data will primarily be collected from: insert where to find returns for portfolios here
   1. The observation level for our final dataset will be portfolio-months





## Streamlit Dashboard

Our final dataset will then be used to determine the optimal portfolio for a given investor using a list of parameters including
1. Current age (Integer)
2. Current income (float?)
3. Expected income growth per year (float)
4. expected retirement age (integer)
5. risk aversion (High, Medium, Low)
6. Inheritance level (High,medium,low, none?)
7. Include social security benefits
   1. SSI becomes taxable once income >$25,000 each year
   2. Maybe assume that users are using a Roth IRA