# Trading

Python tools for quantitative analysis and trading of financial instruments.

## Tools

### Options Deviation Calculator (`OptionsDeviationCalc_2_0.ipynb`)

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/scottmarino-io/Trading/blob/main/OptionsDeviationCalc_2_0.ipynb)

Quantitative options analysis tool that maps historical price move distributions to option strikes — helping identify statistically probable price targets relative to a given expiration.

**How it works:**

1. Pulls historical price data for any ticker via Yahoo Finance
2. Calculates rolling percentage change distribution over the DTE window (days to expiration)
3. Builds a full percentile profile (0–100th) of historical moves
4. Maps each percentile price target to the nearest available option strike
5. Plots a histogram comparing all-time distribution, recent 20-day distribution, and current reading

**Use cases:**
- Identify strikes that align with historically probable price ranges
- Visualize where the market has historically landed over a given horizon
- Find statistically meaningful strike levels for CSPs, covered calls, and spreads

**Inputs:**

| Prompt | Example | Notes |
|--------|---------|-------|
| Ticker | `SPY` | Any yfinance-supported symbol |
| Expiration date | `2025-03-21` | Must be a future date |
| Timeframe | `1y` | Historical lookback period |
| Interval | `1d` | Data granularity |

**Output:**

- Percentile table mapping historical return % → price → nearest option strike → last price
- Plotly histogram of % change distribution (all-time vs. recent 20 days vs. current)

## Requirements

- Python 3.9+
- `pandas`, `numpy`, `yfinance`, `plotly`

Or run directly in [Google Colab](https://colab.research.google.com/github/scottmarino-io/Trading/blob/main/OptionsDeviationCalc_2_0.ipynb) — no local setup needed.

```bash
pip install pandas numpy yfinance plotly
```
