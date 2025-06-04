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



---

## 📈 Data + Assets

- S&P 500 sector ETFs (XLF, XLK, XLV, etc.)
- SPY (market proxy)
- VIX (volatility index)
- Daily data from **2006 to 2021**, pulled via `yfinance`

---

## Quickstart

# Clone and install
git clone https://github.com/your-username/drl-portfolio-optimization
cd drl-portfolio-optimization
pip install -r requirements.txt

# Download and process data
python src/utils/data_loader.py
python src/utils/feature_pipeline.py

# (Later) Train PPO or run MVO
python main.py --mode train_drl
python main.py --mode run_mvo

Metrics Logged
Sharpe, Calmar, Sortino, Max Drawdown

Turnover (Δpw) — how much the portfolio changes

VaR, Tail ratio, Return stability

Logged via Pyfolio + CSVs + plots

Timeline
Day	Focus
1	Data, returns, volatility metrics
2	Build Gym environment, rewards
3	PPO agent and training loop
4	MVO baseline and optimization
5	Full backtesting, multi-seed
6	Plotting, metrics, interpretation
7	Docs, polish, experiment extensions

Paper Being Reproduced
Deep Reinforcement Learning for Optimal Portfolio Allocation: A Comparative Study with Mean-Variance Optimization
FinPlan 2023, JP Morgan AI Research

What’s Next
Add realistic transaction costs and slippage modeling

Train regime-specific agents and switch adaptively

Benchmark vs other DRL algos (TD3, SAC, etc.)

Run ablation studies on features, lookbacks, risk aversion

Maintained by
Mahir Shah — UC Berkeley
I love working on ML + finance, especially when it involves reproducible research and real-world constraints.
Feel free to reach out or fork this and build on top.


---

Let me know if you want:
- A shorter one-liner for the GitHub sidebar or LinkedIn
- An academic-facing version (for a research resume or professor)
- A punchier title or slogan

Ready to roll into **Day 2** when you are.






















