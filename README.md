# Algorithmic Commodity Trading System (XAUUSD Breakout EA)

An institutional-grade algorithmic trading system and quantitative optimization framework developed in **MQL5** for international **Gold (XAUUSD)** on the **MetaTrader 5** platform.

---

## 📌 Strategy & Architectural Overview

```
┌────────────────────────────────────────────────────────────────────────┐
│                        PRICE-ACTION STRUCTURE                          │
│  - Inside-Candle Coiling Detection across Multi-Timeframe Bars         │
│  - High-Low Structural Compression Boundary Mapping                    │
│  - Dynamic Entry Buffers & Volatility Range Threshold Filtering        │
└───────────────────────────────────┬────────────────────────────────────┘
                                    │
                                    ▼
┌────────────────────────────────────────────────────────────────────────┐
│                       EXECUTION & ORDER MECHANICS                      │
│  - Dual Stop Pending Orders with One-Cancels-Other (OCO) Logic         │
│  - Strict Slippage Deviation Control & Expiry Bar Cancellation         │
│  - UTC Session Timing Filters (Liquidity-Optimal Hours)               │
└───────────────────────────────────┬────────────────────────────────────┘
                                    │
                                    ▼
┌────────────────────────────────────────────────────────────────────────┐
│                   QUANTITATIVE OPTIMIZATION PROTOCOL                   │
│  - High-Throughput Strategy Tester Sweeps (3,591,000 Iterations)       │
│  - Throughput: 3,300+ Passes / Second across Tick Data Archives        │
│  - Objective Function: Recovery Factor > 9.0, Linearity R² > 0.90      │
└───────────────────────────────────┬────────────────────────────────────┘
                                    │
                                    ▼
┌────────────────────────────────────────────────────────────────────────┐
│                     DYNAMIC RISK & CAPITAL PRESERVATION                │
│  - Structural Half-Coil Invalidation Levels vs Fixed Stop-Loss         │
│  - Multi-Stage Trailing Stop Engines with Minimum Step Increments      │
│  - Mandatory End-of-Day (EOD) Risk Neutralization                      │
└────────────────────────────────────────────────────────────────────────┘
```

---

## ⚡ Technical Highlights

* **Automated Strategy Architecture:** Built natively in MQL5 using standard trade classes (`CTrade`, `CPositionInfo`, `COrderInfo`, `CSymbolInfo`) to handle asynchronous order management and position tracking with minimal latency.
* **Large-Scale Phase Optimization:** Executed multi-parameter grid searches across **3,591,000 iterations** at an execution speed of **3,300+ passes/second**, uncovering robust parameter sweet spots while avoiding curve-fitting.
* **Capital Risk Profiling:** Ranked candidate configurations by Recovery Factor ($\frac{\text{Net Profit}}{\text{Max Drawdown}}$), achieving record values up to **17.10** with a **97.2% win rate**.
* **Strict Execution Constraints:** Features automatic cancellation of opposite pending orders upon fill (OCO), order expiry timers after $N$ unhit bars, and automatic risk square-off prior to daily market close.

---

## 📊 Backtest Analytics & Optimization Results

### 1. Champion Equity Curve Trajectories ($R^2 = 0.9868$)
Evaluated across tick data to ensure high linearity and smooth capital appreciation:

![Phase 1 Champions Equity Curves](assets/phase1_champions_equity_curves.png)

### 2. Parameter Sensitivity & Distribution Profiling
Surface analysis showing profitable parameter density across varying buffer heights, range filters, and trailing distances:

![Profitable Passes by Input](assets/profitable_passes_by_input.png)

---

## 📈 Multi-Phase Champion Benchmark

| Performance Metric | Champion A (Peak RF) | Champion B (Max Growth) | Champion C (Balanced) |
| :--- | :--- | :--- | :--- |
| **Recovery Factor (RF)** | **17.10** | 7.82 | **9.40** |
| **Win Rate** | **97.2%** | 82.5% | **89.4%** |
| **Equity Linearity ($R^2$)** | **0.9868** | 0.9412 | **0.9650** |
| **Profit Factor** | **9.99** | 4.85 | **6.20** |
| **Max Drawdown** | **$4.58 (0.92%)** | $37.26 (7.45%) | **$18.29 (3.65%)** |

---

## 🛠️ Technology Stack

* **Platform:** MetaTrader 5 (MT5)
* **Languages:** MQL5, C++
* **Markets Analyzed:** International Commodities (XAUUSD / Gold Spot & Futures)
* **Methodology:** Systematic Price Action, Volatility Coiling, Quantitative Grid Optimization

---

## 🔒 Confidentiality Notice
*Note: Proprietary entry buffer equations, live execution magic numbers, and full source code have been omitted to protect strategy intellectual property. *
