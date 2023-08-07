# README!
# Portfolio Optimization with Python for Stocks, Bonds, and other Asset Classes

# Table of Contents:
- Background
- Introduction
- Problem Statement
- Data Dictionary
- Brief Summary of Analysis
- Conclusions and Recommendations
- File Structure
- Sources

## Background:
When I started my career in 2014 at Goldman Sachs as a middle office associate, I didn't much understand the world I was entering, and to some extent I still don't. For 7 years I operated between the institutional Sales and Trading Desk for U.S. Treasuries of GS working with clients on all forms of post execution trade risk. But from that seat is where my interest in financial instruments began, and how the players above and around me decided on which instruments, what quantity, and overall what direction they were looking to invest in. 

This project aims to better my understanding of the greater financial world, its instruments, and its techniques while building upon different skills in my toolbelt such as: Python, SQL, AWS RDS, Data Visualization/Dashboarding, and Time Series Analysis. Specific Tools and methods used in this project are (unedited):
- Python
- SQL
- AWS RDS
- Tableau
- Pandas
- PyPortfolioOpt
- Matplotlib/Seaborn
- PyTorch/Sklearn
- ...

## Introduction:
Portfolio Optimization is the practice of picking investment vehicles while optimizing for growth with minimal risk. It is often referred to as MPT or Modern Portfolio Theory which was pioneered by Harry Markowitz in his paper "Portfolio Selection" published in 1952 in the Journal of Finance. As read from Investopedia, "A key component of the MPT theory is diversification. Most investments are either high risk and high return or low risk and low return. Markowitz argued that investors could achieve their best results by choosing an optimal mix of the two based on an assessement of their individual tolerance to risk."

"Risk" as defined by Investopedia: "the chance that an outcome or investment's actual gains will differ from an expected outcome or return. Risk includes the possibility of losing some or all of an original investment."

"Return" as defined by Investopedia: "A return, also known as a financial return, in its simplest terms is the money made or lost on an investment over some period of time."

"Risk Return Tradeoff" as defined by Investopedia: "An informal rule that states that the potential return rises with an increase in risk. Risk-return tradeoff states that the potential return rises with an increase in risk."

Daily Decisions are made by investors (private citizens, corporations, banks, etc.) based on these high level principles. This project is designed to unearth and demystify some of the techniques used every day to make strategically sound investment decisions.

Version 1 will include only stocks to get the initial architecure up and running, once complete Version 2 will include bonds.


## Problem Statement
Use and verify different portfolio optimization strategies for different financial asset classes to determine their different strengths and weaknesses in performance of return of investment and risk. Current methods are:
- Mean Variance Optimization (MVO or "Harry Markowitz Method")
- Hiearchical Risk Parity (HRP)
- Mean Conditional Value At Risk (MCVAR)
Develop a pipeline that extracts financial instrument information, tansforms the data into a model ready state, models those instruments based on a selected method, visualize for the user all information available and modeled information and insights. Create a financial Dashboard using Tableau and host this information for public use for anyone interested in portfolio optimization and/or financial instruments in the market. Can risk be quantified?

## Data Dictionary
|Feature|Type|Table|Description|
|:---|:---:|:---:|---:|
|**ticker_id**|*Serial Primary Key*|*ticker*|Primary key for each stock ticker symbol in the ticker table|
|**ticker_symbol**|*object*|ticker|Abbreviation for a given Company's Stock, also referred to as a Ticker Symbol|
|**price_id**|*Serial Primary Key*|*price*|Primary key for each date and price of a particular stock|
|**date**|*Date*|*price*|Given date for a given price record for a given stock|
|**open**|*numeric/float64*|*price*|The price of the first trade for any listed stock of a given date|
|**high**|*numeric/float64*|*price*|The highest intraday price of a stock in the most recent (or current) trading session.|
|**low**|*numeric/float64*|*price*|The lowest intraday price of a stock in the most recent (or current) trading session.|
|**close**|*numeric/float64*|*price*|The price of the last transacttion in a security befor ethe market officially closes for normal trading.|
|**adj_close**|*numeric/float64*|*price*|The closing price after adjustments for all applicable splits and dividend distributions|
|**volume**|*bigint/int64*|*price*|The amount of a stock that changes hands over the course of a single trading day.|

## Database Structure
PostgreSQL Database

Table: ticker
|Feature|Type|
|:---|---:|
|**ticker_id**|*SERIAL PRIMARY KEY*|
|**ticker_symbol**|*VARCHAR(10) NOT NULL*|

Table: price
|Feature|Type|
|:---|---:|
|**price_id**|*SERIAL PRIMARY KEY*|
|**ticker_id**|*INT REFERENCES ticker(ticker_id)*|
|**date**|*DATE*|
|**open**|*NUMERIC*|
|**high**|*NUMERIC*|
|**low**|*NUMERIC*|
|**close**|*NUMERIC*|
|**adj_close**|*NUMERIC*|
|**volume**|*BIGINT*|

## Brief Summary of Analysis

## Conclusions and Recommendations

## File Structure

## Sources
- Investopedia

## Learnings so far:
- Creating a database and planning the table structure is more difficult and mostly guess work at this point in my learning path
- So far it looks like the date values of stock price information didnt load properly into the database, still need to do additional discovery and eda on the information weve gathered so far
- Certain stocks have been de-listed from the original list of ~2500 stock tickers gathered from a kaggle dataset, will have to take that into account for final public dashboard.

## Requirements Documentation:

In progress

### MVO Breakdown and Application:

- Step 1: Define the Asset Universe:
    - Start by selecting the assets (e.g., stocks, bonds, commodities) that you want to include in the portfolio. Each asset should have historical return data available.
- Step 2: Gather Asset Data:
    - Collect historical return data for each asset in your chosen universe over a specific time period. This data will be used to estimate expected returns and covariances.
- Step 3: Formulate the Optimization Problem:
    - The optimization problem is to find the weights (allocation) of each asset in the portfolio that maximize the portfolio's expected return for a given level of risk or minimize the risk for a given level of expected return.
- Step 4: Calculate Expected Return and Covariance:
    - Compute the expected return of each asset based on historical data.
    - Calculate the covariance matrix, which represents the relationships between asset returns.
- Step 5: Define the Objective Function:
    - The objective function represents the goal of the optimization. It is typically the portfolio's expected return or its risk (variance).
- Step 6: Set Constraints:
    - Constraints define the boundaries for the optimization. They can include the sum of weights equaling 1 (fully invested) and specifying minimum or maximum allocations for certain assets.
- Step 7: Solve the Optimization Problem:
    - Use mathematical optimization techniques, such as the Markowitz Mean-Variance Optimization model, to find the optimal allocation of assets that meets the defined objectives and constraints.
- Step 8: Construct the Efficient Frontier:
    - Calculate multiple portfolios with varying levels of risk, adjusting the weights of assets. Plot these portfolios on a graph to form the efficient frontier.
- Step 9: Select an Optimal Portfolio:
    - Investors can then select a portfolio from the efficient frontier based on their risk appetite and return expectations.


## Roadmap:
### Week 1: <br>
#### Data Cleaning and Preprocessing:
- Complete data cleaning and handling missing values, if any.
- Ensure consistency in data formats and resolve any data quality issues.
- Create Classes/Methods to check database data and update
- Capture more asset classes and market indicators
- Update Database to house more data
#### Data Exploration and Visualization:
- Continue the exploratory data analysis (EDA) to gain insights into the stock data.
- Create more visualizations to understand the relationships between different stock attributes.
- Identify potential outliers and decide on how to handle them.
#### Implement Core Functions:
- Start implementing the core functions for each of the portfolio optimization methods (MVO, HRP, MCVAR) in Python.
- Validate these functions on a subset of the data to ensure correctness.
#### Database Integration:
- Integrate the core functions with the PostgreSQL database to fetch required data efficiently.
- Optimize database queries to minimize response time.<br>
### Week 2:

#### Portfolio Optimization Implementations:
- Complete the implementation of Mean Variance Optimization (MVO) and test it with historical data.
- Implement Hierarchical Risk Parity (HRP) and Mean Conditional Value At Risk (MCVAR) as additional portfolio optimization methods.
#### Performance Evaluation:
- Develop metrics to evaluate the performance of each optimization method.
- Compare the returns, risks, and other relevant metrics of different portfolios generated by each method.
#### Frontend Development:
- Start building the user interface using Python libraries like Flask or Django.
- Create input forms to take user preferences such as risk tolerance, investment horizon, and constraints (if any).
#### Integration with Tableau:
- Explore Tableau's integration capabilities with Python.
- Connect the backend Python functions to Tableau for visualization and interactive reporting.<br>
### Week 3:

#### User Testing and Feedback:
- Conduct user testing on the tool with potential users or stakeholders.
- Gather feedback and make necessary improvements based on user suggestions.
#### Performance Optimization:
- Optimize the performance of the portfolio optimization algorithms, if needed, to reduce computation time.
#### Security and Data Privacy:
- Implement necessary security measures to protect sensitive data, especially if the tool is accessible online.
#### Documentation and Deployment:
- Document the codebase and provide clear instructions on how to use the tool.
- Deploy the application to a cloud server using AWS RDS for PostgreSQL and AWS EC2 or other suitable hosting options.

