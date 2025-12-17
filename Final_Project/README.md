# Forecasting Crypto Volatility via Semantic Sentiment 🚀

### A Transformer-Based Approach using FinBERT & PCA

**Course:** AAE 722: Machine Learning in Applied Economic Analysis
**University:** University of Wisconsin-Madison
**Author:** Gary Sun
**Date:** December 2025

---

## 📖 Overview

Cryptocurrency markets are driven by narratives, not just fundamentals. This project integrates **Natural Language Processing (NLP)** with **Financial Econometrics** to quantify the "Semantic Alpha" in social media and predict Bitcoin price volatility.

By extracting deep semantic embeddings from Twitter using **FinBERT** (a financial Large Language Model) and distilling them via **PCA** (Principal Component Analysis), we discovered that **social sentiment leads market prices by approximately 29 days** during the 2021 bubble cycle.

---

## 📊 Key Findings

* **The "Bubble Cycle" Lag:** Semantic sentiment is not synchronous with price; it leads the market by **29 days**, reflecting the time gap between retail euphoria and market correction.
* **Contrarian Indicator:** A strong negative correlation (**-0.76**) was observed between peak sentiment and subsequent price action, suggesting that extreme bullishness on Twitter is a reliable sell signal.
* **High Explanatory Power:** The final ARX (Auto-Regressive with Exogenous input) model achieves an **In-Sample $R^2$ of 0.824**.

<p align="center">
  <img src="images/final_model_fit.png" width="85%" alt="Model Fit">
  <br>
  <em>Figure 1: The ARX model (Red) fitted against actual Bitcoin prices (Black).</em>
</p>

---

## 🛠️ Methodology Pipeline

We constructed an end-to-end Data Science pipeline consisting of three stages:

1. **Extraction (NLP):** Processed raw tweets using `FinBERT` to convert unstructured text into 768-dimensional sentiment embeddings.
2. **Distillation (Unsupervised Learning):** Applied **PCA** to reduce dimensionality and extract the "Dominant Market Narrative" (First Principal Component), filtering out noise.
3. **Prediction (Econometrics):** Built a Linear Lagged Regression model to test the causal relationship between the extracted signal and Bitcoin volatility.

<p align="center">
  <img src="images/discovery.png" width="85%" alt="Lead Lag Analysis">
  <br>
  <em>Figure 2: Lead-Lag Analysis showing the peak correlation at 29 days.</em>
</p>

---

## 💾 Data Availability

Due to GitHub's file size limits (100MB), the full raw dataset (**2.1 GB**) is not hosted directly in this

* **Full Dataset:** To reproduce the full analysis, please download the "Bitcoin Tweets" dataset from Kaggle:
  * [**Download Link: Bitcoin Tweets (Kaggle)**](https://www.kaggle.com/datasets/alaix14/bitcoin-tweets-2016-2019)
  * *Note: Please filter for the 2021 period as described in the notebook.*

---

## 🚀 How to Run

1. **Clone the repository:**

   ```bash
   git clone [https://github.com/garysun-uw/AAE-722-Crypto-Sentiment.git](https://github.com/garysun-uw/AAE-722-Crypto-Sentiment.git)
   cd AAE-722-Crypto-Sentiment
   ```
2. **Install dependencies:**

   ```bash
   pip install -r requirements.txt
   ```
3. **Run the Notebook:**

   ```bash
   jupyter notebook Final_Submission.ipynb
   ```

   > **Performance Note:** Running the FinBERT extraction on the full 2.1GB dataset requires significant computational power (GPU recommended). For a quick demonstration, the notebook is configured to run on the provided `sample_tweets.csv` by default.
   >

---

## 📚 References

1. **Vaswani, A., et al. (2017).** Attention Is All You Need. *NeurIPS*.
2. **Araci, D. (2019).** FinBERT: Financial Sentiment Analysis with Pre-trained Language Models. *arXiv*.
3. **Shiller, R. J. (2019).** *Narrative Economics: How Stories Go Viral and Drive Major Economic Events*. Princeton University Press.
4. **Lim, B., et al. (2021).** Temporal Fusion Transformers for Interpretable Multi-horizon Time Series Forecasting. *International Journal of Forecasting*.

---
