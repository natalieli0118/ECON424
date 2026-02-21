# ETF Portfolio Optimization & Risk Analysis

## Overview

This project applies Modern Portfolio Theory (MPT) to construct and evaluate optimal ETF portfolios.

Using six diversified ETFs across equity, sector, and commodity markets, I analyze risk-return tradeoffs, portfolio efficiency, diversification effects, and downside risk using Value-at-Risk (VaR).

The project compares equal-weight allocation with optimized portfolios under both short-selling and no-short-selling constraints.

---

## Assets Included

The portfolio consists of six ETFs representing major asset classes:

- **ITOT** – Total U.S. Stock Market
- **QQQ** – Nasdaq-100 (Technology)
- **XLE** – Energy Sector
- **VNQ** – Real Estate
- **IWM** – Small Cap Stocks
- **AAAU** – Physical Gold ETF

**Sample Period:** September 2018 – March 2025  
**Frequency:** Monthly returns

---

## Research Questions

- Does diversification across sectors and asset classes reduce risk?
- How much improvement does portfolio optimization provide over naive equal weighting?
- What is the impact of short-selling on portfolio efficiency?
- How does tail risk compare across assets and optimized portfolios?

---

## Methodology

### 1. Descriptive Statistics
- Return distributions
- Q-Q plots
- Annualized returns & volatility
- Growth of $1 investment

### 2. Correlation & Diversification Analysis
- Correlation matrix
- Risk contribution decomposition
- Mean-variance risk-return comparison

### 3. Portfolio Construction

**Portfolios Evaluated:**

- Equal-Weighted Portfolio
- Global Minimum Variance Portfolio (GMVP)
- Tangency Portfolio (Maximum Sharpe Ratio)
- Efficient Frontier
- Capital Market Line

Both:
- With short-selling
- Without short-selling

Optimization performed using quadratic programming under mean-variance framework.

---

## Key Results

### Diversification Benefits

- Equity ETFs exhibit high correlations (0.71–0.92).
- Gold (AAAU) shows low correlation with equities.
- Including gold significantly reduces portfolio volatility.

---

### Equal Allocation ≠ Equal Risk

In the equal-weighted portfolio (16.67% each):

- XLE contributes disproportionately high portfolio risk.
- AAAU contributes minimal risk.

Capital allocation does not equal risk contribution.

---

### Global Minimum Variance Portfolio (GMVP)

| Portfolio | Annual Return | Annual Volatility | Sharpe Ratio |
|------------|--------------|------------------|--------------|
| Equal-Weight | 12.5% | 17.4% | 0.69 |
| GMVP | 14.2% | 11.5% | 1.06 |

The GMVP achieved:

- Higher expected return
- Lower volatility
- Superior risk-adjusted performance

This demonstrates that optimization can simultaneously improve return and reduce risk.

---

### Tangency Portfolio (Maximum Sharpe Ratio)

- Annual Return: 22.3%
- Annual Volatility: 14.9%
- Sharpe Ratio: 1.37

The tangency portfolio delivered the highest return per unit of risk among all strategies.

---

### Value-at-Risk (VaR)

For a $100,000 one-month investment:

- XLE exhibits the highest tail risk.
- GMVP has the lowest VaR among all portfolios.
- Allowing short-selling slightly reduces downside risk.

---

## Mathematical Framework

### Portfolio Variance

$$
\sigma_p^2 = w^\top \Sigma w
$$

---

### Sharpe Ratio

$$
S = \frac{E[R_p] - R_f}{\sigma_p}
$$

---

### Global Minimum Variance Problem

$$
\min_{w} \quad w^\top \Sigma w
$$

subject to:

$$
\sum_{i=1}^{n} w_i = 1
$$

---

### Tangency Portfolio (Maximum Sharpe Ratio)

$$
\max_{w} \quad \frac{E[R_p] - R_f}{\sigma_p}
$$

---

## Tools & Libraries

- R
- IntroCompFinR
- PerformanceAnalytics
- quadprog
- ggplot2
- Modern Portfolio Theory (MPT)

---

## Key Takeaways

- Optimization meaningfully improves portfolio efficiency.
- Gold provides strong diversification benefits.
- Risk budgeting is as important as capital allocation.
- Short-selling increases efficiency but introduces practical constraints.
- The tangency portfolio offers the best risk-adjusted return.
