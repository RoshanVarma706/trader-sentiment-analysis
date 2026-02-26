# trader-sentiment-analysis
Trader Performance vs. Market Sentiment
Executive Summary
This Task analyzes the relationship between Bitcoin Market Sentiment (Fear/Greed Index) and trader behavior on the Hyperliquid exchange. By aligning transactional trading data with daily sentiment labels, I identified distinct behavioral patterns and developed risk-management strategies based on trader consistency.

Methodology (Part A)
1. Data Integration & Cleaning
Dataset Merging: I performed a left join between the Bitcoin Market Sentiment (daily) and Historical Trader Data (transaction-level).

Time Alignment: Transaction timestamps were normalized to a daily format (YYYY-MM-DD) to align with the Fear & Greed Index records.

Data Quality: Checked for missing values and duplicates. Handled closedPnL nulls to ensure average profit calculations remained accurate.

2. Feature Engineering
Created specific metrics to capture both performance and behavior:

Performance Metrics: Daily PnL per account, Win Rate per sentiment classification, and average Profit/Loss.

Behavioral Metrics: Trade frequency (total trades per day per user) and sentiment-based bias (long/short ratio).

3. Quantitative Analysis
I categorized the data by sentiment classification (Extreme Fear, Fear, Neutral, Greed, Extreme Greed) to compare how professional and retail behaviors shifted:

Comparative Analysis: Calculated the mean PnL and Win Rates across each sentiment bucket.

Segmentation: Grouped traders into "Frequent" vs. "Infrequent" based on their daily trade count to identify who suffers most during high-volatility (Fear) events.

Key Insights (Part B)
Sentiment Sensitivity: Inconsistent traders tend to over-leverage significantly during "Extreme Greed" phases, leading to larger liquidations when the market corrects.

Trade Frequency: Market "Fear" causes a spike in trade frequency among retail accounts (panic trading), while Consistent Winners tend to maintain a stable or lower frequency, waiting for high-conviction setups.

The Contrarian Gap: On "Fear" days, the Long/Short ratio for top-tier traders often increases before a price rebound, suggesting they are buying the dip while the majority is selling.

Actionable Output (Part C)
Based on the analysis, I propose the following two "Rules of Thumb" for the Primetrade.ai platform:

Rule A: The "Slow Down" Rule (For Fearful Markets)
The Problem: Your data shows frequent traders lose a lot in "Extreme Fear."

The Solution: If the market is in Fear, the platform should limit how many trades a person can make per hour.

The Logic: "Fear" creates big price swings (high profit). By forcing traders to trade less, you force them to pick only the very best setups instead of panic-clicking.

Rule B: The "Safety First" Rule (For Greedy Markets)
The Problem: Your data shows "Greed" has the lowest average PnL. People are likely buying "the top" with too much leverage.

The Solution: If the market is in Greed, automatically lower the maximum leverage.

The Logic: Since the average profit is lower in Greed, taking high risks (high leverage) doesn't make mathematical sense. This protects the trader from a sudden market "dump."

Setup & How to Run

Open Google Colab 

Upload the CSV files and run the code.

Ensure you have the datasets in the /data folder.
OR
Install dependencies: pip install pandas matplotlib seaborn.

Run the Jupyter Notebook: jupyter notebook analysis.ipynb.
