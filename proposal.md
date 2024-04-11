# Research Proposal: Personal Investing Dashboard

## Big Picture Question: Given certain investment parameters, what is the optimal portfolio for retirement?

By Justin Reed, Maria Maragkelli, Reghan Hesser, Daniel Shin

## Research Questions

1. How do different inheritance goals affect portfolio optimization for retirement?
2. Do different income levels affect the optimal portfolio choice?
    - If yes, then what portfolios are favored at different income levels?
<br>

**Prediction**


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