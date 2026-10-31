# 🏥 Health Technology Assessment(HTA) & Financial Data Engineering Pipeline

An Object-Oriented Python data pipeline built for Health Technology Assessment (HTA) modeling, Multi-Criteria Decision Analysis (MCDA), and 10-year financial forecasting across Nova Scotia Health zones. 

This repository contains the backend Python modeling engine that processes clinical, operational, labor, and financial parameters into two structured CSV datasets for downstream visual analytics and reporting.

---

## 📌 Data Pipeline Architecture

The script processes raw clinical metrics, collective agreement rate structures, acute care utilization rates, and multi-criteria weights through two distinct computation tracks:

```text
       ┌─────────────────────────────────────────────────────────┐
       │             IntegratedHealthcareHTAPipeline             │
       └────────────────────────────┬────────────────────────────┘
                                    │
           ┌────────────────────────┴────────────────────────┐
           ▼                                                 ▼
┌───────────────────────────────┐         ┌───────────────────────────────┐
│     PART A: MCDA Engine       │         │   PART B: 10-Year Forecast    │
├───────────────────────────────┤         ├───────────────────────────────┤
│ • 4 Regional Health Zones     │         │ • 10-Year Phased Projection   │
│ • 10 Weighted Subcategories   │         │ • Wage Step & Inflation Logic │
│ • Min-Max Score Normalization │         │ • ED Triage & Admission Offsets│
│ • 4 Strategic Pillar Metrics  │         │ • Centralized vs. Regional Ops│
└──────────────┬────────────────┘         └──────────────┬────────────────┘
               │                                         │
               ▼                                         ▼
  `ns_health_mcda_pillars_output.csv`       `ns_health_10yr_financial_forecast.csv`
```

---

## ⚙️ Core Logic & Business Rules

### 1. Labor & Compensation Framework (NSNU Agreement)
* **Base Rates:** Licensed Practical Nurse (`$35.81/hr`), Registered Nurse (`$49.99/hr`), Nurse Practitioner (`$69.52/hr`).
* **Regional Zone Multipliers:** 
  * Central Zone: `1.04` (Tertiary specialization index)
  * Eastern Zone: `0.99`
  * Northern Zone: `0.98`
  * Western Zone: `1.00`
* **Compounding Adjustments:** Calculates dynamic step wage increases across 4-year collective agreement cycles along with standard annual operational inflation (`2.5%`).

### 2. Acute Care Offset Metrics
* **Emergency Department (ED) Visit Base Cost:** `$380.00`
* **Inpatient Admission Base Cost:** `$6,800.00` (based on a 5.2-day average Length of Stay)
* **Preventative Intervention Impact:** Applies an assumed **15% reduction** in ED triage visits and a **20% reduction** in inpatient admissions.

### 3. MCDA Score Normalization
Normalizes subcategory metrics using Min-Max scaling to compute four strategic pillars:
$$\text{Min-Max Benefit Normalization: } N = \frac{x - x_{\min}}{x_{\max} - x_{\min}}$$
$$\text{Min-Max Cost/Utility Normalization: } N = \frac{x_{\max} - x}{x_{\max} - x_{\min}}$$

* **Pillar 1: Clinical Quality Score** (Efficacy, Workflow Impact, Wait Time Mitigation)
* **Pillar 2: Fiscal Accountability Score** (Cost-Utility ICER, TCO, Downstream Offsets)
* **Pillar 3: Health Equity Score** (Geographic Parity, Cultural Inclusivity, System Interoperability)
* **Pillar 4: System Sustainability Score** (Environmental Footprint, Contractual Resilience)

---

## 📂 Generated CSV Schema Specifications

Execution generates a `generated/` directory containing two clean CSV files:

### 1. `generated/ns_health_mcda_pillars_output.csv`

| Column Name | Data Type | Description |
| :--- | :--- | :--- |
| `Zone` | String | Nova Scotia Health Zone (Central, Eastern, Northern, Western) |
| `PatientCohortSize` | Integer | Aggregated patient volume across target conditions |
| `Pillar_1_Clinical_Quality_Score` | Float | Weighted composite score for clinical efficacy and workflow |
| `Pillar_2_Fiscal_Accountability_Score` | Float | Weighted composite score for cost-utility and TCO |
| `Pillar_3_Health_Equity_Score` | Float | Weighted composite score for geographic parity and inclusion |
| `Pillar_4_System_Sustainability_Score` | Float | Weighted composite score for carbon footprint and resilience |
| `Composite_MCDA_Index` | Float | Sum of all four pillar scores (Total index score) |
| `StrategicRank` | Integer | Relative ordinal ranking (1 = Top strategic match) |

### 2. `generated/ns_health_10yr_financial_forecast.csv`

| Column Name | Data Type | Description |
| :--- | :--- | :--- |
| `FiscalYear` | String | Projected year (`Year 1` through `Year 10`) |
| `DeploymentPhase` | String | `Centralized Hub Pilot` (Y1-3) vs. `Decentralized Regional Operations` (Y4-10) |
| `Zone` | String | Target regional health zone |
| `Monitored_Patient_Cohort` | Integer | Total active patients monitored in the program |
| `Operational_Labour_Cost` | Float | Annualized team salary including inflation & regional adjustments |
| `Laptop_Capital_Cost` | Float | Hardware acquisition and cyclic refresh costs |
| `Total_Program_Cost` | Float | Sum of operational labor and capital costs |
| `ED_Triage_Savings` | Float | Financial savings from averted emergency visits |
| `Inpatient_Admission_Savings` | Float | Financial savings from averted hospital stays |
| `Total_Expected_Savings` | Float | Total gross acute care savings |
| `Net_Fiscal_Impact` | Float | Net savings minus program cost (`Savings - Cost`) |

---

## 🚀 Environment & Execution

### Requirements
* Python `3.8+`
* Dependencies: `pandas`, `numpy`

### Running the Pipeline
```bash
# Clone repository
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name

# Install required dependencies
pip install pandas numpy

# Execute script
python HTA_&_Financial_ROI_Modeling_Code.py
```

Upon completion, output files will be written to `./generated/`.

Thanks for checking out my code!
