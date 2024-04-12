# Research Proposal: Personal Investing Dashboard

## Big Picture Question: Given certain investment parameters, what is the optimal portfolio for retirement?

By Justin Reed, Maria Maragkelli, Reghan Hesser, Daniel Shin

## Research Questions

1. How do different inheritance goals affect portfolio optimization for retirement?
2. Do different income levels affect the optimal portfolio choice?
    - If yes, then what portfolios are favored at different income levels?
<br>

**Prediction**
$$U(C,B) = \sum_{t=481}^{T_{max}} \frac{(C^{i}_{t}/\sqrt{H^{i}_{t}})^{1-\gamma}}{1-\gamma} + \theta{\frac{(B^{i}+k)^{1-\gamma}}{1-\gamma}}$$


$U(C,B) = \sum_{t=481}^{T_{max}}$


* *research question findings will be reported in a markdown file*

## Necessary Data
1. The Data will be collected primarily from [Yahoo Finance](https://finance.yahoo.com/)
2. The Unit of observation will be ETF-months
3. Data collected will come from 5 chosen ETFs to represent different asset classes
   1. [SPDR S&P 500 ETF Trust](https://finance.yahoo.com/quote/SPY/history?period1=728317800&period2=1712881748)
      1.  Inception Date: 1/29/1993
      2.  Asset Type: Domestic Stocks
      3.  Symbol: SPY
   2. [Goldman Sachs MarketBeta Emer Mkt Eq ETF](https://finance.yahoo.com/quote/SPEM/history?period1=1174656600&period2=1712882062)
      1. Inception Date: 3/23/2007
      2. Asset Type: International Stocks
      3. Symbol: GSEE
   3. [Vanguard Total Bond Market Index Fund](https://finance.yahoo.com/quote/BND?.tsrc=fin-srch)
      1. Inception Date: 4/10/2007
      2. Asset Type: Bonds
      3. Symbol: BND
   4. [iShares 0-3 Month Treasury Bond ETF](https://finance.yahoo.com/quote/BIL/history?period1=1180531800&period2=1712883476)
      1. Inception Date: 5/30/2007
      2. Asset Type: Bills
      3. Symbol: SGOV
   5. [Vanguard Real Estate Index Fund ETF Shares](https://finance.yahoo.com/quote/VNQ/history?period1=1096464600&period2=1712883679)
      1. Inception Date: 9/29/2004
      2. Asset Type: Real Estate
      3. Symbol: VNQ
   6. [Vanguard Target Retirement 2020 Fun](https://finance.yahoo.com/quote/VTWNX/history)
      1. Inception Date: 6/7/2006
      2. Asset Type: TDF (Stock/Bond Split)
      3. Symbol: VTWNX




## Streamlit Dashboard

Our final dataset will then be used to determine the optimal portfolio for a given investor using a list of parameters including
1. Current age (Integer)
2. Current income (float?)
3. Expected income growth per year (float)
4. expected retirement age (integer)
5. risk aversion (Categorical: High, Medium, Low)
6. Inheritance level (Categorical : High,medium,low, none)
7. Saving rate? (Maybe assume 10%)
8. Withdrawl rate for retirement assumed to be 4%
9. Household Size
10. utility function from study for retirement consumption
    1.  $U(C^{i},B^{i}) = \sum_{t=481}^{T^{i}_{max}} \frac{(C^{i}_{t}/\sqrt{H^{i}_{t}})^{1-\gamma}}{1-\gamma} + \theta{\frac{(B^{i}+k)^{1-\gamma}}{1-\gamma}}$
    2.  Okay but what the fuck does that mean? **THIS NEEDS EDITING**
    3.  C is consumption
    4.  i is couple (we don't need this)
    5.  t is month (0 is start savings)
    6.  t = 481 isn't necessarily true it's just
        1.  $Retirement\_age - start\_age = t$
        2.  so for example
        3.  $(65*12)-(25*12) + 1 = 481$
    7.  $H^{i}_{t}$ is number of people in household at time t
        1.  Basically consumption is divided by number of people in household because assumption is that consumption doesn't increase linearly(?)
    8.  $\gamma$ is risk aversion
        1.  The paper uses 3.84 following Duarte, Fonseca, Goodman, and Parker (2022)
        2.  This will be a parameter (use 3.84 as medium?)
    9. $B$ is the bequest of household
       1.  How much they leave when they die
    1. $\theta$ is bequest utility?
       1. From paper De Nardi, French, and Jones (2016)
       2. $\theta$ = 2360 in the study but we can raise/lower it
       3. This is actually multipled by $12^{\gamma}$ to translate from annual -> monthly
    2.  $k$ is the extent to which inheritance is viewed as a luxury good, K = $490,000