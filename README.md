## Bitcoin Alpha Intelligence Platform

Real-time Bitcoin analytics dashboard with 5 advanced algorithmic trading strategies, live Binance.US execution, and a professional dark UI. Built with Plotly Dash, SQLite, and the Binance.US API.

---

### Features

- **Live price tracking** — real-time BTC/USDT price, volume, market cap
- **Technical analysis** — RSI, MACD, ADX, EMA ribbon (8/13/21/34/55/200), Bollinger Bands, StochRSI, OBV, CMF, Williams %R, VWAP
- **Market regime detection** — automatically classifies bull trend, bear trend, ranging, or volatile
- **Sentiment analysis** — Fear & Greed index, news sentiment, social media tracking
- **Macro dashboard** — DXY, Gold, SPY, VIX, 10Y Treasury via FRED API
- **On-chain data** — hash rate, active addresses, transaction volume
- **5 trading strategies:**
  - Trend Momentum — ADX + EMA ribbon + MACD confluence
  - Mean Reversion — RSI + StochRSI + Bollinger Band oversold fades
  - Volatility Breakout — BB squeeze release with volume confirmation
  - Multi-TF Confluence — 5m + 1h + 1d signal alignment
  - AI Composite — regime-aware weighted blend of all indicators
- **Risk management** — Kelly Criterion position sizing, ATR trailing stops, 5% daily loss circuit breaker
- **Portfolio analytics** — Sharpe ratio, Sortino ratio, max drawdown, Calmar ratio, profit factor
- **Paper and live trading** — simulate with paper mode or execute real orders on Binance.US

---

### Setup

**1. Clone the repo**

```
git clone https://github.com/brendannorris-dot/bitcoin-algorithmic-trading
cd bitcoin-algorithmic-trading
```

**2. Install dependencies**

```
pip install -r requirements.txt
```

**3. Create your environment file**

```
cp .env.example .env
```

Open `.env` and add your API keys:

```
# Required for live trading
BINANCE_API_KEY=your_key_here
BINANCE_API_SECRET=your_secret_here

# Optional — enhances data sources
GROQ_API_KEY=your_key_here
COINGECKO_API_KEY=your_key_here
CRYPTOPANIC_API_KEY=your_key_here
```

Get your Binance.US API keys at https://www.binance.us/settings/api-management
- Enable Reading + Enable Spot and Margin Trading
- IP whitelist your machine for security

**4. Run**

```
python3 main.py
```

Open http://localhost:8050 in your browser.

---

### Trading modes

| Mode | Description |
|------|-------------|
| Paper | Simulated trades, no real money. Good for testing strategies. |
| Live | Real MARKET orders on Binance.US. Requires API keys in .env. |

Switch between modes per-strategy on the Bot tab.

---

### Tech stack

- **Backend:** Python, Flask, SQLite, APScheduler
- **Frontend:** Plotly Dash, Dash Bootstrap Components
- **Data:** Binance.US API, FRED API, CoinGecko, CryptoPanic
- **Analysis:** pandas, NumPy, custom indicator engine

---

### Disclaimer

This software is for educational purposes only. Cryptocurrency trading carries significant risk. Past performance does not guarantee future results. Use live trading mode at your own risk. The authors are not responsible for any financial losses.
