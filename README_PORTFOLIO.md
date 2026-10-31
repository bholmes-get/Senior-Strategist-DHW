# 🏥 Health Strategy & Capital Governance Portfolio
**Brianna Holmes** | Targeted for Senior Strategist, Department of Health and Wellness (DHW), Nova Scotia

This repository operationalizes Nova Scotia’s ***Action Plan for Health*** by bridging health policy, capital allocation governance, data engineering, and executive analytics. It demonstrates an end-to-end framework for evaluating health technology investments, optimizing regional equity, and driving fiscal accountability.

---

## 🎯 Portfolio Architecture & Core Artifacts

```
[ HTA Governance Policy ] ──► [ Strategic Business Case ] ──► [ Python Data Pipeline ] ──► [ Power BI Executive Dashboard ]
   • 4-Stage Lifecycle           • Big 3 Chronic Care            • MCDA Normalization             • Capital Triage Matrix
   • 10-Submetric Rubric         • Nurse Triage (NSNU)           • 10-Yr Cost/Savings Model       • ICER Trade-Off Analysis
```

### 1. Health Technology Assessment (HTA) Framework (`Health Technology Assessment (HTA)/Health Technology Assessment (HTA) Framework - Holmes.pdf`)
* **Governance Workflow:** Establishes a 4-stage pipeline (**Intake $\rightarrow$ Technical Review $\rightarrow$ MCDA Scoring $\rightarrow$ Treasury Board Sign-Off**) for capital investments ($> \$250\text{k}$).
* **Weighted Rubric:** Scores proposals across **Clinical Quality (30%)**, **Fiscal Accountability (30%)**, **Health Equity (25%)**, and **System Sustainability (15%)**.
* **Capital Decision Triage:** Classifies projects into Tier 1 (Accelerated $\ge 85$), Tier 2 (Conditional 65–84), and Tier 3 (Deferral $< 65$).

### 2. Strategic Business Case: Rural Remote Care (`docs/Business_Case_Remote_Care.pdf`)
* **Targeting High-Density Chronic Care:** Focuses on CHF, COPD, and Diabetes in the Northern, Eastern, and Western zones to alleviate Central Zone (HRM) hospital congestion.
* **Nurse-Driven Maximization Model:** Leverages LPN, RN, and NP scopes under the NSNU collective agreement.
* **Software Cost-Avoidance:** Piggybacks on existing provincial software investments (**OPOR** and **Microsoft 365 / Teams for Healthcare**) for a zero-dollar marginal software footprint.
* **Impact:** Cuts ED visits by **22%**, reduces acute LOS by **15%**, avoids **13,000 acute bed days/yr** by Year 10, and yields **\$31.57M in net annual savings**.

### 3. Quantitative Data & Financial Engine (`src/HTA_Pipeline.ipynb`)
* **Object-Oriented Python Pipeline:** Models zone boundaries, disease cohorts, inflation, and NSNU pay scale steps.
* **MCDA Indexing Engine:** Applies Min-Max normalization to calculate composite strategic priority scores (0–100).
* **Automated Data Outputs:** Exports standardized CSV data for downstream BI ingestion (`ns_health_mcda_pillars_output.csv` and `ns_health_10yr_financial_forecast.csv`).

### 4. Interactive BI Executive Dashboard (`docs/Dashboard_Deck.pdf`)
* **Executive Decision Matrix:** Prioritizes high-performing regional investments (**Western Zone: MCDA 66.91, Rank 1**; **Northern Zone: MCDA 57.36, Rank 2**).
* **Cost-Utility & Trade-Off Analytics:** Visualizes ICER vs. MCDA score plots to identify high-value deployments ($< \$50\text{k/QALY}$).

---

## 🛠️ Mapping to DHW Senior Strategist Requirements

| DHW Competency | Portfolio Evidence | Key Impact / Value Delivered |
| :--- | :--- | :--- |
| **Health Policy & Capital Planning** | HTA Framework & Business Case | Standardized provincial governance aligned with the *Action Plan for Health*. |
| **Financial Modeling & TCO** | 10-Year Financial Forecast Engine | Quantified 7-year TCO, ICER thresholds, and multi-million dollar system savings. |
| **Data Analytics & Engineering** | Python Analytics Pipeline | Automated, reproducible data transformations for complex health metrics. |
| **Health Equity & Rural Access** | Zone-Level Regional Modeling | Addressed HRM vs. rural care disparities by prioritizing non-Central zones. |
| **Executive Communication** | Power BI Dashboard Deck | Translated complex quantitative models into executive decision frameworks. |

---

## 🚀 Quick Start (Running the Analytical Pipeline)

```bash
# Clone repository and execute the analytical engine
python src/HTA_Pipeline.py
```
*Outputs generated in `generated/` directory for Power BI refresh.*
