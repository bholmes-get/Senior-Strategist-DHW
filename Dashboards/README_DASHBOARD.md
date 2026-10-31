# 📊 Dashboard Modeling HTA & Business Case

An executive-level Power BI analytics suite designed to evaluate regional deployment models across healthcare delivery zones. This dashboard synthesizes 10-year financial forecasting with Multi-Criteria Decision Analysis (MCDA) and incremental cost-effectiveness metrics (ICER) to guide strategic healthcare investments.

---

## 💡 Executive Summary

<p align="center">
  <img src="Screenshots/executive-summary.png" width="900px" alt="Executive Summary Dashboard">
</p>

### Key Takeaways
* **Top Performing Region:** **Western Zone (Rank 1)** achieved the highest MCDA score (**66.91**), driven by superior clinical quality scores and strong fiscal accountability.
* **Volume vs. Strategic Alignment:** Western Zone outperformed Central Zone strategically despite Central Zone managing a significantly larger patient volume (**4,180** patients vs. **2,264** in Western Zone).
* **Cohort Scope:** Tracked a total monitored cohort of **2,624 patients** (Year 10 projection) across four key operational zones (Central, Eastern, Northern, Western).

---

## 📈 10-Year Financial Forecast

<p align="center">
  <img src="Screenshots/financial-forecast.png" width="900px" alt="10 Year Financial Forecast Dashboard">
</p>

### Financial Dynamics & Insights
* **Program Investment:** Total estimated 10-year program cost stands at **$19.96M** across labor and equipment expenses.
* **Direct Cost Offset:** Anticipated total savings reach **$7.35M**, heavily weighted toward **Inpatient Admission Savings ($6.43M / 87.53%)** relative to Triage Visit Savings ($0.92M / 12.47%).
* **Net Fiscal Impact:** Net program impact resolves to **($12.61M)** over the 10-year period, reflecting continuous capital and operational investment across deployment phases.

---

## 🧭 Decision Framework & Cost-Utility Trade-Offs

<p align="center">
  <img src="Screenshots/executive-decision-matrix.png" width="900px" alt="Executive Decision Matrix Dashboard">
</p>

### MCDA Score Decomposition
Evaluation criteria evaluate strategic viability across four weighted pillars:
1. **Clinical Quality Score**
2. **Fiscal Accountability Score**
3. **Health Equity Score**
4. **System Sustainability Score**

### Recommendation Categories & Zone Status
* 🟢 **Priority Rollout (Western, Northern, Eastern Zones):** High-performing interventions with top strategic rankings ($\text{MCDA} \ge 50$) and strong cost-effectiveness ($\text{ICER} \le 700$). Recommended for immediate deployment under both Centralized Hub and Decentralized models.
* 🟡 **Phased Implementation (Central Zone):** Requires sequential rollout due to moderate MCDA strategic score (**25.05**) and higher ICER (**767.89**).

---

## 🛠️ Tools & Technologies Used
* **Business Intelligence:** Microsoft Power BI
* **Data Modeling & Analytics:** DAX, Multi-Criteria Decision Analysis (MCDA), Incremental Cost-Effectiveness Ratio (ICER) Modeling
* **Domain Focus:** Healthcare Operations, Financial Forecasting, Strategic Allocation
