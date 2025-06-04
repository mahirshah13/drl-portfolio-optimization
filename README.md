# drl-portfolio-optimization

# DRL vs MVO: Portfolio Allocation Under Market Regimes

This project is based on a 2023 J.P. Morgan research paper that compares deep reinforcement learning (specifically PPO) with traditional mean-variance optimization (MVO) for portfolio allocation across US equity sectors.

The goal is to reproduce their results and then build on top of it. I’m using S&P 500 sector ETFs, SPY, and VIX data from 2006 to 2021 to evaluate both strategies across different market regimes.

---

## What this repo includes

- A custom Gym environment that simulates portfolio rebalancing
- PPO agent with Differential Sharpe Ratio as the reward
- MVO baseline with Ledoit-Wolf covariance shrinkage
- Rolling-window backtests (10 windows × 5 seeds each)
- Full evaluation: Sharpe, Calmar, Max Drawdown, Turnover (Δpw), etc.
- Simple, modular code structure that’s easy to extend

---

## Folder structure

drl-portfolio-optimization/
│
├── data/
│ ├── raw/ # Raw CSVs from Yahoo Finance
│ └── processed/ # Final processed features (returns, volatility, regime)
│
├── notebooks/ # EDA and experimentation notebooks
│
├── src/
│ ├── env/ # Custom Gym environment
│ ├── rl/ # PPO agent, training loop
│ ├── mvo/ # MVO baseline optimizer
│ ├── eval/ # Metrics, plotting, Pyfolio wrapper
│ └── utils/ # Data loading, preprocessing, regime labeling
│
├── experiments/ # Configs for training/backtests
├── results/ # Backtest logs, agent weights, plots
├── docs/ # Paper reproduction tracking
├── main.py # CLI entrypoint
└── requirements.txt


---

## Data used

- Sector ETFs: XLF, XLK, XLY, XLI, XLE, XLV, XLB, XLRE, XLU, XLC
- SPY (S&P 500)
- ^VIX (volatility index)
- Time period: 2006 to 2021 (daily)
- Source: Yahoo Finance (`yfinance`)

---

## Quickstart

```bash
# Install requirements
pip install -r requirements.txt

# Step 1: Download and process data
python src/utils/data_loader.py
python src/utils/feature_pipeline.py

# Step 2: Train the DRL agent (later)
python main.py --mode train_drl

# Step 3: Run MVO baseline
python main.py --mode run_mvo













