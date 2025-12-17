# 📉 Economic Cycles & Monetary Distortions: An Austrian Perspective on Brazil (2004-2024)

> **Bachelor's Thesis (TCC) analyzing the applicability of the Austrian Business Cycle Theory (ABCT) to the Brazilian economy.**

[![R](https://img.shields.io/badge/Made_with-R-blue?style=for-the-badge&logo=R)](https://www.r-project.org/)
[![PDF](https://img.shields.io/badge/Read-Full%20Thesis-red?style=for-the-badge&logo=adobeacrobatreader)](TCC%20-%20Ciclos%20Econômicos%20e%20Distorções%20Monetárias%20-%20Uma%20Leitura%20da%20Escola%20Austríaca%20nos%20Últimos%2021%20anos..pdf)
[![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)]()

## 📄 Project Overview

This repository hosts the source code and the final document of my Bachelor's Thesis in Economics presented at **Ibmec**. 

The study investigates whether monetary and credit distortions in Brazil (from 2004 to 2024) generated imbalances in the productive structure, as predicted by **Hayek's Austrian Business Cycle Theory (ABCT)**.

### 📂 Repository Contents

| File | Description |
|------|-------------|
| **[`TCC_Lauro Aguiar.Rmd`](TCC_Lauro%20Aguiar.Rmd.Rmd)** | The **R source code** containing data extraction (APIs), econometric tests (Granger, VAR), and visualization scripts. |
| **[`Full Thesis.pdf`](TCC%20-%20Ciclos%20Econômicos%20e%20Distorções%20Monetárias%20-%20Uma%20Leitura%20da%20Escola%20Austríaca%20nos%20Últimos%2021%20anos..pdf)** | The **complete academic paper** with theoretical framework, literature review, and detailed interpretation of results. |

---

## 🛠️ Methodology & Tech Stack

The analysis was fully reproducible using **R**, integrating automated data collection from official Brazilian sources and robust econometric modeling.

### 1. Data Pipeline (APIs)
Direct extraction of macroeconomic time series using:
* `rbcb`: Central Bank of Brazil (BCB) API.
* `sidrar`: IBGE (Institute of Geography and Statistics) API.
* `BETS`: Brazilian Economic Time Series.

### 2. Econometric Strategy
To test the ABCT hypothesis, the code performs:
* **Stationarity Tests:** ADF (Augmented Dickey-Fuller) and PP (Phillips-Perron).
* **Causality Analysis:** Granger Causality tests to check the relationship between money supply, interest rates, and production.
* **Time Series Decomposition:** Hodrick-Prescott (HP) Filter via `mFilter`.
* **Vector Autoregression (VAR):** Modeling the interdependencies between variables.

### 3. Visualization
* Custom palettes and publication-ready charts using `ggplot2`, `patchwork`, and `scales`.

---

## 📊 Key Findings

This empirical investigation applied the **Toda-Yamamoto (1995)** methodology on **VARX models** (controlling for the Federal Funds Rate) to test Austrian Business Cycle Theory (ABCT) hypotheses in Brazil. The results reveal a complex landscape of **partial validation**:

1.  **The Wicksellian Effect (Validated):**
    The study found significant empirical evidence that the expansion of the **M2 monetary aggregate** temporally precedes the widening gap between the natural interest rate (proxied by savings) and the market rate. This corroborates the intertemporal distortion mechanism postulated by Wicksell and Mises.

2.  **Monetary Transmission (Robust):**
    The most robust results were observed in the transmission channels. Approximately **51.7% of the tested models** (30 out of 58) demonstrated statistical significance when analyzing the relationship between monetary expansion and interest rate spreads.

3.  **Impact on Real Output (Divergent):**
    Contrary to theoretical predictions, models focusing on **Productive Aggregates (GDP and sectoral variations)** did not yield statistically significant results. This suggests that while the monetary transmission to interest rates is evident, its measurable impact on the physical structure of production in Brazil is less clear or overshadowed by other factors.

4.  **Methodological Limitations:**
    * The **"Forced Savings"** hypothesis remained inconclusive due to serial autocorrelation and heteroscedasticity constraints in the credit data.
    * Monetary effects in the Brazilian economy appear to **dissipate faster** than theoretically predicted.

*(For the complete econometric results and theoretical discussion, please refer to the PDF file).*

---

## 📦 Dependencies

To run the analysis locally, ensure you have the following R libraries installed:

```r
install.packages(c("tidyverse", "rbcb", "sidrar", "BETS", "urca", "vars", "tseries", "mFilter", "gridExtra", "patchwork"))
