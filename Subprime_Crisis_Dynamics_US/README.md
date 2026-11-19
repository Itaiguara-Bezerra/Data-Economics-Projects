# From Subprime to the Fall of Lehman Brothers: Delinquency and Financial Stress in the United States

**Author:** Itaiguara de Oliveira Bezerra  
**Portfolio:** [itaiguara-bezerra.github.io](https://itaiguara-bezerra.github.io)  

[![Paper EN](https://img.shields.io/badge/Working%20Paper-English%20PDF-1f425f)](https://github.com/Itaiguara-Bezerra/Data-Economics-Projects/blob/main/Subprime_Crisis_Dynamics_US/macrofinancial_dynamics_2008_crisis_us.pdf?raw=true)
[![Paper PT](https://img.shields.io/badge/Working%20Paper-Portuguese%20PDF-c5a880)](https://github.com/Itaiguara-Bezerra/Data-Economics-Projects/blob/main/Subprime_Crisis_Dynamics_US/dinamica_macrofinanceira_crise_2008_eua.pdf?raw=true)

---

## Overview

This study investigates the dynamic interactions between delinquency across three segments of the US credit market—**consumer credit, credit cards, and mortgages**—and the broader macrofinancial system, with an emphasis on the **2007–2009 Subprime Crisis**.

Continuing the research agenda initiated in [*Retail Credit Default Dynamics in Brazil*](../Credit_Default_Dynamics_BR), this project shifts from individual microdata risk classification to aggregate time-series econometrics and macrofinancial contagion. The empirical strategy bridges classical time-series models with exploratory non-linear machine learning to examine how stress transmitted across credit segments and how the conditional sensitivity of monetary policy evolved during the crisis.

---

## Key Empirical Findings

* **Asymmetric Contagion (Spillover FEVD):** Innovations in mortgage delinquency explain **18.4%** of the forecast error variance in consumer credit and **8.8%** in credit cards, whereas the reverse channel (consumer credit to mortgages) accounts for only **1.8%**.
* **Endogenous Regime Shifts (PELT):** The PELT changepoint algorithm endogenously detects a structural break in mortgage delinquency in **2008Q3**, coinciding with peak systemic stress.
* **Spatial Concentration (NMDB / CFPB):** Severe mortgage delinquency (90+ days past due) in 2008Q3 concentrated heavily in the *Sand States*—led by Florida (3.8%), Nevada (3.5%), California (2.8%), and Arizona (2.5%).
* **Monetary Policy Sensitivity (Rolling-Window VAR):** 48-month rolling estimations reveal heightened conditional sensitivity of the Fed Funds rate to interbank liquidity shocks (TED Spread) during and after the Lehman Brothers collapse. *(Note: this documents increased conditional covariance rather than causal identification of an exogenous structural break in the Federal Reserve's reaction function.)*
* **Non-Linear Vulnerability (Exploratory ML):** K-Means clustering ($k=3$, Silhouette Score: 0.637) and XGBoost with Tree SHAP (strict chronological split: 2000–2015 train / 2016–2026 test) highlight the **Household Debt Service Ratio** (mean $|SHAP| = 0.842$) as the dominant exploratory predictor, with a visual non-linear inflection near the **12%** threshold.

---

## Empirical Architecture

| Stage | Methodology | Frequency | Sample | Horizon / Window |
| :--- | :--- | :--- | :--- | :--- |
| **1. Connectivity** | Generalized Spillover Index (Diebold & Yilmaz, 2012) | Quarterly | 2000Q1–2026Q2 | 8 quarters (FEVD) |
| **2. Persistence & Dynamics** | ARDL-ECM Bounds Testing (Pesaran et al., 2001) | Quarterly | 2005Q1–2026Q2 | Long- & short-run |
| **2. Persistence & Dynamics** | Local Projections with Newey-West SE (Jordà, 2005) | Quarterly | 2000Q1–2026Q2 | 12 quarters |
| **3. Regime Detection** | PELT Algorithm with MBIC Penalty (Killick et al., 2012) | Quarterly | 2000Q1–2026Q2 | Min. 12 quarters |
| **4. Monetary Dynamics** | Rolling-Window VAR (Cholesky, 500 MC reps) | Monthly | 2000M01–2015M12 | 48-month rolling |
| **Appendix A** | Spatial Mapping & Window Robustness (36m–84m) | Quarterly / Monthly | 2008Q3 / 2000–2015 | BIC, RMSFE, Stability |
| **Appendix B** | Exploratory ML: K-Means ($k=3$), XGBoost & SHAP | Quarterly | 2000Q1–2026Q2 | Chronological OOT |

---

## Data Sources

* **Federal Reserve Economic Data (FRED / Federal Reserve Board):** `TEDRATE`, `FEDFUNDS`, `UNRATE`, `DRCLACBS`, `DRCCLACBS`, `DRSFARCBS`, `TDSP`, `DRTSCILM`, `GDPC1`, and `T10Y3M`.
* **Consumer Financial Protection Bureau (CFPB) & FHFA:** National Mortgage Database (NMDB) state-level microdata for 90+ days severe mortgage delinquency (2008Q3).

---

## Reproducibility

1. Clone this repository and install the required Python packages (`pandas`, `numpy`, `statsmodels`, `ruptures`, `scikit-learn`, `xgboost`, `shap`, `matplotlib`, `seaborn`, `fredapi`).
2. Obtain a free API key from the [FRED API portal](https://fred.stlouisfed.org/docs/api/api_key.html).
3. Insert your key in the designated placeholder (or configure it as an environment variable `FRED_API_KEY`) before running the data extraction scripts.

---

## Feedback & Peer Dialogue

This study is open for technical scrutiny—particularly regarding institutional nuances of the US credit market, econometric specification choices, and economic interpretation. Feel free to open an issue or reach out directly via [itaiguara.bezerra@gmail.com](mailto:itaiguara.bezerra@gmail.com).

---

## Disclaimer

Responsibility for the econometric modeling, economic interpretation, writing, and any errors or omissions is exclusively the author's. Artificial intelligence tools were used in a restricted and auxiliary manner for code optimization and LaTeX formatting.
