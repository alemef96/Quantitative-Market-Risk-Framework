# Quantitative Market Risk Framework

## Overview
This repository hosts a quantitative framework for **Market Risk Management** and **Model Validation**, developed in **R**. 
The objective is to calculate regulatory risk metrics (Value at Risk) and perform independent validation (Backtesting) to assess model performance under stress.

Current focus: **Energy Sector volatility** (using XLE ETF as a proxy for commodity exposure) and S&P 500 benchmarking.

## Key Features 🚀
* **Data Ingestion:** Automated data extraction from Yahoo Finance using `quantmod`.
* **Risk Metrics:**
    * **Historical VaR (99%):** Non-parametric approach based on rolling windows.
    * **Expected Shortfall (ES):** Average of losses exceeding the VaR threshold (Tail Risk measurement).
* **Model Validation (Backtesting):**
    * Detection of **Breaches** (Exceptions) where actual loss exceeds VaR.
    * Visual inspection of model performance over time.

## Validation Results
The chart below illustrates the backtesting performance on the Energy Sector (XLE).
* **Blue Line:** Value at Risk (99% Threshold).
* **Orange Line:** Expected Shortfall (Average loss when things go wrong).
* **Red Dots:** Actual market crashes that broke the model limit.

![Market Risk Backtesting](output/market_risk_es_chart.png)

*Observation: The model shows a breach rate of 1.27% (vs 1.00% target), indicating slight underestimation of tail risk during volatility clusters (2020, 2022).*

## Technologies
* **Language:** R (v4.0+)
* **Libraries:** `quantmod`, `PerformanceAnalytics`, `ggplot2`, `dplyr`.

---
*Author: Alessandro D'Atria | Risk Management Professional*
