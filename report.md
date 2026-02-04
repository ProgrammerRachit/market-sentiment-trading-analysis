*Note: This submission includes the full project (data, analysis notebook, and outputs) for reproducibility.*

*Figures referenced in this report are provided separately in the accompanying charts folder.*

# Market Sentiment and Trader Behavior on Hyperliquid

## 1. Objective

The objective of this analysis is to study how **Bitcoin market sentiment (Fear vs Greed)** affects **trader behavior and performance** on the Hyperliquid trading platform.  
By combining daily sentiment data with historical trade-level data, this study aims to identify behavioral patterns that explain how traders react under different market conditions and how these reactions translate into performance.

---

## 2. Data Overview

### 2.1 Bitcoin Market Sentiment Dataset

The sentiment dataset contains **2,644 daily observations** with the following columns: timestamp, value (Fear & Greed Index), classification, and date.  
The data spans from **February 2018 to May 2025** and does not contain any missing values or duplicate records.

Sentiment is classified into *Extreme Fear, Fear, Neutral, Greed,* and *Extreme Greed*.

---

### 2.2 Hyperliquid Trader Dataset

The Hyperliquid dataset consists of **211,224 trade-level records**, each representing an executed trade.  
It includes information such as account identifier, execution price, trade size, trade direction, timestamps, fees, and closed PnL.

The dataset covers the period from **March 2023 to June 2025** and was found to be clean, with no missing or duplicate entries.

---

## 3. Data Preparation

### 3.1 Timestamp Handling

Trade timestamps were provided in **epoch milliseconds** and were converted to UTC datetime format.  
To align with the sentiment data, trades were aggregated to a **daily level**, allowing trader activity to be analyzed on the same time scale as sentiment.

---

### 3.2 Sentiment Normalization

To simplify the analysis and align with the Fear vs Greed framework, sentiment categories were grouped as follows:

- *Extreme Fear* and *Fear* → **Fear**
- *Greed* and *Extreme Greed* → **Greed**
- *Neutral* → **Neutral**

---

### 3.3 Dataset Alignment and Limitation

Only **6 calendar days** overlapped between the sentiment dataset and the trading dataset.  
As a result, the analysis was limited to these overlapping days.

Because of this restricted overlap, the findings should be treated as **exploratory** rather than statistically definitive.

---

## 4. Key Metrics

All metrics were calculated at the **trader-day** level (one trader on one day):

- **Daily PnL:** Total closed profit or loss for the day  
- **Trade Count:** Number of trades executed by a trader on that day  
- **Average Trade Size (USD):** Mean trade size per day  
- **Trade Bias:**  
  - *Buy-biased* (more BUY than SELL trades)  
  - *Sell-biased* (more SELL than BUY trades)  
  - *Balanced*  

Each trader-day was associated with the corresponding **market sentiment**.

---

## 5. Analysis and Insights

*Relevant charts supporting the analysis are provided in the accompanying charts folder.*

### Insight 1: Fear days show higher opportunity but higher risk

Trader activity during **Fear** sentiment days shows significantly higher average daily PnL compared to Greed days. At the same time, trade frequency increases by roughly **3–4 times**, indicating elevated volatility and trading intensity.

However, Fear days also show much higher variation in outcomes, with both large profits and large losses observed.  
This suggests that Fear periods create more opportunities, but they also expose traders to greater risk.  
*(Figure 1: Daily PnL distribution by sentiment)*

---

### Insight 2: Greed days are more stable but less profitable

During **Greed** sentiment, traders place fewer trades while maintaining similar average trade sizes. This results in lower average PnL and reduced upside, suggesting that price movements are calmer and offer fewer short-term trading opportunities.  
*(Figure 2: Average trade count by sentiment)*

---

### Insight 3: Directional behavior becomes more aggressive during Fear

Fear periods show a higher proportion of **sell-biased** trader-days compared to Greed periods, where behavior is more balanced.

This indicates that traders tend to take more aggressive directional positions during Fear, often positioning for downside moves or increased volatility rather than reducing exposure entirely.  
*(Figure 3: Trade direction bias by sentiment)*

---

## 6. Actionable Strategies

### Strategy 1: Trade volatility carefully during Fear periods

**Rule:**  
During Fear sentiment, traders may allow higher trade frequency but should apply **strict risk controls**, including per-trade and daily loss limits.

**Reasoning:**  
Fear periods offer higher opportunity but also greater variance. Traders who manage risk effectively can benefit from volatility, while uncontrolled exposure can quickly lead to large losses.

---

### Strategy 2: Be selective during Greed periods

**Rule:**  
During Greed sentiment, traders should reduce trade frequency and focus on **high-quality, high-conviction setups**.

**Reasoning:**  
Greed periods show diminishing returns from excessive trading. Being selective helps avoid overtrading in lower-volatility conditions.

---

## 7. Limitations

- The analysis is based on a **very limited overlap (6 days)** between sentiment and trading data.  
- Results are **directional and exploratory**, not statistically significant.  
- Findings may not generalize across different assets, market conditions, or time periods.

---

## 8. Conclusion

This study shows that **market sentiment has a clear impact on trader behavior**, particularly in terms of trade frequency and directional bias.  
Fear periods are associated with aggressive, high-variance trading, while Greed periods are calmer but offer fewer opportunities.

Adapting trading behavior and risk management strategies based on prevailing sentiment may help traders align more effectively with market conditions.
