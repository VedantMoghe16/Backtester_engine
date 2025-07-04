# Backtester_engine
Backtesting Engine A robust, multi-strategy quantitative trading backtesting framework. The engine handles data loading, signal generation, portfolio construction, and performance analysis in a single pipeline. 
🔹 Key Features:

Supports both ML-based (LightGBM) and traditional momentum/reversal strategies

Market-neutral portfolio construction with risk controls

Realistic transaction cost modeling

Comprehensive performance metrics (Sharpe ratio, drawdowns, etc.)

Interactive visualization of results

🔹 Tech Stack:
Python | LightGBM | scikit-learn | pandas | matplotlib

🔹 Ideal For:

Quantitative researchers developing alpha signals

Traders evaluating strategy performance

Students learning algorithmic trading concepts

The engine handles data loading, signal generation, portfolio construction, and performance analysis in a single pipeline. Includes detailed documentation and example notebooks.

What I Learned
1. Alpha & Beta (Finance Concepts)
Alpha: Represents a strategy's ability to beat the market. I tried to generate alpha by building multiple strategies based on market signals such as EMA crossover, Bollinger Bands, Momentum, and factor models from Parquet-based data.

Beta: Measures a portfolio’s sensitivity to the market. Though not explicitly computed yet, the correlation analysis gives a proxy for understanding beta in this context.

2. Numpy for Fast Computation
Used numpy for handling vectorized calculations on signals, prices, and returns.

Implemented portfolio normalization and return computation without for-loops for better performance.

Learned how to clean and reshape matrices using slicing, np.vstack, and broadcasting.

3. CUDA & Numba (Foundations of Acceleration)
Studied how Numba and CUDA could accelerate portfolio backtests when scaling to thousands of tickers.

While GPU acceleration isn't implemented yet, I now understand:

How JIT (@jit) compilation can accelerate Python loops.

CUDA can help in massively parallel tasks like portfolio rebalancing or feature extraction from OHLCV data.

Planning to move some signal generation to @njit compiled functions to increase speed in future versions.

4. Working with Financial Data
Learned how to:

Ingest over 500 CSV files from Yahoo Finance.

Use Parquet files (myfeature and myuniverse) to simulate real-world factor models.

Align and handle missing data across tickers and timeframes robustly.

5. Strategy Development
Built and tested 3 strategies:

First TradingStrategy class uses a machine learning-based approach to predict stock returns

Bollinger Bands Mean-Reversion Strategy: This strategy employs a classic technical analysis approach to identify overbought/oversold conditions

Dual Moving Average Crossover


6. Backtesting Engine Design
Created a full backtest pipeline that:

Computes daily returns using signal × return.

Tracks metrics like Sharpe Ratio, Max Drawdown, Turnover, and Correlation.

Plots results using Plotly with subplots for deep diagnostics.
