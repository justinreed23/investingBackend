# Research Proposal: Personal Investing Dashboard

By Justin Reed, Maria Maragkelli, Reghan Hesser, Daniel Shin

## Research Question

Given certain investment parameters, what is the optimal personal investment strategy for retirement?

How do different inheritance goals affect portfolio optimization for retirement?

How does age affect risk aversion


This section should cover:

1. What do we want to know or what problems are we trying to solve? As in the midterm, you should list (1) the “bigger” question/debate/problem you’re interested in, and also (2) the specific research question(s) you’ll actually try to answer.

For retirement purposes is it better to invest in an all equity portfolio or a traditional TDF?

    - The research question will be smaller in scope than the big picture question. But the answer to your specific research question should shed light on the bigger question (although it likely won’t conclusively answer it).

    - The answer to your specific research question should shed light on the bigger question (although it likely won’t conclusively answer it).

2. If your project is about relationships, what are the hypotheses you’re testing?

3. If your project is about prediction, what is your metrics of success? (What are you maximizing?) Can you find a baseline from prior work to give you a ball park to aim for?

Maximize the utility gained 

## Necessary Data

This section should cover:

1. What does the final dataset need to look like (mostly dictated by the question and the availability of data):
    - What is an observation, e.g. a firm, or a firm-year, etc.
          - Observation is daily-portfolio-returns
    - What is the sample period?
          - 1959-2019
    - What are the sample conditions? (Years, restrictions you anticipate (e.g. exclude or require some industries)
          - 60 years, 10 portfolios
          - International stocks defined in paper
    - What variables are absolutely necessary and what would you like to have if possible?
          - returns
          - years
2. What data do we have and what data do we need?
        - Data from the paper
4. How will we collect more data?
5.     stealing from the paper
6. What are the raw inputs and how will you store them (the folder structure(s) for each input type)?
7. 
8. Speculate at a high level (not specific code!) about how you’ll transform the raw data into the final form.

merge returns on year

Get daily returns, make them yearly returns
merge yearly returns together

Security type
return
date



## Dictionary for Terms from Article

1. DC: Defined contribution
    - Every year, Americans contribute about 5% of their total employee compensation to defined contribution (DC) pension plans
2. PPA: Pension Protection Act of 2006
    - Created safe harbors for employers for default options in DC plans
    - These are QDIAs
3. QDIA: Qualified Default Investment Alternative
    - Default options in DC plans
    - Most popular type of QDIA is a portfolio that provides "long-term appreciation and capital preservation through a mix of equity and fixed income exposures based on the participant's age"
    - Regulators rely on "generally accepted investment theories"
    - Basically advice is split investments across stocks and bonds and invest more in stocks while young than while old.
4. TDF: Target-date fund
    - This is a type of QDIA
    - A TDF basically targets a specific year as the retirement age and then rebalances the fund every so often according to that target
    - Effectively as retiree moves closer to retirement date, stocks $\downarrow$ and bonds $\uparrow$
5. SSA: Social Security Administration
6. Stocks/I
    - 50% domestic stocks/ 50% international stocks portfolio
7. Stocks
    - 100% domestic stocks portfolio
8. IID: Independently and identically distributed (returns)




## Important information from Article

- Evaluate strategies based on: Wealth at retirement, retirement income, conservation of savings, and bequest at death.
  - Study lifecycle portfolios on long-horizon returns rather than short-horizon (monthly/annual) returns given nature of retirement investing
- Simple, all-equity portfolio outperforms QDIAs across all retirement outcomes.
- Strategy of 50% in domestic stocks and 50% international stocks throughout one's lifetime (Not a QDIA) dominates QDIAs in long-term appreciation, higher initial retirement consumption, also compares favorably in capital preservation
- 50/50 less likely to exhaust savings and more likely to leave large inheritance
- Non QDIA strategy beats TDF/other QDIAs in achieving PPA goals
- See below, but effectively Stocks/I dominates TDF
  - However Stocks/I has a larger intermediate drawdown than TDF
  - Regulations stipulate QDIAs be "diversified so as to minimize the risk of large losses"
  - Department of Labor and SEC held joint hearing in 2009 to discuss large TDF losses from '08 crash
  - Minimizing intermediate drawdowns appears to be priority for regulators regardless of retirement outcomes
  - Policy issue? Should regulation focus on minimizing psychological pain of intermediate drawdowns vs maximizing economic outcomes of retirement savers given vast performance disparities
- Under US-IID Method (Method that uses only US returns relying on short term evenly distributed data)
  - TDFs seem favorable compared to Stocks/I for capital preservation
  - However, acknowledging returns are NOT IID ***OR*** that US sample presents a severe small sample problem for long-horizon asset performance restores dominance of Stocks/I


**4 Discussed Strategies**
- Money Market
- Stocks (100% domestic)
  - 30% higher average retirement compared to TDF
  - Worse left-tail outcomes
  - 17.4% ruin probability
- Stocks/I (50dom/50int)
  - 32% higher average retirement compared to TDF
  - Favored relative to TDF through entire distribution of wealth outcomes
  - 8.2% ruin probability
  - Dominates TDF in retirement consumption levels (wealthier people can spend more)
- TDF
  - 16.9% ruin probability


### Terms of Simulation

- Lifecycle of US Couple (Male/Female)
  - Save during working years, consumes during retirement years
- Adopt a lifetime portfolio strategy
- Save portion of their monthly income at age 25
  - Model uncertain labor income using model of Guvenen, Karahan, Ozkan, and Song (20221)
- Retire at 65
- Receive Social Security
- Draw on savings using 4% rule
  - The 4% rule dictates that the couple withdraws 4% of their initial retirement wealth balance in the first year and then withdraws equal inflation-adjusted amounts in subsequent years. The 4% rule is ubiquitous in financial advice on retirement spending [see Anarkulova, Cederburg, O’Doherty, and Sias (2023) and cites therein].
- Simulated investment outcomes based on historical developed country asset-class returns and the couple's portfolio weights
- Longevity modeled on SSA mortality tables
- Couple leaves inheritance once both have died.
