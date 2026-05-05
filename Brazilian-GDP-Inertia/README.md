# The Brazilian GDP in Black and White
**A Portrait of Structural Inertia through Markov Chains and XGBoost (1996-2025)**

This repository contains a technical analysis of the "inertial trap" in the Brazilian economy. By combining Classical Econometrics with Machine Learning, this study maps why the national growth is "addicted" to low altitudes.

## 📊 Key Findings
* **Stagnation Dominance**: There is a **96.3% probability** of the economy remaining in the stabilization/stagnation regime once it enters it.[cite: 8]
* **Recovery Speed**: The expected duration of a stagnation period is approximately **27 quarters (7 years)**.[cite: 8]
* **2026 Projection**: Using XGBoost, the model projects a quarterly growth of **0.43%** for Q1 2026, pointing to an annual ceiling of **1.74%**.[cite: 8]

## 🛠️ Methodology & Vigor Zones
The GDP behavior strata are defined by quarterly variation ($y$):
* **Severe Recession**: $y < -1\%$
* **Stagnation**: $-1\% \leq y < 0.5\%$
* **Structural Inertia**: $0.5\% \leq y \leq 1.5\%$
* **Real Expansion**: $y > 1.5\%$

## 📁 Repository Structure
* `markov-switching-analysis_three_regimes.ipynb`: Complete Python audit script.
* `markov-switching-three-regimes-en.pdf`: Final report (English).
* `markov-switching-three-regimes-pt.pdf`: Relatório final (Português).
* `brazil_gdp-data.xlsx`: Raw data from IBGE.

---
**"One day at a time, with constancy!"** 🥋📊🚀
