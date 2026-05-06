# iFVG NY session entry - Research Log

## Strategy Overview
- **Type:** Original
- **Timeframe:** 15min
- **Asset Tested:** NQ1!
- **Backtest Period:** Feb 2 – May 6 2026

## Note on Originality
FVG and iFVG concepts originate from SMC/ICT trading methodology and are publicly known. The specific entry combination  (stop loss placement, entry logic, variable RR input) represents original code and strategy structure development.

## Hypothesis
When a FVG is disrespected (iFVG) it signals a possible continuation in the corresponding direction. NY_AM session due to high volatility during that time period.

## Entry Rules
- **Long:** enters off of a bull iFVG in the ny session 
- **Short:** enters off of a bear iFVG in the ny session 
- **Session Filter:** 09:30 – 11:00 EST (New York_AM)

## Exit Rules
- **Long Stop Loss:** bearFVG bottom boundary
- **Short Stop Loss:** bullFVG top boundary
- **Take Profit:** R:R ratio applied from entry (default 1:2, adjustable)

## Parameter Rationale
- **Session (09:30–11:00):** High volatility session. Therefore, price movements will be bigger.
- **R:R (2.0):** Adjustable, not necessarily 1:2 RR

## Backtest Results
| Win Rate | Profit Factor | Sharpe Ratio | Max Drawdown | No. Trades | Backtest Period |
|----------|---------------|--------------|--------------|------------|-----------------|
|   45.99%   |    1.406      |    0.878    |    2.96%    |   137    |  Feb 2 – May 6 2026 |

_results image at the end - after evaluation_

## Buy & Hold Comparison
| Strategy Return | Buy & Hold Return |
|-----------------|-------------------|
|     7.65%     |       4.40%       |

This indicates a positive 0.47% from the Buy & Hold return

# EVALUATION
## What Worked
Positive returns above the buy and hold return, 46% win rate with a 1:2RR, good profit factor.
## Weaknesses
Moderate Sharpe ratio
## Backtest Limitations
The backtest period is too small (3 months).

## Overfitting Concerns
The reason of positive trading returns could be due to a sample size chosen that is favourabe towards the strategy and not a reflection of market periods going further back.

## Backtest Results - Image
<img width="3360" height="814" alt="image" src="https://github.com/user-attachments/assets/666dea16-5484-4a9f-b6bb-6c7d2de656ee" />


