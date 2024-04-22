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
   9.  $T^{max}$ is date of death.
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
      1.  Asset Type: Domestic Stocks
      3.  Symbol: SPY
   1. [Vanguard FTSE All-Wld ex-US Idx Admiral](https://finance.yahoo.com/quote/VFWAX/history2)
      1. Inception Date: 9/27/2011
      5. Asset Type: International Stocks
      6. Symbol: VFWAX
   1. [Vanguard Total Bond Market Index Fund](https://finance.yahoo.com/quote/BND?.tsrc=fin-srch)
      1. Inception Date: 4/10/2007
      8. Asset Type: Bonds
      9. Symbol: BND
   1. [iShares 0-3 Month Treasury Bond ETF](https://finance.yahoo.com/quote/BIL/history?period1=1180531800&period2=1712883476)
      1. Inception Date: 5/30/2007
      11. Asset Type: Bills
      12. Symbol: SGOV
   1. [Vanguard Real Estate Index Fund ETF Shares](https://finance.yahoo.com/quote/VNQ/history?period1=1096464600&period2=1712883679)
      1. Inception Date: 9/29/2004
      14. Asset Type: Real Estate
      15. Symbol: VNQ
   1. [Vanguard Target Retirement 2025 Fund](https://finance.yahoo.com/quote/VTTVX?.tsrc=fin-srch)
      1. Inception Date: 6/7/2006
      17. Asset Type: TDF (Stock/Bond Split)
      18. Symbol: VTTVX
   1. [iShares Core Growth Allocation ETF](https://finance.yahoo.com/quote/AOR?.tsrc=fin-srch)
      1. Inception Date: 4/11/2008
      20. Asset Type: Traditional Stock/Bond Split
      21. Symbol: AOR
   1. [Regents Park Hedged Market Strategy ETF](https://finance.yahoo.com/quote/RPHS?.tsrc=fin-srch)
      1. Inception Date: 3/30/2022
      23. Asset Type: Risk Hedging(?)
      24. Symbol: RPHS
   1. [Strategy Shares Nasdaq 7 Handl Index ETF](https://finance.yahoo.com/quote/HNDL?.tsrc=fin-srch)
      1. Inception Date: 1/16/2018
      26. Asset Type: ETF ETF?
      27. Symbol: HNDL
4. The raw input for this data will be one `.csv` file containing the following columns: Name, Date, AdjClose. This will be saved in the `inputs` folder

   1. From this dataset, we will calculate a monthly return for each ETF and store that in a column called Ret
   
   1. We will convert this 'tall' dataset to a 'wide' one, that includes a row for each 'Date' and a column for each ETF's 'Ret' on that date
   
   1. We will drop all rows that are missing at least one ETF
   
   1. Finally, we will randomly pull rows to create a dataframe with 600 rows (12 months * 50 years) and convert this back to a tall dataframe. This will be our final dataframe.
   
5. Any importannt dataframes and/or visualizations created from this data will be saved in the `outputs` folder

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
SPY|3-1-2001|.05
VFWAX|1-1-2001|.01
VFWAX|2-1-2001|.23
VFWAX|3-1-2001|.03
AOR|1-1-2001|.003
AOR|2-1-2001|-.04
AOR|3-1-2001|.034




## Streamlit Dashboard

We will host the dashboard on streamlit<br>
[Link to Streamlit Dashboard](https://github.com/justinreed23/streamlitTesting)
