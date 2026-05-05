# iFVG NY Session Strategy - Research Log

## Strategy Overview
- **Type:** Original
- **Timeframe:** 15min
- **Asset Tested:** NQ1!
- **Backtest Period:** Feb 2 – May 5 2026

## Note on Originality
FVG and iFVG concepts originate from SMC/ICT trading methodology and are publicly known. The specific implementation — including session-gated entry logic, inverse FVG boundary as stop loss placement, and variable R:R input — represents original code and strategy structure developed independently.

## Hypothesis
When price returns to and crosses back through a Fair Value Gap boundary (creating an Inverse FVG), it signals a potential continuation move. 
Filtering entries to the NY session concentrates trades during peak liquidity and reduces noise.

## Entry Rules
- **Long:** enters off of a bull iFVG in the ny session 
- **Short:** enters off of a bear iFVG in the ny session 
- **Session Filter:** 09:30 – 11:00 EST (New York_AM)

## Exit Rules
- *Long Stop Loss:** bearFVG bottom boundary
- **Short Stop Loss:** bullFVG top boundary
- **Take Profit:** R:R ratio applied from entry (default 1:1, adjustable)

## Parameter Rationale
- **Session (09:30–11:00):** 
- **Box Length (20):** 
- **R:R (1.0):** 

## Backtest Results
| Win Rate | Profit Factor | Sharpe Ratio | Max Drawdown | No. Trades | Backtest Period |
|----------|---------------|--------------|--------------|------------|-----------------|
|          |               |              |              |            |                 |

![Backtest Results](backtest_screenshot.png)

## Buy & Hold Comparison
| Strategy Return | Buy & Hold Return |
|-----------------|-------------------|
|                 |                   |

## What Worked

## Weaknesses / What Failed

## Backtest Limitations

## Overfitting Concerns

## Next Steps / Potential v2 Changes
