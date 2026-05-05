# Bullish Engulfing Trend Continuation - Research Log

## Strategy Overview
- **Type:** Original
- **Timeframe:** 15min
- **Asset Tested:** NQ1!
- **Backtest Period:** Feb 2 – May 5 2026

## Note on Originality
Core components (EMA/SMA trend filter, engulfing candle pattern) are 
individually public concepts. This strategy represents my own combinations, parameters and testing of these elements.

## Hypothesis
Price trading above both EMA 200 and SMA 200 indicates an established 
trend. A bullish or bearish engulfing candle signals 
trend continuation momentum.

## Entry Rules
- **Long:** Close > EMA(200) and Close > SMA(200) and bullish engulfing candle
- **Short:** Close < EMA(200) and Close < SMA(200) and bearish engulfing candle

## Exit Rules
- **Stop Loss:** ATR(14) × 1.7 from entry price
- **Take Profit:** ATR(14) × 1.7 from entry price
- **R:R Ratio:** 1:1 dynamic (adjusts with volatility)

## Parameter Rationale
- **ATR Multiplier (1.7):** selected this specific value after testing multiple multiplier values which yield highest profits. This is aknowledged as an overfitting concern.
- **EMA/SMA Length (200):** helped identify the general trend over 200 candles, both the average trend as well as the recent trend over the 200 candle bars.
- **ATR Length (14):** used the general ATR value

## Backtest Results

| Win Rate | Profit Factor | Sharpe Ratio | Max Drawdown | No. Trades | Backtest Period |
|----------|---------------|--------------|--------------|------------|-----------------|
|   56.59%   |     1.287      |  1.007       |    2.20%    |    516     | Feb 2 – May 5 2026 |

   _results image at the end - after evaluation_
## Buy & Hold Comparison
| Strategy Return | Buy & Hold Return |
|-----------------|-------------------|
| 9.74%           | 4.41%             |


This indicates a positive 5.33% from the Buy & Hold return


# EVALUATION
## What Worked
Positive 5.33% returns above the buy and hold return. Adequate sharpe ratio, decent profit factor, healthy win rate.
## Weaknesses
Took 500+ trades in a span of 3 months, which is very high. There could be a way to sieve out bad trades, and take lower trades. To increase win rate.

## Backtest Limitations
The backtest period is too small (3 months), and the code does not factor in slippage and comissions which could slightly lower the returns.
## Overfitting Concerns
Used a specific ATR value of 1.7 which could be a bias towards the data set i tested out and not a reflection of different periods. 

-------------

## Backtest Results - Image
<img width="2736" height="814" alt="image" src="https://github.com/user-attachments/assets/f6bb9d16-e2f7-4578-a8d2-4f608fbb694b" />
