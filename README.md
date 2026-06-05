# 🤖 AI-Assisted SMC (Smart Money Concepts) Trading Bot | Pine Script v5

This repository features an automated algorithmic trading system engineered in **Pine Script v5** for the TradingView platform. The algorithm automates the detection of institutional liquidity sweeps and market structure shifts (MSS) to execute high-probability reversal trades.

The project was developed using a hybrid engineering approach, combining technical analysis and financial programming with **Advanced Artificial Intelligence (AI) assistance** to accelerate debugging, codebase refactoring, and risk-management optimization.

---

## 🧠 Problem Solving & Engineering Challenges

Developing this trading bot required overcoming significant programming obstacles and market structure anomalies. Below is the documentation of the engineering and problem-solving process:

### 1. Resolving the Timeline Disconnect (Historical Data Bug)
* **The Problem:** Early iterations of the script suffered from a structural logic syntax error during historical data parsing. The bot remained trapped in a "past loop," failing to calculate real-time metrics on live candle updates and freezing execution at older data feeds.
* **The Solution:** Utilizing AI-driven logical debugging, the entire architecture was refactored into **Pine Script v5**. Timeframe fetching and execution loops were synchronized, anchoring the algorithm dynamically to the hard-right edge of the data feed to ensure seamless, real-time live execution.

### 2. Engineering the "Time-Exit Protection" Against Choppy Markets
* **The Problem:** During initial tests on hyper-scalping timeframes (5-minute charts), the algorithm frequently accumulated break-even trades or micro-losses. The issue stemmed from market consolidation phases (sideways price action), where the capital remained locked and hostage to market noise without reaching structural targets.
* **The Solution:** A strict programmatic time-decay function was introduced: `max_candele_durata = 30`. If a trade fails to hit either the Stop Loss or Take Profit within 30 candles (7.5 hours on a 15m chart), the bot automatically forces a market exit ("Chiusura Tempo"). This safeguards account equity and protects psychological trading morale during low-volume sessions.

### 3. Asset & Capital Optimization (The Micro-Account Compromise)
* **The Problem:** Testing the strategy on traditional equity vehicles like the SPY ETF yielded microscopic monetary returns due to low intraday volatility, making the strategy highly inefficient for smaller, realistic retail capital sizes (e.g., live accounts under $1,000).
* **The Solution:** Through rigorous cross-asset data analysis, the strategy was shifted toward high-volatility, highly liquid derivative instruments—specifically **Index CFDs (SPX500)** and **Cryptocurrencies (BTCUSD)**. The **15-minute timeframe** was identified as the operational "Sweet Spot," filtering out minor market noise while preserving necessary intraday volatility.

---

## 📊 Backtesting Methodology & Performance Metrics

To validate the mathematical reliability of the strategy prior to live deployment, exhaustive historical backtests were conducted using TradingView's native *Strategy Tester* engine.

The algorithm utilizes an asymmetric risk-mitigation framework with a strict **1:2 Risk-to-Reward Ratio ($R:R = 2.0$)**. This mathematical asymmetry ensures that a single successful trade financially covers two consecutive losses.

### Key Performance Summary (15-Minute Timeframe):

| Underlying Asset | Data Feed / Broker | Registered Performance | Operational Notes |
| :--- | :--- | :--- | :--- |
| **SPX500 (CFD)** | Capital.com | **+315.00 USD** | Highly linear equity curve; exceptional structural stability over time. |
| **BTCUSD** | Binance / Coinbase | **Net Positive** | Accelerated drawdown recovery driven by the asset's natural directional volatility. |

---

## 🛠️ Technology Stack
* **Language:** Pine Script v5 (TradingView Proprietary Language)
* **Development Environment:** TradingView Pine Editor, AI-Assisted Debugging Tools
* **Financial Logic:** Smart Money Concepts (SMC), Liquidity Sweeps, Order Blocks Tracking, Automated Risk Management.

---

## 📈 Future Roadmap
- Implementation of automated execution hooks (Alerts / Webhooks) to bridge TradingView signals directly into retail broker APIs for hands-free live execution.
- Integration of a macro-economic sentiment filter (External News Engine) to temporarily halt the bot during high-impact financial releases (e.g., US CPI, FOMC rate decisions).
