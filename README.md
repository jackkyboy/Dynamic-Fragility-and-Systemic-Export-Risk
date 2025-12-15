# Dynamic Fragility and Systemic Export Risk

This repository contains the full analytical pipeline for the research project  
**“Dynamic Fragility and Systemic Export Risk: A Route-Level Trade-in-Value-Added Approach”**.

The project develops an **explainable, dynamic risk framework** that links
route-level trade volatility and regime switching to **systemic economic exposure**
through **Domestic Value Added (TiVA)**, with an empirical application to Thailand’s exports.

---

## 1. Research Motivation

Traditional trade risk indicators rely on:
- average volatility,
- static concentration indices, or
- gross trade values.

These approaches fail to distinguish between:
- *structurally fragile routes*,
- *temporarily stable but shock-prone routes*, and
- *truly resilient export channels*.

This project introduces a **Dynamic Fragility framework** that:
1. Models **risk regime transitions** at the route level.
2. Identifies **persistent vs. transitory risk**.
3. Integrates **Trade in Value Added (TiVA)** to measure **systemic economic exposure**.
4. Produces **policy-actionable early warning signals**.

---

## 2. Core Research Questions

### STEP 1 — Foundations & Dynamics
- **Q1:** What are the structural drivers of route-level trade risk?
- **Q2:** Is trade risk related to market size in a non-linear way?
- **Q3:** Which routes are *truly stable* vs. *temporarily stable* (fragile)?
- **Q4:** Did COVID-19 represent a structural break in trade risk dynamics?

### STEP 2 — Systemic Impact & Policy Relevance
- **Q5:** Do high-risk routes coincide with high Domestic Value Added exposure?
- **Q6:** Should policymakers diversify *routes* or *value-added structures*?
- **Q7:** Can Dynamic Fragility function as an early-warning indicator?
- **Q8:** Which export routes should be prioritised for risk mitigation?

---

## 3. Conceptual Framework

### 3.1 Dynamic Risk Regimes
Each export route is classified annually into:
- **LOW**
- **MID**
- **HIGH** risk regimes

Transitions across regimes are explicitly modelled.

### 3.2 Dynamic Fragility
Fragility captures **how easily a route deteriorates**, not just how risky it is on average.

A typical formulation:

\[
Fragility_r
= \alpha \cdot P(LOW \rightarrow HIGH)_r
+ (1-\alpha) \cdot Share(HIGH)_r
\]

This allows identification of:
- **PERSISTENT_RISK** routes,
- **STABLE_TRUE** routes,
- **STABLE_TEMP** (“false-safe”) routes.

---

## 4. Data Sources

### 4.1 Bilateral Merchandise Trade Statistics (BIMTS)
- Source: OECD
- Level: Reporter × Partner × Flow × Year
- Use: Construct route-level trade values and risk dynamics

### 4.2 Trade in Value Added (TiVA) 2025 Edition
- Source: OECD TiVA (EXGR_DVA)
- Coverage: 1995–2022
- Use: Measure Domestic Value Added embodied in exports

---

## 5. Route-Level DVA Allocation

TiVA provides national-level DVA in exports.
To obtain route-level exposure, DVA is allocated using export shares:

\[
DVA_{route,t}
=
DVA^{national}_{t}
\times
\frac{Exports_{route,t}}{\sum_{routes} Exports_{t}}
\]

This produces a **policy-relevant approximation** of DVA exposure by destination.

---

## 6. Systemic Risk Measure

### 6.1 Systemic Export Risk Score

\[
SystemicRisk_{route}
=
Fragility_{route}
\times
DVAExposure_{route}
\]

This formulation captures:
- **Dynamic vulnerability**, and
- **Macroeconomic importance** simultaneously.

### 6.2 Risk–VA Matrix
Routes are classified into four quadrants:
1. High Fragility × High DVA (Systemic Priority)
2. Low Fragility × High DVA (Stable Core)
3. High Fragility × Low DVA (Localised Risk)
4. Low Fragility × Low DVA (Tail Risk)

---

## 7. Policy Simulation

The repository includes simulations that reallocate a fraction of Domestic Value Added
away from high-risk routes toward stable routes.

Results show:
- Route diversification reduces systemic risk,
- But effects are limited unless **structural value-added exposure** is also addressed.

---

## 8. Key Findings (Thailand Case Study)

- Systemic export risk is **not driven by the largest markets alone**.
- Risk arises from the interaction of **fragility and value-added exposure**.
- Post-COVID, much latent fragility has materialised into persistent risk.
- Route diversification helps, but **structural upgrading matters more**.

---

## 9. Repository Structure

Dynamic-Fragility-and-Systemic-Export-Risk/
│
├── data/
│ ├── bimts/ # Bilateral trade data (raw)
│ └── tiva/ # TiVA EXGR_DVA files
│
├── notebooks/
│ ├── 01_route_construction.ipynb
│ ├── 02_dynamic_fragility.ipynb
│ ├── 03_tiva_integration.ipynb
│ └── 04_systemic_risk_analysis.ipynb
│
├── figures/
│ ├── fragility_dva_scatter.png
│ └── risk_va_matrix.png
│
├── results/
│ ├── route_rankings.csv
│ └── policy_simulation.csv
│
└── README.md



---

## 10. Reproducibility Notes

- Python ≥ 3.10
- Key packages: `pandas`, `numpy`, `matplotlib`, `seaborn`
- All results are reproducible using OECD public datasets.

---

## 11. Intended Audience

- Trade economists
- Central banks and ministries
- OECD / WTO / IMF policy teams
- Researchers in systemic risk and supply-chain resilience

---

## 12. Citation

If you use this framework or code, please cite:

> *Janya, A. (2025).*  
> **Dynamic Fragility and Systemic Export Risk: A Route-Level Trade-in-Value-Added Approach.**  
> Working Paper / Policy Note.

---

## 13. Disclaimer

This project is for research and policy analysis purposes only.
The views expressed do not represent any official position of OECD or affiliated institutions.

---
