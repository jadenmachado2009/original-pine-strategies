# Momentum Fade - Research Log
 
## Strategy Overview
- **Strategy Name:** Momentum Fade
- **Category:** Original
- **Timeframe:** 5min
- **Asset Tested:** NQ1!
- **Backtest Period:** May 4 – May 30, 2026

## Hypothesis
Noticed that when candles kept moving in the same direction but kept getting smaller, 
price would often reverse shortly after. Built a strategy to fade that pattern.
 
## Note on Originality
Candle body compression as an exhaustion signal is not a publicly documented strategy.
The specific entry logic — consecutive same-direction candles with strictly shrinking bodies used as a mean reversion trigger — represents original strategy design and is not derived from any known public methodology.

## Core Logic
3 consecutive bearish candles with each body smaller than the previous → Long (fade the down move)
3 consecutive bullish candles with each body smaller than the previous → Short (fade the up move)
 
## Entry Rules
- **Long:** 3 consecutive bearish candles, each body strictly smaller than the prior. Enter market on signal bar close.
- **Short:** 3 consecutive bullish candles, each body strictly smaller than the prior. Enter market on signal bar close.
- **Session Filter:** None applied in v1 — all hours tested

## Exit Rules
- **Stop Loss:** Entry price ± (ATR × 2.5)
- **Take Profit:** Entry price ± (ATR × 2.5)
- **RR:** 1:1 (same multiplier for SL and TP in v1)
  
## Simulation Parameters
- **Initial Capital:** $1,000,000
- **Position Size:** 3 contracts (fixed)
- **Commission:** $2.50 per contract
- **Slippage:** 2 ticks
  _ADDITIONAL NOTE: use 50% margin while backtesting_
  
## Parameter Rationale
- **ATR Length (14):** Standard volatility measure. Captures recent NQ session range adequately on 5m.
- **3 Candle Sequence:** Minimum meaningful sequence. Fewer candles = too much noise. More = too few trades to evaluate.
- 
## Backtest Results
 
## Backtest Results
| Win Rate | Profit Factor | Shaarpe Ratio | Max Drawdown | No. Trades | Backtest Period |
|----------|---------------|--------------|--------------|------------|-----------------|
|    63.01%  |   1.694  |      0.692     |     2.75%    |     146   |  May 4 – May 30, 2026 |
 
## Buy & Hold Comparison
 
| Strategy Return | Buy & Hold Return |
|---|---|
| 13.46% | 4.89% |
 
Strategy outperforms buy and hold by 8.57% over the test period.
 
---
 
# Evaluation
 
## What Worked
- 63% win rate — signal has genuine edge in identifying exhausted moves
- 1.694 profit factor at 1:1 R:R is meaningful — implies the wins are cleaner than the losses
- Low drawdown at 2.75% relative to return — equity curve is relatively smooth
- High strategy returns

## Weaknesses
- R:R is 1:1 — leaving significant profit potential on the table. A winning signal at 63% deserves a better exit structure
- Poor Sharpe Ratio
- No session filter — trades done in low volatility
  
## Backtest Limitations
- Test period is 26 days — far too short
  
## Overfitting Concerns
- With only 26 days of data, positive results could reflect a favourable sample rather than a durable edge
- ATR multiplier of 2.5 was used due to high returns in that time period
  
## v2 strat Notes - next step
- Add session filter - to sieve out trades in suboptimal volatility (NY session)
- Add a volume filter

## Backtest Results - Image
<img width="2652" height="814" alt="image" src="https://github.com/user-attachments/assets/0339ea32-6782-4289-aea7-8f2ad19c84d3" />


_Green line indicates strategy return. Blue line indicated Buy & Hold return_
