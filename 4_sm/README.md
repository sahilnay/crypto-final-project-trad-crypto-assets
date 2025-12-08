# Statistical Modeling Analysis (Person 4)

## Overview
This directory contains comprehensive statistical analysis comparing traditional and crypto portfolios, focusing on:
1. **Cointegration Analysis** - Long-run equilibrium relationships
2. **Downside Beta & Tail Dependence** - Asymmetric risk during market stress
3. **CoVaR & Expected Shortfall** - Systemic risk and tail risk measures
4. **Crisis Period Analysis** - Behavior during market crashes
5. **Summary & Interpretation** - Key insights and recommendations

## Files

### Analysis Scripts
- **`statistical_modeling.py`** - Complete Python script with all analyses
- **`statistical_modeling.ipynb`** - Jupyter notebook (runs the Python script)

### Outputs

#### Tables (`outputs/tables/`)
- `cointegration_eg_portfolios.csv` - Engle-Granger pairwise cointegration results
- `cointegration_johansen.csv` - Johansen multivariate cointegration results
- `downside_beta_summary.csv` - Full vs downside beta comparison
- `quantile_regression_spy.csv` - Quantile regression vs equity market
- `quantile_regression_btc.csv` - Quantile regression vs crypto market
- `expected_shortfall.csv` - VaR and ES for all portfolios
- `covar_summary.csv` - Conditional Value at Risk analysis
- `crisis_correlations.csv` - Correlation changes during crises
- `crisis_performance.csv` - Portfolio performance during stress periods
- `summary_insights.csv` - Key statistical findings
- `recommendations.txt` - Portfolio construction recommendations

#### Figures (`outputs/figures/`)
- `rolling_cointegration_*.png` - Time-varying cointegration (3 key pairs)
- `downside_beta_comparison.png` - Beta comparison across regimes
- `quantile_betas_vs_spy.png` - Quantile betas vs equity market
- `quantile_betas_vs_btc.png` - Quantile betas vs crypto market
- `covar_heatmap.png` - Systemic risk spillover visualization
- `es_comparison.png` - Expected Shortfall comparison
- `corr_crisis_vs_normal.png` - Correlation regime comparison
- `crisis_timeline_*.png` - Individual crisis episode analysis

## Data Sources

### Input Data
- Traditional portfolio returns: `../2_trad_port/outputs/tables/portfolio_returns_monthly.csv`
  - Equity_100, 70_30_Equity_AGG, 60_40_Equity_AGG, Diversified_40_30_10_10_10, PutWrite_100
- Crypto portfolio returns: `../3_crypto_port/outputs/tables/portfolio_returns_monthly.csv`
  - BTC_only, BTC_SOL_ETH, MarketCap_All
- Historical prices: `../1_data/historical_prices.csv`
- Stress episodes: From existing analysis outputs

## Running the Analysis

### Option 1: Run Python Script
```bash
cd 4_sm
python statistical_modeling.py
```

### Option 2: Run Jupyter Notebook
```bash
cd 4_sm
jupyter notebook statistical_modeling.ipynb
```

Then execute the cell containing `%run statistical_modeling.py`

### Option 3: Interactive Analysis
Open `statistical_modeling.ipynb` and run cells interactively to explore specific sections.

## Key Findings

### 1. Cointegration
- Limited long-run equilibrium relationships between traditional and crypto portfolios
- Most pairs fail cointegration tests at 5% significance
- Suggests crypto can provide diversification, but relationship is time-varying

### 2. Downside Beta
- Crypto portfolios show higher beta ratios during market downturns
- Beta asymmetry indicates amplified tail risk
- Cross-benchmark analysis reveals differential behavior vs equity vs crypto markets

### 3. Tail Risk (CoVaR & ES)
- Expected Shortfall significantly higher for crypto portfolios
- Meaningful systemic risk spillovers between asset classes
- Delta CoVaR indicates conditional tail risk dependencies

### 4. Crisis Behavior
- Correlations spike dramatically during stress periods
- Traditional diversification benefits erode in crises
- Crypto portfolios experience severe drawdowns during both traditional and crypto-specific crises

### 5. Recommendations for Portfolio Optimization (Person 5)
1. **Allocation Limits**: Consider 0-20% crypto allocation due to tail risk
2. **Risk Constraints**: Use CVaR constraints in optimization
3. **Regime Awareness**: Implement regime-switching strategies
4. **Hedging**: Traditional tail hedges (puts, CDS) may be more effective than crypto diversification
5. **Dynamic Rebalancing**: Account for time-varying correlations and cointegration

## Dependencies

### Required Python Packages
```
pandas
numpy
matplotlib
seaborn
statsmodels
scipy
```

### Custom Modules
- `../cmds/portfolio_management_helper.py` - Portfolio analysis utilities

## Methodology

### Cointegration Tests
- **ADF Test**: Augmented Dickey-Fuller for stationarity
- **Engle-Granger**: Two-step cointegration for all trad-crypto pairs (15 pairs)
- **Johansen**: Multivariate cointegration for combined, traditional-only, and crypto-only systems
- **Rolling Analysis**: 1-year rolling window for key pairs

### Downside Risk
- **Downside Beta**: Beta conditional on benchmark below mean
- **Quantile Regression**: Betas at 5%, 25%, 50%, 75%, 95% quantiles
- Analysis vs both SPY (Equity_100) and BTC benchmarks

### Tail Risk Measures
- **Historical VaR/ES**: Non-parametric 5% and 1% levels
- **Parametric VaR/ES**: Normal distribution assumption
- **CoVaR**: VaR conditional on benchmark in distress
- **Delta CoVaR**: Change in VaR during benchmark stress

### Crisis Analysis
- **Episode Identification**: From worst drawdown analysis (Persons 2 & 3)
- **Regime Comparison**: Correlation matrices in crisis vs normal periods
- **Performance Tracking**: Cumulative returns during each crisis episode

## Notes

- All analysis uses monthly rebalanced portfolio returns for consistency
- Crisis periods defined by worst drawdown episodes from traditional and crypto analyses
- Statistical significance generally tested at 5% level
- All visualizations saved at 300 DPI for publication quality

## Contact & Collaboration

This analysis supports Person 5 (Portfolio Optimization & Hedging Lead) with:
- Statistical evidence for portfolio construction constraints
- Risk factor identification for optimization
- Crisis behavior insights for hedging strategy design

---

**Date Created**: December 2025  
**Analysis Period**: Varies by portfolio (generally 2017-2025)  
**Project**: Portfolios of Crypto vs Traditional Assets

