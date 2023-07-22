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

## Brief Summary of Analysis

## Conclusions and Recommendations

## File Structure

## Sources
- Investopedia

## Learnings so far:
- Creating a database and planning the table structure is more difficult and mostly guess work at this point in my learning path
- So far it looks like the date values of stock price information didnt load properly into the database, still need to do additional discovery and eda on the information weve gathered so far
- Certain stocks have been de-listed from the original list of ~2500 stock tickers gathered from a kaggle dataset, will have to take that into account for final public dashboard.