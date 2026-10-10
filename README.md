# Portfolio Risk Analysis in Python

> **Status: in development.** This repository is being built step by step. The roadmap below shows what is done and what is coming next.

## Overview

This project is a Python toolkit to measure, explain and stress-test the risk of an equity portfolio. It answers one question: **"What risk does this portfolio carry, how much can it lose, and what happens in a crisis?"**

It is also a learning project: each risk concept (volatility, VaR, Expected Shortfall, Monte Carlo simulation, stress testing...) is documented in a short theory note, then implemented from scratch in Python and interpreted on real market data.

## Scope

- **Universe:** 8 U.S. large-cap equities across sectors (AAPL, MSFT, JPM, XOM, JNJ, AMZN, KO, WMT)
- **Benchmark:** S&P 500 (SPY)
- **Data:** historical daily prices via `yfinance`, with a CSV snapshot included so the project runs without any API key
- **Portfolios analyzed:** an equally weighted portfolio and a custom-weighted portfolio, to compare their risk profiles

## Roadmap

### 1. Data and return statistics [Completed]
- [x] Download, clean and store historical price data
- [x] Simple and log returns
- [x] Annualized volatility, covariance and correlation matrix
- [x] Drawdown and maximum drawdown
- [x] Beta versus the S&P 500, Sharpe and Sortino ratios

### 2. Value at Risk and Expected Shortfall
- [ ] Historical VaR
- [ ] Parametric (variance-covariance) VaR
- [ ] Monte Carlo VaR
- [ ] Conditional VaR (Expected Shortfall)
- [ ] Comparison of the three methods and their limitations
- [ ] VaR backtesting (exceedance count, Kupiec test)

### 3. Risk decomposition and stress testing
- [ ] Risk contribution of each asset to portfolio risk
- [ ] Rolling volatility
- [ ] Historical stress tests (2008 financial crisis, 2020 Covid crash)
- [ ] Hypothetical scenarios (e.g. equity market shock, sector-specific shock)
- [ ] Final summary report

## Risk metrics covered

| Metric | Question it answers |
|---|---|
| Volatility | How much does the portfolio fluctuate on average? |
| Maximum drawdown | What was the worst peak-to-trough loss? |
| Beta | How much does the portfolio move when the market moves? |
| Value at Risk (VaR) | What loss should not be exceeded with a given confidence level over a given horizon? |
| Expected Shortfall (CVaR) | When the VaR is exceeded, what is the average loss? |
| Backtesting | Is the VaR model reliable in practice? |
| Risk contribution | Which asset contributes the most to total portfolio risk? |
| Stress tests | How much would the portfolio lose in an extreme scenario? |

## Tech stack

- **Python**
- **pandas**: data manipulation and time series
- **numpy**: numerical computations and Monte Carlo simulation
- **scipy**: statistical distributions and tests
- **matplotlib**: visualization
- **yfinance**: market data
- **Jupyter**: exploration and demonstration

## Project structure

```
├── README.md
├── requirements.txt
├── data/
│   └── prices.csv
└── notebooks/
    ├── 01_data.ipynb
    └── 02_returns.ipynb
```

## Limitations
- Equity-only universe of 8 predefined stocks
- Historical data used as a proxy for the future
- Normality assumption in parametric VaR, which underestimates tail risk
- No transaction costs, taxes or market impact

*This README will be updated as the project progresses.*
