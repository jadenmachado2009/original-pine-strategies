# Original Strategy Lab

> First stage of a fully-automated prop firm trading pipeline — strategy research and signal development in Pine Script.

This folder contains self-developed Pine Script strategies built to generate entry/exit signals on TradingView. The end goal is a profitable, automated signal engine that feeds into a prop firm trading pipeline.

This is **stage 1** — research and backtesting only. The full pipeline:

1. **Strategy Lab** (this folder) — develop and backtest Pine Script strategies on TradingView
2. **Signal Bridge** — extract signals via webhooks or alerts
3. **Execution Layer** — automated order routing with risk controls
4. **Prop Firm Account** — live deployment on funded accounts

Stages 2–4 do not exist yet. This folder is where the work starts.

---------------

## Purpose

Build and test original Pine Script strategies to find a consistently profitable signal engine.

Each strategy is coded as a `strategy()` block in Pine Script v6 with realistic simulation parameters baked in — commission, slippage, fixed position sizing, and defined capital. Example:

```pine
strategy("Strategy Name",
     overlay           = true,
     initial_capital   = 1000000,
     default_qty_type  = strategy.fixed,
     default_qty_value = 2,
     commission_type   = strategy.commission.cash_per_contract,
     commission_value  = 2.5,
     slippage          = 2)
```

The simulation parameters are set to approximate realistic trading conditions, not to inflate backtest results.

---------------

## Scope & Limitations

**In scope:**
- Short-term intraday strategies (primary timeframe: 15-minute)
- Self-developed strategy logic — original combinations of public and proprietary concepts
- Pine Script v6, backtested via TradingView Strategy Tester
- Nasdaq 100 Futures (NQ1!) exclusively
- No session restriction — strategies may trade any session unless a specific session filter is part of the hypothesis

**Out of scope:**
- Long-term alpha decay studies — backtest windows are too short to support those claims
- Multi-year institutional research — data constraints reduce validity
- Discretionary trading
- Public strategy recreations (those belong in `/public-strategy-benchmarking`)

**Honest constraints:**
- Backtest periods are typically 2–4 months. Results reflect that specific window, not a universal edge.
- Strategies use publicly known components (EMAs, RSI, ATR, engulfing patterns, etc.) in original combinations. Originality is in the assembly, filtering, and parameter selection — not in inventing new indicators.

-----------

## Strategy Documentation Standard

Every strategy must have a `RESEARCH_LOG.md` covering these sections:

### Strategy Overview
- Type (original)
- Timeframe
- Asset: NQ1!
- Backtest period

### Note on Originality
Acknowledge which components are publicly known and what the original contribution is (combination, parameters, filtering, etc.).

### Hypothesis
One clear statement: what edge is being tested and why it should work.

### Entry & Exit Rules
- Long and short conditions, written explicitly
- Stop-loss method and value
- Take-profit method and value
- R:R ratio

### Simulation Parameters
- Initial capital
- Position size (contracts or % equity)
- Commission model and value
- Slippage setting
- Any margin notes

### Parameter Rationale
For each tunable parameter: why that value was chosen, and whether overfitting is a concern.

### Backtest Results

| Win Rate | Profit Factor | Sharpe Ratio | Max Drawdown | No. Trades | Backtest Period |
|----------|---------------|--------------|--------------|------------|-----------------|
| % | x.xx | x.x | x.xx% | n | date range |

Include a buy & hold comparison where applicable.

### Evaluation
- **What worked** — positive observations
- **Weaknesses** — honest problems (trade frequency, parameter sensitivity, etc.)
- **Backtest limitations** — sample size, market regime bias, etc.
- **Overfitting concerns** — any parameter that was tuned to the dataset rather than derived from theory

### Backtest Results Image
Screenshot from TradingView Strategy Tester with equity curve.

-------

## Methodology

### Code Standards
- Pine Script **v6**
- `strategy()` blocks only — backtest output is required for every strategy
- Realistic simulation: commission, slippage, and position sizing defined in every script
- No repainting indicators
- No look-ahead bias

### Backtest Discipline
- Backtest window stated explicitly (exact date range)
- Trade count reported — low trade counts are flagged as unreliable
- Buy & hold comparison included as a baseline sanity check
- Results presented as-is, not cherry-picked from the best window

### Overfitting Awareness
- Specific parameter values selected via optimization are acknowledged as potential overfit
- Standard values (ATR 14, EMA 200, etc.) are preferred where possible
- Any non-standard parameter choice must have a documented rationale in the research log

---

## Comparative Reporting

Strategies are compared across:
- Win rate, profit factor, Sharpe ratio, max drawdown
- Trade frequency (fewer, higher-quality trades preferred)
- Buy & hold outperformance
- Market regime suitability (trending vs ranging vs volatile)

Running comparisons are maintained in `_logs/development-log.md`.

---------

## Disclaimer

This is a personal research project, not investment advice and not a signal service. Backtest results are not predictive of future performance. No strategy in this folder has been deployed with real capital — that happens only after passing all downstream pipeline stages, if at all.

This work demonstrates quantitative reasoning, systematic experimentation, and applied programming in financial markets — skills developed through independent research.

---------------

## Roadmap

- [ ] Build as many pine strategies as possible and then sieve out strategies with a high pass probability
- [ ] Begin stage 2 research (signal bridge / webhook extraction)
- [ ] Define criteria for when a strategy is "good enough" to move to stage 2
 
