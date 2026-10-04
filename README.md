# Portfolio Risk Analysis in Python

> **Status: in development.** This repository is being built step by step. The roadmap below shows what is done and what is coming next.

## Overview

This project is a Python-based risk analysis toolkit for equity portfolios. It answers the question: **"What risk does this portfolio actually carry?"**

It is the natural continuation of my [Portfolio Optimization & Asset Allocation Tool](https://github.com/ilona-gavoille/portfolio-optimization-excel) (Excel, Power Query, VBA, Solver), which answers the question *"Which portfolio should I build?"*. Together, the two projects cover two consecutive stages of the investment process:

```
Asset Allocation & Portfolio Construction   →   Risk Management
        (Excel project)                           (this project)
```

A second goal of this project is to build and demonstrate my Python skills for finance, in particular data collection, cleaning and manipulation with pandas.

## Scope

- **Universe:** the same 8 U.S. equities as the Excel project (AAPL, MSFT, JPM, XOM, JNJ, AMZN, KO, WMT)
- **Benchmark:** S&P 500 (SPY)
- **Data source:** historical daily prices via `yfinance`
- **Portfolios analyzed:** equally weighted portfolio, then the Maximum Sharpe and Minimum Variance portfolios from the Excel tool

## Roadmap

### Level 1: Foundations
- [ ] Project setup (environment, repository structure)
- [ ] Download, clean and cache historical price data
- [ ] Daily returns
- [ ] Annualized volatility
- [ ] Correlation matrix
- [ ] Maximum drawdown
- [ ] Beta versus the S&P 500
- [ ] First visualizations

### Level 2: Risk measures
- [ ] Value at Risk (VaR): historical method
- [ ] Conditional VaR (CVaR / Expected Shortfall)
- [ ] Rolling volatility
- [ ] Value at Risk (VaR): parametric method
- [ ] Risk contribution of each asset to the portfolio
- [ ] Stress tests

### Level 3: Advanced (planned next phase, time permitting)
- [ ] Monte Carlo VaR
- [ ] VaR backtesting
- [ ] Import portfolio weights from the Excel optimization tool
- [ ] Cross-check of Python results against the Excel model

## Risk metrics covered

| Metric | Question it answers |
|---|---|
| Volatility | How much does the portfolio fluctuate on average? |
| Maximum drawdown | What was the worst peak-to-trough loss? |
| Beta | How much does the portfolio move when the market moves? |
| Value at Risk (VaR) | What loss should not be exceeded with a given confidence level over a given horizon? |
| Conditional VaR (CVaR) | When the VaR is exceeded, what is the average loss? |
| Risk contribution | Which asset contributes the most to total portfolio risk? |

## Tech stack

- **Python**
- **pandas**: data manipulation and time series
- **numpy**: numerical and matrix computations
- **scipy**: statistical distributions
- **matplotlib / seaborn**: visualization
- **yfinance**: market data
- **pytest**: unit tests (planned)
- **Jupyter**: exploration and demonstration

## Planned project structure

```
portfolio-risk-analysis/
├── data/                # local data cache (not versioned)
├── src/
│   ├── data_loader.py   # download, clean, cache
│   ├── returns.py       # return calculations
│   ├── risk_metrics.py  # volatility, VaR, CVaR, drawdown
│   ├── portfolio.py     # weights and risk contributions
│   └── plots.py         # charts
├── notebooks/           # exploration and demonstration
├── tests/               # unit tests
├── main.py
├── requirements.txt
└── README.md
```

## Limitations (by design, for now)

- Equity-only universe of 8 predefined stocks
- Historical data used as a proxy for the future
- No transaction costs, taxes or market impact

## Related project

- [Portfolio Optimization & Asset Allocation Tool](LINK_TO_EXCEL_REPO): Markowitz framework, efficient frontier and Capital Allocation Line built with Excel, Power Query, VBA and Solver.

## Author

Ilona Gavoille: Master in Finance student, Paris-Saclay University.

---

*This README will be updated as the project progresses.*
