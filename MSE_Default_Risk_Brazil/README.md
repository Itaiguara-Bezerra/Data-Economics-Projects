# Credit Risk & Default Modeling for Brazilian Micro and Small Enterprises (MSEs)
### An Out-of-Time Machine Learning Pipeline with SCR/BACEN Microdata & Tree SHAP Interpretability

[![Author](https://img.shields.io/badge/Author-Itaiguara%20Bezerra-c5a880.svg)](https://itaiguara-bezerra.github.io)
[![Institution](https://img.shields.io/badge/Affiliation-FGV--EPGE%20Alumnus-blue.svg)](https://epge.fgv.br/)
[![Analytics](https://img.shields.io/badge/GA4-Integrated-brightgreen.svg)](https://itaiguara-bezerra.github.io/lab.html)
[![License](https://img.shields.io/badge/License-MIT-lightgrey.svg)](LICENSE)

---

## 1. Executive Summary & Economic Motivation

Micro and Small Enterprises (MSEs / MPEs) constitute the backbone of Brazil's formal employment and business ecosystem. However, they operate with tight liquidity buffers, limited collateral availability, and heightened vulnerability to macroeconomic monetary tightening cycles. 

Traditional credit scoring models aggregated at the national or macroeconomic level systematically obscure profound sectoral, regional, and balance-sheet asymmetries. This project constructs an end-to-end quantitative pipeline to predict and explain credit default transitions across Brazilian MSEs using granular microdata from the **Credit Information System of the Central Bank of Brazil (SCR/BACEN)**.

### Core Methodological Pillars:
1. **Strict Out-of-Time (OOT) Validation:** Temporal data splitting strategy to prevent forward-looking data leakage and rigorously evaluate model generalizability across macroeconomic credit cycles.
2. **Dual Metric Evaluation (ROC vs. PR Curves):** Priority assigned to Precision-Recall (PR-AUC) over standard ROC-AUC, addressing the severe class imbalance inherent to banking credit default datasets.
3. **Model Interpretability via Tree SHAP:** Shapley Additive Explanations (Tree SHAP) applied locally and globally to decompose non-linear feature interactions, guaranteeing macroprudential auditability and alignment with financial economic theory.

---

## 2. Repository Structure & Research Assets

This repository provides reproducible code, curated statistical pipelines, and publication-ready academic documentation in both English and Portuguese:

```text
MSE_Default_Risk_Brazil/
│
├── MSE_DEFAULT_RISK_BRAZIL.pdf     # Full Working Paper (English Version, Parous/Mirror Pagination)
├── INADIMPLENCIA_MPE_BRASIL.pdf    # Texto para Discussão / Paper Completo (Versão em Português)
│
├── mse_default_risk_brazil.ipynb   # Complete Jupyter Notebook / Pipeline (English Architecture)
├── inadimplencia_mpe_Brasil.ipynb  # Caderno Interativo / Pipeline Completa (Arquitetura em Português)
│
└── README.md                       # Technical & Architectural Documentation
