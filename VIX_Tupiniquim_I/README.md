# VIX Tupiniquim I: PCA & Linear Regularization for Brazilian Financial Stress

## Executive Summary

This repository contains the quantitative pipeline, empirical outputs, and documentation for **VIX Tupiniquim I**, the first module of a broader quantitative framework for analyzing financial stress in Brazil.

Part I focuses on condensing high-dimensional macro-financial risk indicators into parsimonious stress metrics using **Principal Component Analysis (PCA)** combined with **Linear Regularization (LASSO, Ridge, and Elastic Net)**.

---

## Economic Motivation

Financial stress is a multidimensional phenomenon. Domestic credit conditions, monetary policy, sovereign risk, exchange-rate volatility, market liquidity, and global risk appetite may move together while conveying different dimensions of economic stress.

VIX Tupiniquim I investigates whether these signals can be condensed into interpretable and parsimonious measures of Brazilian financial stress using complementary linear approaches.

---

## Methodological Workflow

### 1. Feature Space Definition

Standardized macro-financial time series including bank spreads, system default rates, SELIC Over Rate, Brazil 5Y CDS, yield curve slope, exchange-rate volatility, B3 financial volume, Ibovespa returns, and the Global VIX Index.

The **Economic Confidence Index (ICE)** is used as the economic benchmark for lag identification and supervised estimation.

### 2. Latent Factor Extraction

**Principal Component Analysis (PCA)** is applied to capture common variation and uncover co-movements across domestic and global financial variables.

### 3. Regularized Estimation & Variable Selection

**LASSO, Ridge, and Elastic Net** are calibrated using cross-validation on the training sample (80%).

Model performance is then compared using the **Bayesian Information Criterion (BIC)** on the held-out test set (20%), with LASSO providing the most parsimonious specification.

### 4. Historical & External Comparison

Historical behavior is assessed against Brazilian recession dates established by **CODACE (FGV/IBRE)**.

The resulting indicators are also compared with the **Brazilian Economic Policy Uncertainty (EPU) Index** through visual analysis and Granger causality tests.

---

## Sample

**November 2011 – April 2026 | 162 monthly observations**

---

## Repository Structure

```text
VIX_Tupiniquim_I/
├── README.md
├── VIX_TUPINIQUIM_I_EN.pdf
├── VIX_TUPINIQUIM_I_PT.pdf
├── vix_tupiniquim_pca_lasso_en.ipynb
├── vix_tupiniquim_pca_lasso_pt.ipynb
├── provocation_granger_epu_en.ipynb
├── provocation_granger_epu_pt.ipynb
└── vix_tupiniquim_historical_series.xlsx
