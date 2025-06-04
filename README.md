# drl-portfolio-optimization

# DRL vs MVO: Portfolio Allocation Under Market Regimes

This repo is my deep dive into a J.P. Morgan research paper that compares Deep Reinforcement Learning (specifically PPO) with traditional Mean-Variance Optimization (MVO) for portfolio allocation. The idea is simple: can a well-trained agent beat classical portfolio theory in real-world backtests?

This project aims to faithfully reproduce the paper’s framework — and then extend it in directions that make it more realistic and robust (e.g., transaction cost modeling, regime switching, etc.).

---

## What I’m Building

- A custom Gym environment that mimics a portfolio manager allocating across sector ETFs
- A PPO agent trained on 60-day lookbacks, with Differential Sharpe Ratio as the reward
- A fully replicable MVO baseline using PyPortfolioOpt and Ledoit-Wolf shrinkage
- 10-year rolling-window backtesting, multiple seeds per window for robustness
- Proper regime labeling (low vs high vol), evaluation with Sharpe, Calmar, Drawdown, Turnover, and more
- Clean codebase designed to be extensible — I want to experiment freely as I go

---

## Why This?

I’ve worked on machine learning in finance before, but this time I wanted to go deeper — both technically and statistically. This paper by J.P. Morgan hit the sweet spot: well-scoped, rigorous, and practical. Plus, it opens up tons of interesting questions around stability, risk management, and generalization in volatile markets.

---

## 💡 Repo Structure

drl-portfolio-optimization/
├── data/ # Yahoo Finance downloads + processed features
├── notebooks/ # EDA, MVO sanity checks
├── src/
│ ├── env/ # Gym-style trading environment
│ ├── rl/ # PPO training logic
│ ├── mvo/ # Mean-Variance Optimizer
│ ├── eval/ # Sharpe, Calmar, Δpw, plots, Pyfolio stats
│ └── utils/ # Data pipeline, volatility labeling, helpers
├── experiments/ # Hyperparameter configs
├── results/ # Backtest logs, saved agents, figures
├── docs/ # Mapping code to paper results
└── main.py # CLI to train/test/backtest

















