Perfect — I’ll **rewrite the README specifically for the 2nd project folder** in a **clean, portfolio-ready, recruiter-friendly way**, while keeping it **honest to what you actually built** and **not overclaiming**.

This version is **shorter, sharper, and aligned with BI / Data / ML internships**, and it clearly distinguishes this project from your **Tableau + demographics project**.

---

# 📌 `02-ml-sql-attack-prediction`

### Global Terrorism Analysis using SQL, Machine Learning & Power BI

![Python](https://img.shields.io/badge/Python-pandas%20|%20sklearn-blue)
![Power BI](https://img.shields.io/badge/Power%20BI-Dashboards-yellow)
![SQL](https://img.shields.io/badge/SQL-SQLite-green)
![ML](https://img.shields.io/badge/ML-Random%20Forest-red)

---

## 🔍 Project Overview

This project focuses on **advanced analytical and predictive insights** from the **Global Terrorism Database (GTD)** using **SQL, Machine Learning, and Power BI**.

Unlike the first GTD project (Tableau + global indicators), this work emphasizes:

* **Relational SQL analytics**
* **ML-based severity prediction**
* **Power BI dashboards backed by a SQL database**
* **End-to-end analytical pipeline (raw data → insights)**

The goal is to simulate a **real BI / Data Science workflow** used in industry.

---

## 🎯 Objectives

* Build a **structured SQL analytics database** from GTD
* Engineer features for **attack severity classification**
* Train an ML model to **predict attack severity**
* Create **interactive Power BI dashboards** for decision-makers
* Demonstrate **data + ML + BI integration**

---

## 📊 Dataset Summary

| Metric                    | Value               |
| ------------------------- | ------------------- |
| Total Attacks             | 209,706             |
| Time Span                 | 1970 – 2020         |
| Total Fatalities          | 479K+               |
| Total Injuries            | 586K+               |
| Most Affected Country     | Iraq                |
| Most Frequent Attack Type | Bombing / Explosion |

---

## 🧠 Machine Learning Component

* **Model**: Random Forest Classifier
* **Target**: Attack Severity (Low, Medium, High, Extreme)
* **F1-Score**: ~0.65
* **Features**:

  * Casualties (killed, wounded, total)
  * Attack type, weapon type, target type
  * Temporal features (year, month, season)
  * Geographic indicators (country, region)
  * Attack success flag

### Severity Logic

```
Low      → 1–4 casualties
Medium   → 5–19 casualties
High     → 20–50 casualties
Extreme  → >50 casualties
```

---

## 🗄️ SQL Analytics Layer

A **SQLite database** (`gtd_analytics.db`) was designed to support analytical queries and BI reporting.

### Key Tables

* `attacks_core` → Incident-level GTD data
* `attack_summary` → Aggregated yearly & regional metrics
* `predictions` → ML severity predictions & confidence scores

### Example SQL Insight

```sql
SELECT country_txt,
       COUNT(*) AS total_attacks,
       SUM(nkill) AS fatalities
FROM attacks_core
GROUP BY country_txt
ORDER BY fatalities DESC
LIMIT 10;
```

---

## 📈 Power BI Dashboards

### Dashboard Highlights

* **Global attack heatmap**
* **Yearly trends of attacks, fatalities, and injuries**
* **Most affected countries & regions**
* **Attack type and target analysis**
* **ML-based severity distribution**
* **Model performance & feature importance**

All dashboards are **filterable by year, region, attack type, and severity**.

---

## 📁 Project Structure

```
02-ml-sql-attack-prediction/
├── data/
│   ├── raw/                 # Original GTD data
│   └── processed/           # Cleaned datasets & SQLite DB
├── notebooks/
│   ├── data_preprocessing.ipynb
│   ├── sql_analytics.ipynb
│   ├── ml_modeling.ipynb
│   └── powerbi_export.ipynb
├── dashboards/
│   └── powerbi/             # PBIX & CSV files
├── screenshots/             # Dashboard previews
└── README.md
```

---

## 🔑 Key Insights

* **Bombing/Explosion** is the most frequent attack type
* **Private Citizens & Property** are the most targeted
* Peak global activity observed around **2014**
* High-severity attacks strongly correlate with casualty features
* Certain regions show consistently higher lethality despite fewer attacks

---

## 🧩 How This Fits With Project 1

| Project              | Focus                                                              |
| -------------------- | ------------------------------------------------------------------ |
| **Project 1**        | Tableau dashboards + GTD + World Bank indicators (population, GDP) |
| **Project 2 (this)** | SQL analytics + ML prediction + Power BI                           |

➡️ Together, they show:

* **Exploratory + explanatory analytics**
* **Predictive modeling**
* **Multiple BI tools**
* **Strong end-to-end data skills**

---

## 🛠 Tech Stack

* **Python**: pandas, numpy, scikit-learn
* **SQL**: SQLite
* **BI**: Power BI
* **ML**: Random Forest
* **Tools**: Jupyter Notebook

---

## 🔮 Future Improvements

* Handle class imbalance more effectively
* Add explainability (SHAP values)
* Time-series forecasting for attack trends
* NLP on attack summaries
* Deployment as a BI-backed analytics app

---

## 👩‍💻 Team

**NUST SEECS – BS Data Science (Semester 5)**

* Huma Ejaz
* **Rimsha Mahmood**
* Khadija Faisal

---

## 🔗 Related Work

➡️ **Project 1**: Tableau-based GTD + Global Demographics Analysis
`../01-global-demographics-analytics`

---

### ⭐ If you’re a recruiter:

This project demonstrates **SQL analytics, ML modeling, and BI dashboarding in one pipeline** — the exact skill mix expected in **Data, BI, and AI internships**.