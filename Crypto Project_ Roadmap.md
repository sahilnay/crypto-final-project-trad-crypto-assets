### ***Portfolios of Crypto vs Traditional Assets: Cointegration, Downside Beta, Tail Risk & Hedging***

---

1\. Asset Classes

Traditional: Equities (SPY, FF factors), Bonds (AGG, IEF), Real Estate (VNQ), Derivatives (CBOE put index, CDS index). Crypto: BTC-only, Top 5 majors (BTC, ETH, BNB, SOL, XRP), Top 5 \+ Meme (DOGE, SHIB, PEPE, etc.).

---

2\. Data Pipeline

* Collect & clean data from Yahoo/WRDS/FRED/CoinMarketCap  
* Align frequency \+ compute returns, vol, drawdowns  
* Build master dataset for analysis

---

3\. Benchmarking

* Compute performance for:  
  * 100% equity  
  * 70/30 equity–bond  
  * Equity/bond/REIT mix  
  * BTC-only & crypto baskets  
* Metrics: Sharpe, Sortino, drawdown, rolling correlations

---

4\. Cointegration & Dependencies

* Engle–Granger \+ Johansen tests  
* Rolling cointegration between crypto & traditional assets  
* Crypto-only internal cointegration  
* Crisis-period correlation analysis

---

5\. Downside & Tail Risk

* Downside beta  
* Tail dependence (quantile regressions)  
* CoVaR & Expected Shortfall  
* Drawdown correlation in key stress periods

---

6\. Portfolio Optimization

* MVO efficient frontier (0–50% crypto)  
* Risk parity portfolio  
* CVaR-constrained optimization  
* Regime-switching portfolios (high vs low vol regimes)

---

7\. Hedging Strategies

* Protective puts (S\&P, BTC proxies)  
* CDS overlays (CDX IG / HY)  
* Tail-risk overlays (VIX calls, long volatility)  
* Evaluate cost vs tail-risk mitigation

---

8\. Final Backtesting & Results

* Build 3 final portfolios:  
  1. Risk-adjusted mixed portfolio  
  2. Tail-controlled (CVaR) portfolio  
  3. Hedged crypto-enhanced portfolio  
* Compare performance vs benchmarks  
* Present results, charts, narrative

---

**Person 1 — Data Engineering Lead**

**Responsibilities**

* Collect all datasets (crypto, equities, bonds, REITs, FF factors, CDS, CBOE)  
* Clean, align, merge, and produce the master dataset  
* Compute basic return series \+ drawdowns

**Deliverables**

* `master_data.csv`  
* Data dictionary \+ notebook

---

**Person 2 — Traditional Assets Lead**

**Responsibilities**

* Build traditional benchmark portfolios (SPY, 70/30, REIT mix)  
* Compute Sharpe/Sortino/DD/rolling corr  
* Analyze Fama–French factor behavior

**Deliverables**

* Benchmark performance section \+ plots

---

**Person 3 — Crypto Assets Lead**

**Responsibilities**

* BTC-only, Top 5, Top 5 \+ Meme portfolios  
* Compute risk/return, drawdowns, rolling correlations  
* Provide crypto-only correlation \+ cointegration matrix

**Deliverables**

* Crypto portfolio charts \+ summary

---

**Person 4 — Statistical Modeling Lead**

**Responsibilities**

* Engle–Granger \+ Johansen cointegration tests  
* Downside beta \+ quantile regressions  
* CoVaR, ES, tail dependence metrics  
* Crisis behavior analysis

**Deliverables**

* Statistical results tables \+ heatmaps

---

**Person 5 — Portfolio Optimization & Hedging Lead**

**Responsibilities**

* MVO, CVaR optimization, risk parity  
* Construct hedged portfolios (puts, CDS, VIX overlays)  
* Run backtests and compute final performance

**Deliverables**

* 3 final portfolios \+ performance dashboards