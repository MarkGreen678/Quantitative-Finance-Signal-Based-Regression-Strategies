# Quantitative Finance Signal Based Regression Strategies
This project explores whether simple technical indicators can predict stock returns.   Using Python, Yahoo Finance data, and regression models, I build and back test trading signals — momentum, volatility, and RSI — at both daily and monthly horizons.

---

## Contents
- **README.md** — Project documentation, methodology, results, and key takeaways  
- **Quant_Finance_project_1.ipynb** — Full Jupyter Notebook with data collection, modeling, backtesting, and figures.  

---

## Project Overview
- **Goal:** Test if basic trading signals (momentum, volatility, RSI) have predictive power for SPY returns.  
- **Data:** SPY (S&P 500 ETF) daily price history, sourced from Yahoo Finance via `yfinance`.  
- **Methods:**  
  - Ordinary Least Squares (OLS) regression models  
  - Signals converted into trading strategies (long/short, long-only)  
  - Backtests against a simple buy & hold benchmark  

---

## Features & Models
- **Momentum:** Percentage price change over a lookback window (5-day for daily, 3-month for monthly).  
- **Volatility:** Rolling standard deviation of returns (20-day daily, 60-day aggregated for monthly).  
- **RSI (Relative Strength Index):** Ratio of average gains to losses, lagged to avoid lookahead bias.  
- **Models:** Linear regression (OLS) to test explanatory power of these signals.  

---

## Key Results

### Daily Horizon
- R² close to **zero** — daily returns are extremely noisy.  
- Momentum showed weak **mean reversion**, but not statistically significant.  
- Strategies built on daily predictions **underperformed** buy & hold.  

### Monthly Horizon
- R² improved to ~**10%**, with volatility showing some predictive power.  
- Long-only strategy tracked buy & hold more closely, but still failed to outperform.  
- Long/short strategy suffered from **shorting bias** in an upward-trending market.  

---

## Backtest Performance
- **Buy & Hold (SPY):** Strongest cumulative return.  
- **Strategy 1 (long/short):** Underperformed due to frequent shorts in a bull market.  
- **Strategy 2 (long-only):** Reduced downside risk, but added little alpha vs. buy & hold.  

---

## Take-aways
- **Daily predictions are unreliable** due to market noise.  
- **Longer horizons** (monthly) provide slightly better signal, but still weak.  
- **Buy & Hold is difficult to beat** — especially for broad indices like SPY.  
- Improvements require:
  - More diverse features (fundamental, macro, cross-asset signals)  
  - Nonlinear models (tree-based methods, machine learning, Bayesian approaches)  
  - Portfolio-level strategies and risk management  

---

## Tools & Libraries
- `numpy`, `pandas` — data manipulation  
- `yfinance` — Yahoo Finance API for price data  
- `matplotlib` — plotting results  
- `statsmodels` — regression modeling  

---

## Conclusion
This project demonstrates the challenges of predicting stock returns using simple technical signals.  
While signals like momentum, volatility, and RSI are widely used, their predictive power is limited on SPY — especially at the daily level.  
The framework, however, provides a **foundation for experimenting with more advanced models and features** in quantitative finance research.  

---

## Next Steps
- Extend feature set with **fundamental and macroeconomic data**  
- Explore **Bayesian approaches** (e.g., Bayesian regression, probabilistic modeling with priors)
- Backtest across multiple assets and markets.

---

