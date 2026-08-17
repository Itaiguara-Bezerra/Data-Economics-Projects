# VIX Tupiniquim II: Non-Linear Modeling and Interpretability of Financial Stress

[![Python](https://img.shields.io/badge/Python-3.10%2B-blue.svg)](https://www.python.org/)
[![Status](https://img.shields.io/badge/Status-Completed-success.svg)]()
[![License](https://img.shields.io/badge/License-MIT-lightgrey.svg)]()

This repository contains the full quantitative framework, empirical pipelines, datasets, and technical papers for **VIX Tupiniquim II: Non-Linear Modeling and Interpretability of Financial Stress via Gradient Boosting Machines and SHAP Values**.

---

## 📌 Overview

Building upon **Part I** (Linear Structure & Regularization via PCA, LASSO, Ridge, and Elastic Net), this exercise explores the non-linear dimension of domestic financial stress in Brazil using **Extreme Gradient Boosting (XGBoost)**. 

To overcome the risks of overfitting and economic counter-intuition in small macroeconomic samples ($N = 162$), the architecture embeds structural discipline directly into the tree-building process[cite: 1]:
1. **Monotonic Sign Constraints:** Enforces theoretically consistent directional responses across all macro-financial drivers (e.g., higher interest rates and spreads strictly increase stress).
2. **Structural Interaction Constraints:** Partitions features into distinct economic channels (Sovereign/Monetary vs. Credit/Capital Markets) to prevent spurious inter-block splits.
3. **Game-Theoretic Interpretability (SHAP):** Decomposes individual predictions into additive marginal contributions with exact directional attributions via Cooperative Game Theory[cite: 1].
4. **Temporal Precedence & Causality:** Tests linear informational precedence against the Economic Policy Uncertainty Index (Brazil EPU) via Granger Causality and the Toda-Yamamoto (1995) modified Wald procedure[cite: 1].

---

## 📊 Core Empirical Findings

* **Ablation Study (Predictive Cost of Theory):** Constraining the algorithm with economic theory incurs a deliberate out-of-sample performance cost ($+5.4\%$ RMSE, $+10.3\%$ MAE relative to the unconstrained benchmark), ensuring invariant partial derivatives and eliminating counter-intuitive economic responses out-of-sample.
* **Key Financial Stress Drivers:** Non-financial corporate banking spreads (`Spread PJ`) and the monetary policy rate (`Selic Target`) account for the highest partition gains and the largest average absolute contributions to confidence contractions.
* **Precedence vs. Media Uncertainty:** Granger causality and Toda-Yamamoto tests fail to reject the null hypothesis of non-causality in both directions, confirming that market balance-sheet stress and news-based narrative uncertainty provide complementary, non-redundant macro-financial signals.

---

## 📂 Repository Structure

```text
├── VIX_TUPINIQUIM_II_EN.pdf                       # Technical Paper in English
├── VIX_TUPINIQUIM_II_PT.pdf                       # Artigo Técnico em Português
├── vix_tupiniquim_gradient_boosting_en.ipynb      # Main XGBoost & SHAP Pipeline (English)
├── vix_tupiniquim_gradient_boosting_pt.ipynb      # Pipeline Principal XGBoost & SHAP (Português)
├── provocation_granger_boosting_vs_epu_en.ipynb   # Causality Tests: VIX II vs. EPU (English)
├── provocation_granger_boosting_vs_epu_pt.ipynb   # Testes de Causalidade: VIX II vs. EPU (Português)
├── vix_tupiniquim_ii_historical_series.xlsx       # Output Data: Estimated VIX II Index (English)
├── serie_historica_vix_tupiniquim_ii.xlsx         # Dados de Saída: Série Histórica VIX II (Português)
└── README.md                                      # Repository Documentation
