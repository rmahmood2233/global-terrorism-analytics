# Global Terrorism Analytics: Demographics & Risk (2000–2020)

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Python](https://img.shields.io/badge/python-3.8+-blue.svg)
![Tableau](https://img.shields.io/badge/Tableau-2023+-orange.svg)

## 📊 Project Overview

This project presents a **data-driven exploration of global terrorism patterns (2000–2020)** by integrating the **Global Terrorism Database (GTD)** with **World Bank demographic and economic indicators**. The goal is to move beyond raw incident counts and provide **population-normalized, sector-aware, and economically contextualized insights** through interactive Tableau dashboards.

The project emphasizes **data preprocessing, feature engineering, normalization, and visual storytelling** to support strategic analysis for policy, security, and research stakeholders.

### Key Outcomes

* Analyzed **138,900+ terrorism incidents** across **171 countries**
* Integrated **population and GDP per capita** to normalize risk
* Designed **5 interactive Tableau dashboards** covering time, geography, sectors, and tactics
* Identified peak terrorism period (**2014**) and high-risk regions when adjusted for population

---

## 🎯 Problem Motivation

Many terrorism dashboards rely on **absolute attack counts**, which can:

* Overemphasize populous countries
* Underrepresent risk in smaller or fragile states
* Ignore socioeconomic context
* Mask sector-specific vulnerabilities

This project addresses these gaps by incorporating **population-adjusted metrics, sector analysis, and economic indicators**, enabling a more realistic assessment of global terrorism risk.

---

## 🔍 Research Questions

1. How have global terrorism **frequency and lethality** evolved since 2000?
2. Which regions face the **highest population-normalized risk**?
3. Which **target sectors** are most vulnerable, and how does this vary geographically?
4. What relationship exists between **GDP per capita and terrorism burden**?
5. How have **attack tactics and target–weapon combinations** evolved over time?

---

## 📁 Repository Structure

```
01-global-demographics-analytics/
├── dashboards/
│   └── tableau/              # Tableau workbooks
├── data/
│   ├── raw/                  # Original GTD & World Bank datasets
│   └── processed/            # Cleaned, merged datasets
├── notebooks/                # Data preprocessing & EDA notebooks
├── reports/                  # Project report & presentation
└── screenshots/              # Dashboard previews
```

---

## 🛠️ Data Pipeline & Processing

### Data Sources

* **Global Terrorism Database (GTD)**
  Incidents, targets, attack types, casualties
* **World Bank Indicators**

  * Population (`SP.POP.TOTL`)
  * GDP per capita (`NY.GDP.PCAP.CD`)

### Processing Workflow

1. **Filtering**

   * Restricted analysis to **2000–2020**
   * Selected relevant temporal, geographic, tactical, and casualty fields

2. **Cleaning**

   * Converted GTD missing codes (`-99`) → `0` for casualty counts
   * Standardized categorical nulls as `Unknown`
   * Harmonized country naming across datasets
   * Unified date formats

3. **Feature Engineering**

   * Total casualties (killed + injured)
   * Severity groupings
   * Temporal features (month, quarter, season)
   * Consolidated target sector categories

4. **Integration & Normalization**

   * Joined GTD with World Bank data using **country + year**
   * Created normalized indicators:

     * Attacks per million population
     * Casualties per million population
     * Fatalities per million population

5. **Final Dataset**

   * ~140K clean, analysis-ready incidents
   * Consistent and visualization-optimized

---

## 📈 Key Analytical Findings

### 1️⃣ Temporal Evolution

* **Baseline (2000–2007)**: ~1,500 attacks/year
* **Escalation (2008–2014)**: Rapid increase
* **Peak (2014)**: 9,214 attacks globally
* **Post-2014 Decline**: Reduced frequency but sustained impact

> Global attack success rate remained consistently high (~90%).

---

### 2️⃣ Sector Vulnerability

| Sector            | % of Incidents | Avg Casualties | Insight               |
| ----------------- | -------------- | -------------- | --------------------- |
| Civilians         | 29.5%          | Moderate       | Soft-target strategy  |
| Military & Police | 34.3%          | High           | Insurgency pressure   |
| Aviation          | ~3%            | Very High      | Rare but catastrophic |

**Insight:** Aviation terrorism is low-frequency but extremely high-impact.

---

### 3️⃣ Tactical Patterns

* **Bombing/Explosion**: ~49.6% of incidents
* **Armed Assault**: ~24%
* High-lethality combinations:

  * Explosives + civilians
  * Firearms + security forces

---

### 4️⃣ Seasonal Trends

* Peak activity consistently observed **May–August**
* Likely linked to improved mobility and operational conditions

---

### 5️⃣ Economic Context

* Population-normalized casualties spike during **2014–2016**
* Lower-income regions exhibit **higher relative burden**
* GDP-adjusted analysis reveals vulnerabilities masked by raw counts

---

## 🎨 Dashboard Suite

### Dashboard 1 — Temporal Trends

* Incidents vs casualties over time
* Global success rate
* Seasonal heatmaps
* Aviation incident timeline

### Dashboard 2 — Sector Vulnerability

* Civilian vs state targeting
* Regional sector comparisons
* Aviation risk visualization

### Dashboard 3 — Attack Methodology

* Weapon type distribution
* Target–weapon lethality matrix
* Tactical evolution heatmaps

### Dashboard 4 — Geographic Overview

* Global hotspot map
* Country-level density
* Regional aggregation

### Dashboard 5 — Economic Analysis

* GDP vs terrorism burden
* Population-normalized risk metrics
* Socioeconomic vulnerability comparison

---

## 👥 Intended Stakeholders

| Group                  | Purpose                                      |
| ---------------------- | -------------------------------------------- |
| Policy & Security      | Strategic planning and resource allocation   |
| Sector Security        | Infrastructure and corporate risk assessment |
| Researchers & Analysts | Trend analysis and hypothesis testing        |

---

## 🚀 Getting Started

### Requirements

```bash
Python 3.8+
Tableau Desktop 2023+
Jupyter Notebook
pandas, numpy, matplotlib, seaborn
```

### Steps

```bash
git clone https://github.com/yourusername/global-terrorism-analytics.git
cd global-terrorism-analytics/01-global-demographics-analytics
```

1. Download GTD and World Bank datasets
2. Run preprocessing notebooks
3. Open Tableau dashboards from `dashboards/tableau/`

---

## 📄 License

MIT License

---

## 👨‍💻 Authors

**NUST School of Electrical Engineering & Computer Science**

* Huma Ejaz
* Rimsha Mahmood
* Khadija Faisal

*Data Visualization & Analytics | BSDS (Semester 5)*

---

## 🙏 Acknowledgments

* START Consortium (GTD)
* World Bank Open Data
* NUST SEECS

---

⭐ *If this project was helpful, please consider starring the repository.*

🔗 **Related Project**:
[`02-ml-sql-attack-prediction`](../02-ml-sql-attack-prediction) — ML & SQL–based severity prediction pipeline

