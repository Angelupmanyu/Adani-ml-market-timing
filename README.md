# Adani-ml-market-timing
Predicting favorable market conditions for Adani Enterprises using technical indicators and a Random Forest classifier with realistic backtesting.
# ML-Based Trading Strategy  
Adani Enterprises (ADANIENT.NS)

This project applies machine learning to develop a practical trading strategy for **Adani Enterprises** (ADANIENT.NS).  
Instead of attempting to forecast exact prices—which is extremely difficult and often unreliable—this model focuses on determining **whether market conditions are favorable enough to hold a position** on the next trading day.

By combining well-known technical indicators with a Random Forest Classifier and evaluating performance using **realistic backtesting**, the project demonstrates how data-driven decision-making can help **reduce risk and improve entry/exit timing**, compared to a simple Buy & Hold approach.

---

## Objective

Predict whether the stock will gain **at least +1%** on the next trading day.

| Output | Interpretation | Action |
|--------|---------------|--------|
| 1      | Market conditions favorable | Enter / Stay in the trade |
| 0      | Conditions uncertain or weak | Stay out |

This aligns with real trading behavior:  
**The decision is not “what will the price be?” but “should I be in the market?”**

---

## Features (Technical Indicators Used)

| Indicator | Why This Matters |
|----------|-----------------|
| RSI | Measures momentum to detect overbought/oversold phases |
| MACD & Signal Line | Identifies trend direction and possible reversals |
| 20-Day Moving Average | Short-term trend behavior |
| 50-Day Moving Average | Medium-term trend direction |
| Moving Average Spread | Normalizes price relative to trend strength |

---

## Model Used

**Random Forest Classifier**, chosen because:

- It handles noisy financial time series effectively
- Captures non-linear, interaction-based patterns
- Provides **feature importance**, improving interpretability

**Train/Test Split (Time-Based):**

- First 75% of data → Training
- Last 25% → Testing  
- No shuffling (preserves chronological structure)

---

## Backtesting Approach (Important)

To avoid *future knowledge leakage*, predictions are **shifted forward by one day**:

- Model predicts on day *t*
- Decision is executed on *t+1*

| Strategy | Meaning |
|----------|---------|
| ML Strategy | Invest only when model signals favorable conditions |
| Buy & Hold | Always invested |

This ensures **realistic** performance measurement.



