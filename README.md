# Portfolio Diversification and Markowitz Optimization in Vietnam Stock Market

## Overview

This project analyzes the impact of portfolio diversification on investment risk and return in the Vietnamese stock market. Using Modern Portfolio Theory (Markowitz, 1952), the study investigates how stock correlations, portfolio size, and asset allocation affect portfolio performance.

The project is implemented in Python and uses historical stock data from HOSE-listed companies collected from CafeF.

## Objectives

* Analyze correlations among stocks from different industries.
* Compare the performance of high-correlation and low-correlation portfolios.
* Evaluate the impact of increasing portfolio size on risk reduction.
* Construct optimal portfolios using Markowitz Mean-Variance Optimization.
* Backtest portfolio performance on out-of-sample data.

## Dataset

### Source

* CafeF Historical Stock Data

### Period

* 01/01/2021 – 01/06/2026

### Sample Stocks

The dataset includes 18 stocks from 9 sectors:

| Sector             | Stocks   |
| ------------------ | -------- |
| Banking            | VCB, TCB |
| Securities         | SSI, HCM |
| Real Estate        | VHM, NLG |
| Technology         | FPT, CMG |
| Retail             | MWG, PNJ |
| Steel              | HPG, HSG |
| Energy & Utilities | REE, POW |
| Food & Beverage    | VNM, MSN |
| Logistics          | GMD, VSC |

## Methodology

### 1. Data Preparation

* Data cleaning and preprocessing
* Missing value handling using Forward Fill
* Daily return calculation

### 2. Correlation Analysis

* Pearson correlation matrix
* Correlation heatmap visualization
* Identification of highest and lowest correlated stock pairs

### 3. Portfolio Comparison by Correlation Level

Two equally weighted portfolios are constructed:

**High Correlation Portfolio**

* HCM
* SSI
* HPG
* HSG

**Low Correlation Portfolio**

* VCB
* FPT
* MWG
* GMD

Performance metrics:

* Annualized Return
* Annualized Risk
* Sharpe Ratio

### 4. Diversification Simulation

Monte Carlo simulation is performed to examine how portfolio risk changes as the number of stocks increases from 1 to 18.

### 5. Markowitz Portfolio Optimization

Two optimal portfolios are generated:

* Maximum Sharpe Ratio Portfolio
* Minimum Variance Portfolio

Optimization is solved using:

```python
scipy.optimize.minimize(method="SLSQP")
```

### 6. Backtesting

Out-of-sample testing is conducted using 2026 data to evaluate the real-world performance of:

* Max Sharpe Portfolio
* Minimum Variance Portfolio
* Equal Weight Portfolio

## Key Findings

### Correlation Effect

* Stocks within the same industry generally exhibit higher correlations.
* Low-correlation portfolios achieve significantly lower risk while maintaining competitive returns.
* Sharpe Ratio improves substantially when diversification is based on low-correlated assets.

### Diversification Effect

* Portfolio risk decreases rapidly as the number of stocks increases.
* Most diversification benefits are achieved with approximately 10 stocks.
* Beyond this point, additional risk reduction becomes marginal.

### Portfolio Optimization

#### Maximum Sharpe Portfolio

Concentrated mainly in:

* FPT (71.83%)
* GMD (10.41%)
* VHM (7.20%)
* REE (5.66%)
* TCB (4.91%)

#### Minimum Variance Portfolio

Focused on defensive assets:

* VNM (34.04%)
* VCB (28.48%)
* PNJ (8.17%)
* REE (7.95%)
* FPT (7.08%)

### Backtest Results (2026)

| Portfolio    | Annual Return | Annual Risk | Sharpe Ratio |
| ------------ | ------------- | ----------- | ------------ |
| Max Sharpe   | -30.62%       | 30.81%      | -1.09        |
| Min Variance | 4.45%         | 24.52%      | 0.06         |
| Equal Weight | 4.17%         | 23.20%      | 0.05         |

The Minimum Variance portfolio demonstrated the most stable performance during volatile market conditions.

## Technologies Used

* Python
* NumPy
* Pandas
* Matplotlib
* Seaborn
* SciPy

## Project Structure

```text
├── data/
│   └── CafeF.HSX.Upto01.06.2026.csv
├── notebooks/
│   └── portfolio_analysis.ipynb
├── figures/
│   ├── correlation_heatmap.png
│   ├── diversification_risk.png
│   └── efficient_frontier.png
├── report/
│   └── Final_Report.pdf
└── README.md
```

## Conclusion

The results support the core principles of Modern Portfolio Theory. Diversification across low-correlated assets significantly reduces portfolio risk, while Markowitz optimization provides a systematic framework for portfolio construction. In practice, the Minimum Variance strategy showed greater robustness than the Maximum Sharpe strategy during the 2026 out-of-sample period.

## Author

* Nguyen Quoc Trong
* Student at University of Economics Ho Chi Minh City (UEH)
