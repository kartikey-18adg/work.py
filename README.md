## PrimeTrade: Trader Performance vs Market Sentiment

This project analyzes Hyperliquid historical trades against the Bitcoin Fear & Greed Index to uncover how sentiment affects trader performance.

### Project structure
- `work.py`: main analysis script
- `historical_data.csv`: Hyperliquid trades (sample)
- `fear_greed_index.csv`: Fear & Greed daily data
- Outputs: `trader_sentiment_analysis.xlsx`, `*.png` charts

### Setup
1) Python 3.11+ (tested on 3.13)
2) Install deps:
```bash
python -m pip install -r requirements.txt
```

### Run
```bash
python work.py
```

### What it does
- Normalizes both datasets and merges on `Date`
- Computes metrics per `account-Date-Classification`
- Creates charts: sentiment distribution, PnL by sentiment, top traders, transitions
- Exports Excel with `Trader Metrics` and `Merged Data`

### Notes
- If your trades CSV has a `leverage` column, it will be used; otherwise NaN.
- Matplotlib runs in headless mode (`Agg`) so it works on servers/CI.
