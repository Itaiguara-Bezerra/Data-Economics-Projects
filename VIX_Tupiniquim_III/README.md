# VIX Tupiniquim III: Financial Stress Modeling via TVP-VAR-SV
### Time-Varying Parameter Vector Autoregression with Stochastic Volatility

[![Python 3.10+](https://img.shields.io/badge/Python-3.10%2B-blue.svg)](https://www.python.org/)
[![Status](https://img.shields.io/badge/Status-Completed-success.svg)]()
[![License](https://img.shields.io/badge/License-MIT-green.svg)]()

---

## 🇬🇧 About the Project

**VIX Tupiniquim III** is the final exercise of the trilogy designed to measure financial stress in the Brazilian economy. The repository contains the implementation of a **TVP-VAR-SV** (*Time-Varying Parameter Vector Autoregression with Stochastic Volatility*) model estimated via Bayesian inference (*Gibbs Sampling* and *Kalman Filtering*).

The model aims to capture structural changes in transmission channels and account for stochastic volatility in macro-financial shocks across the 2003–2026 period.

### Methodological Overview:
* **Time-Varying Coefficients:** Captures evolving dynamics across macro-financial variables.
* **Stochastic Volatility:** Accounts for time-varying innovation variances.
* **Dynamic FEVD:** Time-varying Forecast Error Variance Decomposition.
* **Causality Testing:** Granger and Toda-Yamamoto causality tests against the Economic Policy Uncertainty (EPU) index.

---

## 🇧🇷 Sobre o Projeto

O **VIX Tupiniquim III** é o último exercício da trilogia de mensuração do estresse financeiro na economia brasileira. O projeto implementa um modelo **TVP-VAR-SV** (*Time-Varying Parameter Vector Autoregression with Stochastic Volatility*), estimado via econometria bayesiana (*Gibbs Sampling* e *Filtro de Kalman*).

O objetivo é capturar mudanças estruturais nos mecanismos de transmissão e acomodar a volatilidade estocástica nos choques macrofinanceiros ao longo do período de 2003 a 2026.

### Estrutura Metodológica:
* **Parâmetros Variantes no Tempo:** Coeficientes autorregressivos que evoluem como passeios aleatórios.
* **Volatilidade Estocástica (SV):** Matriz de variância-covariância residual com heterocedasticidade temporal.
* **FEVD Dinâmica:** Decomposição da Variância do Erro de Previsão variante no tempo.
* **Testes de Causalidade:** Não-causalidade de Granger e procedimento de Toda-Yamamoto frente ao índice de incerteza da política econômica (EPU).

---

## 📁 Repository Structure / Estrutura de Arquivos

```text
├── VIX_TUPINIQUIM_III_EN.pdf                    # Technical paper (English)
├── VIX_TUPINIQUIM_III_PT.pdf                    # Artigo técnico completo (Português)
├── vix_tupiniquim_tvp_var_en.ipynb              # Core estimation pipeline notebook (EN)
├── vix_tupiniquim_tvp_var_pt.ipynb              # Notebook de estimação principal (PT)
├── provocation_granger_tvp_var_vs_epu_en.ipynb  # Causality tests Granger / TY (EN)
├── provocation_granger_tvp_var_vs_epu_pt.ipynb  # Testes de causalidade Granger / TY (PT)
├── vix_tupiniquim_iii_historical_series.xlsx    # Historical series dataset (2003–2026)
├── serie_historica_vix_tupiniquim_iii.xlsx      # Série histórica estimada (2003–2026)
└── README.md                                    # Documentação do repositório
