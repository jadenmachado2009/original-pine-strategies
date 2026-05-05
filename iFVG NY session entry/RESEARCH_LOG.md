# iFVG NY session entry - Research Log

## Strategy Overview
- **Type:** Original
- **Timeframe:** 15min
- **Asset Tested:** NQ1!
- **Backtest Period:** Feb 2 – May 5 2026

## Note on Originality
FVG and iFVG concepts originate from SMC/ICT trading methodology and are publicly known. The specific entry combination  -- stop loss placement, entry logic, variable RR input -- represents original code and strategy structure development.

## Hypothesis
When a FVG is disrespected (iFVG) it signals a possible continuation in the corresponding direction. NY_AM session due to high volatility during that time period.

## Entry Rules
- **Long:** enters off of a bull iFVG in the ny session 
- **Short:** enters off of a bear iFVG in the ny session 
- **Session Filter:** 09:30 – 11:00 EST (New York_AM)

## Exit Rules
- *Long Stop Loss:** bearFVG bottom boundary
- **Short Stop Loss:** bullFVG top boundary
- **Take Profit:** R:R ratio applied from entry (default 1:2, adjustable)

## Parameter Rationale
- **Session (09:30–11:00):** High volatility session. Therefore, price movements will be bigger.
- **R:R (2.0):** Adjustable, not necessarily 1:2 RR

## Backtest Results
| Win Rate | Profit Factor | Sharpe Ratio | Max Drawdown | No. Trades | Backtest Period |
|----------|---------------|--------------|--------------|------------|-----------------|
|   45.59   |    1.437      |    0.841    |    1.44     |   136    |  Feb 2 – May 5 2026 |

_results image at the end - after evaluation_

## Buy & Hold Comparison
| Strategy Return | Buy & Hold Return |
|-----------------|-------------------|
|     4.14%      |       3.66%     |

## What Worked

## Weaknesses / What Failed

## Backtest Limitations

## Overfitting Concerns

## Next Steps / Potential v2 Changes
