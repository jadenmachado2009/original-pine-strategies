# Volume Spike Strategy - Research Log

## Strategy Overview
- **Type:** Original
- **Timeframe:** 5min
- **Asset Tested:** NQ1!
- **Backtest Period:** Apr 13 – May 12 2026

## Note on Originality
The volume spike concept is individually a known technical analysis tool. This strategy represents my own hypothesis, combination of conditions, and parameter choices — specifically the use of volume exhaustion as a mean reversion signal rather than a continuation signal.

## Hypothesis
After noticing that a spike in trading volume on NQ often showed a price movement correspondent to the opposing direction of the volume spike candle, leading me to test out the strategy myself on NQ.

## Entry Rules
- **Long:** Previous bar was a bearish volume spike (volume ≥ 2× 40-bar SMA, close < open) enter long on next bar open
- **Short:** Previous bar was a bullish volume spike (volume ≥ 2× 40-bar SMA, close > open) enter short on next bar open

## Exit Rules
- **Stop Loss:** ATR(14) × 1.6 against entry price
- **Take Profit:** ATR(14) × 1.6 in favour of entry price
- **R:R Ratio:** 1:1 dynamic (adjusts with volatility)

## Simulation Parameters
- **Initial Capital:** $1,000,000
- **Position Size:** 3 contracts (fixed)
- **Margin Used:** 50%
- **Commission:** $2.50 per contract
- **Slippage:** 2 ticks
_ADDITIONAL NOTE: use 50% margin while backtesting_

## Parameter Rationale
- **Volume Multiplier (2×):** A spike must be at least double the 40-bar average volume to qualify. Chosen to identify spikes over a 40 period average, 2x the average so that it does not pick a small spike.
- **Volume Lookback (40):** Wider lookback than standard 20-bar to reduce minor spikes.
- **ATR Multiplier (1.6):** Selected after initial testing. Acknowledged as a potential overfitting concern.
- **ATR Length (14):** Standard ATR period.

## Backtest Results
| Win Rate | Profit Factor | Sharpe Ratio | Max Drawdown | No. Trades | Backtest Period |
|----------|---------------|--------------|--------------|------------|-----------------|
|  51.76%   |    1.156     |     0.241   |    2.88%   |   454   |  Apr 13 – May 12 2026 |

_Results image at the end — after evaluation_

## Buy & Hold Comparison
| Strategy Return | Buy & Hold Return |
|-----------------|-------------------|
|  5.82%     |   8.30%      |

# EVALUATION

## What Worked
- even though the strategy return is slightly lower than the Buy & Hold Return, the return is still good considering NQ went on a bull run in that period.
- decent profit factor

## Weaknesses
- poor Sharpe ratio
- too many trades in a period of 1 month
  
## Backtest Limitations
- Backtest period is short

## Overfitting Concerns
- ATR multiplier of 1.6 was selected after testing multiple values, which introduces bias towards the tested dataset


---

## Backtest Results - Image

<img width="1188" height="848" alt="image" src="https://github.com/user-attachments/assets/b8e58c5f-eb6d-4980-94ca-32c3882332a0" />


_Green line indicates strategy return. Blue line indicates Buy & Hold return_
