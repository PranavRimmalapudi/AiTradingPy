# AI Stock Indicator Bot 📈

> XGBoost-powered paper trading bot using the Alpaca API

![Python](https://img.shields.io/badge/Python-3.x-blue) ![XGBoost](https://img.shields.io/badge/Model-XGBoost-orange) ![Paper Trading](https://img.shields.io/badge/Mode-Paper%20Trading-green)

## About
An AI-driven paper trading bot that trains an XGBoost classifier on historical 5-minute OHLCV data to predict short-term price direction. It trades 5 major tech stocks (AAPL, MSFT, TSLA, NVDA, GOOG) with built-in stop-loss protection and logs every trade to a CSV.

Built as a personal project to explore machine learning applied to financial data.

## How It Works
1. Loads historical 5-min candlestick CSVs per symbol
2. Engineers features: % return, rolling volatility, moving average divergence
3. Trains an XGBoost classifier (80/20 train/test split)
4. Replays data step-by-step, executing BUY / SELL / HOLD via Alpaca paper API

## Tech Stack
- **XGBoost** — ML prediction model
- **Alpaca API** — Paper brokerage (no real money)
- **Pandas / NumPy** — Data processing
- **scikit-learn** — Train/test split
- **joblib** — Model persistence

## Setup
```bash
pip install pandas numpy xgboost scikit-learn alpaca-trade-api joblib
```
1. Add your Alpaca API key and secret in the `CONFIG` section at the top of `bot.py`
2. Add CSV files named `AAPL_5min.csv`, `MSFT_5min.csv`, etc. (5-min OHLCV format)
3. Run: `python bot.py`

## Features
- Auto stop-loss at 10% below entry price
- Trades 5 symbols simultaneously in replay mode
- Logs every trade (time, symbol, action, price, equity, cash) to `trade_log.csv`
- Model saved to `xgb_model.joblib` for reuse

## Disclaimer
Paper trading only — for educational purposes. Not financial advice.

---
*Built by [Pranav Rimmalapudi] | 9th grade | Part of an AI/ML portfolio*
