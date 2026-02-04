# Market Sentiment Trading Analysis

This project explores how **Bitcoin market sentiment (Fear vs Greed)** relates to **trader behavior and performance** using historical trade data from the Hyperliquid platform.

The objective is to understand how different sentiment regimes influence trading activity, risk-taking behavior, and outcomes, and to derive **practical insights** that can inform trading decisions.

---

## Project Overview

The analysis combines:
- Daily Bitcoin **Fear & Greed Index** data
- Trade-level historical data from **Hyperliquid**

Trades are aggregated to a **trader-day** level and aligned with market sentiment to study changes in behavior and performance across sentiment regimes.

---

## Datasets

### 1. Bitcoin Market Sentiment
- Daily Fear & Greed Index values
- Coverage: February 2018 to May 2025
- Sentiment categories: Extreme Fear, Fear, Neutral, Greed, Extreme Greed

### 2. Hyperliquid Trade Data
- Over 200,000 executed trades
- Includes trade size, direction, timestamps, fees, and closed PnL
- Coverage: March 2023 to June 2025

---

## Key Metrics

Metrics are computed at the **trader-day** level:

- **Daily PnL** – Total closed profit or loss per day
- **Trade Count** – Number of trades executed
- **Average Trade Size (USD)**
- **Trade Bias** – Buy-biased, Sell-biased, or Balanced

Each trader-day is associated with the corresponding **market sentiment**.

---

## Analysis Highlights

- Fear sentiment days show **higher trading activity** and **greater variance in PnL**
- Greed sentiment days tend to be **calmer**, with fewer trades and lower average returns
- Traders display more **directional bias** during Fear regimes

These observations are based on aggregated trader-day behavior and should be interpreted in the context of market volatility.

Supporting visualizations are provided in the `outputs/charts/` directory.

---

## Project Structure

```text
market-sentiment-trading-analysis/
│
├── data/
│   ├── sentiment.csv
│   └── trades.csv
│
├── notebooks/
│   └── analysis.ipynb
│
├── outputs/
│   ├── charts/
│   └── report.md
│
├── requirements.txt
└── README.md
```
How to Run:
1. Clone the repository 
2. Create the virtual environment
 3. Install dependencies:
    pip install -r requirements.txt
4. Open the notebook:
   jupyter notebook
 5. Run analysis.ipynb

Notes and Limitations
1. The analysis is limited by a small overlap period between sentiment and trading data
2. Results are exploratory and not statistically conclusive
3. Findings should be interpreted as behavioral signals rather than trading guarantees

Author
Created by Aaryan as an exploratory data analysis project.
