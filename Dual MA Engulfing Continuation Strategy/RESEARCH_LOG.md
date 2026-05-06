# Dual MA Engulfing Continuation Strategy - Research Log

## Strategy Overview
- **Type:** Original
- **Timeframe:** 15min
- **Asset Tested:** NQ1!
- **Backtest Period:** Feb 2 – May 6 2026

## Note on Originality
Core components (EMA/SMA trend filter, engulfing candle pattern) are individually public concepts. This strategy represents my own combinations, parameters and testing of these elements.

## Hypothesis
Price trading above both EMA 200 and SMA 200 indicates an established trend. A bullish or bearish engulfing candle signals trend continuation momentum.

## Entry Rules
- **Long:** Close > EMA(200) and Close > SMA(200) and bullish engulfing candle
- **Short:** Close < EMA(200) and Close < SMA(200) and bearish engulfing candle

## Exit Rules
- **Stop Loss:** ATR(14) × 1.7 from entry price
- **Take Profit:** ATR(14) × 1.7 from entry price
- **R:R Ratio:** 1:1 dynamic (adjusts with volatility)

## Simulation Parameters
- **Initial Capital:** $1,000,000
- **Position Size:** 2 contracts (fixed)
- **Commission:** $2.50 per contract
- **Slippage:** 2 ticks
_ADDITIONAL NOTE: use 50% margin while backtesting_
## Parameter Rationale
- **ATR Multiplier (1.7):** selected this specific value after testing multiple multiplier values which yield highest profits. This is aknowledged as an overfitting concern.
- **EMA/SMA Length (200):** helped identify the general trend over 200 candles, both the average trend as well as the recent trend over the 200 candle bars.
- **ATR Length (14):** Standard ATR period.


## Backtest Results
| Win Rate | Profit Factor | Sharpe Ratio | Max Drawdown | No. Trades | Backtest Period |
|----------|---------------|--------------|--------------|------------|-----------------|
|   56.60%   |     1.264     |  1.1       |   4.56%     |    523     | Feb 2 – May 6 2026 |

_results image at the end - after evaluation_
## Buy & Hold Comparison
| Strategy Return | Buy & Hold Return |
|-----------------|-------------------|
|      18.36%    |      5.42%        |

Outperformed buy and hold by 12.94% over the backtest period.

# EVALUATION
## What Worked
Positive 12.94% returns above the buy and hold return, Adequate sharpe ratio, decent profit factor, healthy win rate(good for a general 1:1 RR).
## Weaknesses
Took 500+ trades in a span of 3 months, which is very high. There could be a way to sieve out bad trades, and take lower trades. To increase win rate.
## Backtest Limitations
The backtest period is too small (3 months).
## Overfitting Concerns

Used a specific ATR value of 1.7 which could be a bias towards the data set tested out and not a reflection of different periods.

-------------
## Backtest Results - Image
<img width="3360" height="814" alt="image" src="https://github.com/user-attachments/assets/8478b193-d979-4045-85e0-973d35e99163" />

