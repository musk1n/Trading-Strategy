# Trading Strategy Development and Backtesting

## Overview
This project analyzes S&P 500 (^SPX) data and implements multiple trading strategies. The project involves Exploratory Data Analysis (EDA) to uncover market patterns, and strategies based on technical indicators are developed and backtested to optimize risk-adjusted returns.

---

## Data Sources
- Stock: S&P 500 Index (^SPX)
- Data Period: January 1, 2022, to December 30, 2024
- Source: Retrieved using Yahoo Finance (yfinance) API.

---

## Exploratory Data Analysis (EDA)
The analysis focuses on price movements, volatility, returns, technical indicators, and option greeks to better understand stock and market behavior.
1. Price Trends and Daily Returns Analysis
  - Calculated as the percentage change in the closing price between consecutive days. Visualization of Time-series plots highlight daily returns and large positive or negative moves.
2. Volatility and Extreme Returns
  - Volatility: Daily returns fluctuate with a standard deviation of 0.00798 (0.8%), representing moderate price variability.
  - xtreme Returns: There were 6 extreme positive and 8 extreme negative return days, indicating asymmetric downside risk during market shocks.
3. Technical Indicators: The analysis employs several trend-following and momentum-based indicators
  - Simple Moving Averages (SMA): Detects long-term and short-term trends using 20-day and 50-day windows.
  - Exponential Moving Averages (EMA): Reacts more quickly to recent prices, aiding in early trend detection.
  - Bollinger Bands: Based on a rolling mean and volatility bands at ±2 standard deviations.
  - Relative Strength Index (RSI): Measures momentum and overbought/oversold conditions.
  - Moving Average Convergence Divergence (MACD): Tracks trend strength and direction using EMA differences.
  - Average Directional Index (ADX): Quantifies trend strength; values above 25 indicate a strong trend.
4. Option Greeks Analysis: Options data is evaluated using greeks, which measure sensitivity to various factors.
  - Delta (Δ): Measures the change in option price for a 1-unit change in the underlying asset's price.
  - Gamma (Γ): Tracks how Delta changes with price fluctuations of the underlying stock.
  - Vega (ν): Assesses sensitivity to changes in volatility, providing insight into market uncertainty.
  - Theta (Θ): Represents time decay, showing how the option's value decreases as expiration approaches.
  - Rho (ρ): Evaluates how changes in interest rates affect the option's value.

## Trading Strategies
1. SMA Crossover Strategy
  - What: Uses 20-day and 50-day Simple Moving Averages (SMA) to detect trend reversals.
  - Why: Crossovers provide reliable signals for momentum shifts.
  - Signal Generation:
    - Buy: 20-day SMA crosses above 50-day SMA (bullish crossover).
    - Sell: 20-day SMA crosses below 50-day SMA (bearish crossover).
   
2. Bollinger Bands Strategy
  - What: Utilizes Bollinger Bands to capture mean reversion based on volatility.
  - Why: Prices near the bands suggest potential overbought/oversold conditions.
  - Signal Generation:
    - Buy: Price falls below the lower band (oversold).
    - Sell: Price rises above the upper band (overbought).
   
3. RSI Strategy
  - What: Leverages the Relative Strength Index (RSI) to identify momentum shifts.
  - Why: RSI helps find overbought (> 70) and oversold (< 30) conditions.
  - Signal Generation:
    - Buy: RSI < 30.
    - Sell: RSI > 70.

4. Trend Reversal with EMA and Stochastic Oscillator
  - What: This strategy uses Exponential Moving Averages (EMAs) and the Stochastic Oscillator to detect trend reversals.
  - Why: Combining a trend indicator (EMA) and a momentum indicator (Stochastic Oscillator) enhances signal accuracy in volatile markets.
  - Signals:
    - Buy: The Fast EMA (e.g., 10-period EMA) crosses above the Slow EMA (e.g., 50-period EMA), and the Stochastic Oscillator crosses above 20 (oversold level).
    - Sell: The Fast EMA crosses below the Slow EMA, and the Stochastic Oscillator crosses below 80 (overbought level).
      
**Out of these, Strategy 2 gave best result!**

