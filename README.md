# trader-sentiment-analysis
Trader Performance vs. Market Sentiment
Executive Summary
This project analyzes the relationship between Bitcoin Market Sentiment (Fear/Greed Index) and trader behavior on the Hyperliquid exchange. By aligning transactional trading data with daily sentiment labels, I identified distinct behavioral patterns and developed risk-management strategies based on trader consistency.

Methodology (Part A)
1. Data Preparation & Cleaning
Data Audit: Analyzed two datasets: Bitcoin Sentiment (Daily) and Hyperliquid Trader Data (Transactional).

Aggregation: To align the datasets, I aggregated the high-frequency trader data into a daily grain per account.

Feature Engineering: Calculated key performance indicators (KPIs) including:

Daily PnL: Total profit/loss per day.

Win Rate: Percentage of profitable trades.

Long/Short Ratio: Trader bias toward buying vs. selling.

Leverage Metrics: Average and maximum leverage used per session.

Key Insights (Part B)
Sentiment Sensitivity: Inconsistent traders tend to over-leverage significantly during "Extreme Greed" phases, leading to larger liquidations when the market corrects.

Trade Frequency: Market "Fear" causes a spike in trade frequency among retail accounts (panic trading), while Consistent Winners tend to maintain a stable or lower frequency, waiting for high-conviction setups.

The Contrarian Gap: On "Fear" days, the Long/Short ratio for top-tier traders often increases before a price rebound, suggesting they are buying the dip while the majority is selling.

Actionable Output (Part C)
Based on the analysis, I propose the following two "Rules of Thumb" for the Primetrade.ai platform:

Strategy 1: The "Greed Cap" (Risk Mitigation)
Rule: If the Fear/Greed Index exceeds 75 (Extreme Greed), automatically reduce the maximum allowable leverage for the "Inconsistent" segment by 50%.

Goal: To prevent catastrophic "blow-ups" during market tops driven by emotional euphoria.

Strategy 2: The "Alpha-Follower" (Signal Generation)
Rule: When Market Sentiment is in Fear (< 30), monitor the Long/Short ratio of the "Consistent Winners" segment. If they begin a "Long" accumulation, trigger a buy signal for the copy-trading bot.

Goal: To capitalize on "Smart Money" behavior during periods of retail panic.

Setup & How to Run
Clone this repository.

Ensure you have the datasets in the /data folder.

Install dependencies: pip install pandas matplotlib seaborn.

Run the Jupyter Notebook: jupyter notebook analysis.ipynb.
