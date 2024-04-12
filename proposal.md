# Research Proposal: Personal Investing Dashboard

## Big Picture Question: Given certain investment parameters, what is the optimal portfolio for retirement?

By Justin Reed, Maria Maragkelli, Reghan Hesser, Daniel Shin

## Research Questions

1. How do different inheritance goals affect portfolio optimization for retirement?
2. Do different income levels affect the optimal portfolio choice?
    - If yes, then what portfolios are favored at different income levels?
<br>

**Prediction**
$$U(C,B) = \displaystyle\sum_{t=\Delta}^{T_{max}} \frac{(C_{t}/\sqrt{H_{t}})^{1-\gamma}}{1-\gamma} + \theta{\frac{(B+k)^{1-\gamma}}{1-\gamma}}$$

1. We will be using the utility equation from [Anarkulova, Cederburg, O'Doherty](Related_reading/Beyond_Status_Quo.pdf) (2023) to determine optimal portfolio selection
2. Variable Definitions
   1. $C$ is defined as consumption in dollars
   2. $H$ is number of people in household
   3. $t$ is time since started saving (in months)
   4. $\gamma$ is risk aversion
      1. "Normal" is $3.82$
      2. We will adjust this based on respondents self-described risk aversion
   5. $\theta$ is inheritance utility intensity
      1. Normal is $2360 * 12^{\gamma}$
      2. We will adjust this based on respondents self-described inheritance goals
   6. $B$ is inheritance amount
   7. $k$ is the extent to which inheritance is viewed as a luxury good
      1. Normal is $490,000
   8. $\Delta$ is the time between retirement age and savings age in months
   9.  Saving assumption is 10% of income if income is $>15000$
   10. Ask respondent for expected income growth(?)


* *Research question findings will be reported in a markdown file*

## Outputs
* Graph comparing returns of each portfolio through the respondents expected saving periods
  * Optimal portfolio will be highlighted in different color
* Separate pages for each portfolio that show more details about each
  * Gives numerical values for retirement consumption, total inheritance left
* Possibly include calculator for retirement
  * Ask respondent how much they want to spend/save during/for retirement
  * Ask how much inheritance they want to leave
  * Calculate necessary income and necessary retirement age(?)

## Necessary Data
1. The Data will be collected primarily from [Yahoo Finance](https://finance.yahoo.com/)
2. The Unit of observation will be ETF-months
3. Data collected will come from chosen ETFs to represent different asset classes (Date Format: MM/DD/YYYY)
   1. [SPDR S&P 500 ETF Trust](https://finance.yahoo.com/quote/SPY/history?period1=728317800&period2=1712881748)
      1.  Inception Date: 1/29/1993
      2.  Asset Type: Domestic Stocks
      3.  Symbol: SPY
   2. [Vanguard FTSE All-Wld ex-US Idx Admiral](https://finance.yahoo.com/quote/VFWAX/history2)
      1. Inception Date: 9/27/2011
      2. Asset Type: International Stocks
      3. Symbol: VFWAX
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
   6. [Vanguard Target Retirement 2025 Fund](https://finance.yahoo.com/quote/VTTVX?.tsrc=fin-srch)
      1. Inception Date: 6/7/2006
      2. Asset Type: TDF (Stock/Bond Split)
      3. Symbol: VTTVX
   7. [iShares Core Growth Allocation ETF](https://finance.yahoo.com/quote/AOR?.tsrc=fin-srch)
      1. Inception Date: 4/11/2008
      2. Asset Type: Traditional Stock/Bond Split
      3. Symbol: AOR
   8. [Regents Park Hedged Market Strategy ETF](https://finance.yahoo.com/quote/RPHS?.tsrc=fin-srch)
      1. Inception Date: 3/30/2022
      2. Asset Type: Risk Hedging(?)
      3. Symbol: RPHS
   9. [Strategy Shares Nasdaq 7 Handl Index ETF](https://finance.yahoo.com/quote/HNDL?.tsrc=fin-srch)
      1.  Inception Date: 1/16/2018
      2.  Asset Type: ETF ETF?
      3.  Symbol: HNDL
4. The raw inputs for this data will be `.csv` files downloaded from Yahoo Finance
   1. All of the datasets will be saved in the `inputs` folder
      1. columns: Date, Open, High, Low, Close, Adj Close, Volume 
   2. Any importannt dataframes and/or visualizations created from this data will be saved in the `outputs` folder
5. Considering that the ETF inception date to now is often shorter than the span between savings start and retirement we need to figure out a way to estimate portfolio performance(machine learning?)

6. High-level Data cleaning plan

* The datasets from yahoo finance generally have no missing price variables
  * We will need to generate a return variable for each month
  * Uncertain if using Adj. Close or Close **Need Feedback**
  * We will use a cumulative return function similar to previous assignments in order to calculate portfolio performance
* Final Dataframe should look like<br>

Portfolio|Date|Ret
---|---|---
SPY|1-1-2001|.01
SPY|2-1-2001|.01




## Streamlit Dashboard

We will host the dashboard on streamlit<br>
[Link to Streamlit Dashboard](https://github.com/justinreed23/streamlitTesting)