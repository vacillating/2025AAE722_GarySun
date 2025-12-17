.# Forecasting Crypto Volatility via Semantic Sentiment 🚀

### A Transformer-Based Approach using FinBERT & PCA
**Course:** AAE 722: Machine Learning in Applied Economic Analysis  
**University:** University of Wisconsin-Madison  
**Author:** Gary Sun

---

## 📖 Overview

Cryptocurrency markets are driven by narratives, not just fundamentals. This project integrates **Natural Language Processing (NLP)** with **Financial Econometrics** to quantify the "Semantic Alpha" in social media and predict Bitcoin price volatility.

By extracting deep semantic embeddings from Twitter using **FinBERT** and distilling them via **PCA**, we discovered that **social sentiment leads market prices by approximately 29 days** during the 2021 bubble cycle.

---

## 📊 Key Findings

* **The "Bubble Cycle" Lag:** Semantic sentiment is not synchronous with price; it leads the market by **29 days**.
* **Contrarian Indicator:** A strong negative correlation (**-0.76**) was observed between peak sentiment and subsequent price action (Smart Money Divergence).
* **High Explanatory Power:** The final ARX model achieves an **In-Sample $R^2$ of 0.824**.

<p align="center">
  <img src="images/final_model_fit.png" width="80%" alt="Model Fit">
  <br>
  <em>Figure 1: The ARX model (Red) fitted against actual Bitcoin prices (Black).</em>
</p>

---

## 🛠️ Methodology Pipeline

We implemented an end-to-end Data Science pipeline:

1.  **Extraction (NLP):** Processed raw tweets using `FinBERT` (a Transformer model pre-trained on financial text) to obtain 768-dimensional embeddings.
2.  **Distillation (Unsupervised Learning):** Applied **PCA (Principal Component Analysis)** to reduce dimensionality and extract the "Dominant Market Narrative" (PC1).
3.  **Prediction (Econometrics):** Built a Linear Auto-Regressive model with Exogenous inputs (ARX) to forecast price dynamics.

<p align="center">
  <img src="images/discovery.png" width="80%" alt="Lead Lag Analysis">
  <br>
  <em>Figure 2: Lead-Lag Analysis showing the peak correlation at 29 days.</em>
</p>

---

