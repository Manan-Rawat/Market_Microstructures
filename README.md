# 📊 Market Microstructure Modeling and Simulation

This repository explores market microstructure using limit order book (LOB) data from cryptocurrencies (BTC, ETH, ADA). It covers data preprocessing, order flow dynamics, statistical dependencies, price impact, and strategy design using stochastic models like Fokker-Planck processes. The goal is to build intuition and tools for high-frequency trading research and prototyping.

---

## 📁 Overview of Modules

### 1. `crypto_lob_preprocessing_and_analysis_1753676291.pdf` – **LOB Feature Engineering**
This notebook analyzes 1-minute crypto limit order book data (BTC, ETH, ADA), estimating tick sizes, bid-ask spreads, and market activity flows. It visualizes normalized spreads and order activity across depth levels, includes CDFs of order sizes, and explores liquidity patterns. The study offers rich diagnostics of microstructure behavior and order dynamics in the context of digital asset markets. 

---

### 2. `Queue_Dynamics_using_Fokker_Planck_dynamics_1753676289.pdf` – **Queue Depth and FP Dynamics**
This document applies stochastic modeling, particularly Fokker-Planck dynamics, to analyze and forecast cryptocurrency order book volumes. Using high-frequency Bitcoin tick data, it constructs bid-price distances, estimates volume dynamics through a rolling CIR (Cox-Ingersoll-Ross) process, and simulates queue evolution. It blends time-series regression and numerical stochastic simulation to model and predict liquidity behavior in financial microstructure.

---

### 3. `Autocorrelation_and_Hawkes_1753676289.pdf` – **BTC 1-Second Sign Autocorrelation**
This document explores trade sign autocorrelation and order flow modeling using high-frequency Bitcoin data. It calculates the Hurst exponent, fits a power-law to autocorrelations, and implements a DAR (Discrete Auto-Regressive) model to simulate and predict trade behavior. A simple alpha strategy based on predicted sign returns is tested, revealing insights into market microstructure memory and order flow clustering.

---

### 4. `PriceImpact_1753676290.pdf` – **BTC Metaorder Detection and Price Impact**
This notebook analyzes market impact of metaorders on Bitcoin, Ethereum, and Cardano using high-frequency limit order book data. It identifies directional trading windows based on volume imbalance and fits power-law models between price impact and order flow intensity. By extracting and filtering metaorders, the study reveals how price impact scales with net volume-to-total volume ratios, across crypto assets.
---

### 5. `ADA1_1753676291.pdf` – **ADA 5-Minute FP Strategy with Walk-Forward Validation**
Implements a Fokker-Planck model using Order book features as the input signal. Trains models on rolling windows, selecting the best one on validation segments. Evaluates three strategies: FP-based, Buy & Hold, and No Position Change — across different transaction cost scenarios.

---

### 6. `BTC1_1753676291.pdf` – **BTC 5-Minute FP with Rolling Selection**
Applies the same FP modeling framework as ADA1 but to BTC. Features walk-forward model selection using validation PnL, and comprehensive test evaluation across fee/slippage combinations. Produces PnL comparisons between FP, Buy & Hold, and passive NPC strategies, showing strategy robustness.

---

### 7. `ETH1_1753676290.pdf` – **ETH 5-Minute FP Strategy**
Implements the simplified FP signal model using Order book features as the primary driver. Applies the same segment-wise training, threshold optimization, and cost-aware evaluation as in BTC and ADA cases. Results validate that this modeling framework generalizes well to ETH market behavior.

---

### 8. `1_min_1753676290.pdf` – **ADA 1-Minute FP Strategy**
A more complex FP model for ADA at 1-minute resolution. Uses 10+ features including OBI, depth, and queue slope. Models signal with a stochastic differential equation, optimized using CMA-ES. Simulates trading strategy and evaluates it under transaction costs using rolling validation.

---

### 9. `5_Min_1753676290.pdf` – **BTC 5-Minute FP Strategy with Full Features**
Applies the full-feature FP modeling pipeline to BTC. Uses a rich feature set and stochastic simulation of signals. Evaluates strategy via rolling training/validation/testing split with transaction costs. This version is closest to a production-grade prototype for testing high-frequency strategies.

---

## 📈 Run the Models

Each module can be executed as a script or converted into a Jupyter notebook:

```python
