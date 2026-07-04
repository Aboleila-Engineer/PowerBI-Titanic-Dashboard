# 🚢 Titanic Survival Data Analysis

A complete data analysis project exploring the factors that influenced passenger survival aboard the RMS Titanic, using **Python** for data cleaning & statistical analysis, and **Power BI** for interactive dashboard visualization.

![Status](https://img.shields.io/badge/status-completed-brightgreen)
![Python](https://img.shields.io/badge/Python-Pandas%20%7C%20Matplotlib-blue)
![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-yellow)

---

## 📌 Overview

This project analyzes the well-known Kaggle Titanic dataset to answer a central question:

> **What factors made a passenger more likely to survive the disaster?**

The workflow covers the full data analysis lifecycle — from raw data to a polished, interactive dashboard:

1. **Data Cleaning** — handling missing values (`Age`, `Cabin`, `Embarked`)
2. **Exploratory Data Analysis (EDA)** — statistical breakdown by gender, class, age, and family size
3. **Visualization** — custom charts (Python) + a 3-page interactive Power BI dashboard
4. **Reporting** — a full written report summarizing findings and recommendations

---

## 📸 Dashboard Preview

### Overview
![Overview](Images/overview.png)

### Passenger Analysis
![Passenger Analysis](Images/passenger_analysis.png)

### Destination
![Destination](Images/destination.png)
> *Screenshot pending — add `destination.png` to the `Images/` folder once exported from Power BI.*

---

## 📂 Project Structure

```
titanic-survival-analysis/
│
├── data/
│   ├── train.csv               # Training data (891 passengers, includes Survived column)
│   ├── test.csv                # Test data (418 passengers, no Survived column)
│   └── gender_submission.csv   # Baseline submission (predicts all females survive)
│
├── dashboard/
│   └── titanik.pbix            # Power BI interactive dashboard (3 pages)
│
├── report/
│   └── Titanic_Analysis_Report.docx   # Full written analysis report (Arabic)
│
├── Images/
│   ├── overview.png
│   ├── passenger_analysis.png
│   └── destination.png
│
└── README.md
```

---

## 🗂️ Dataset Description

| Column     | Description                                  | Type             |
|------------|-----------------------------------------------|------------------|
| Survived   | Survival status (0 = No, 1 = Yes)             | Binary           |
| Pclass     | Ticket class (1st, 2nd, 3rd)                  | Categorical      |
| Sex        | Passenger gender                              | Categorical      |
| Age        | Age in years                                  | Numeric          |
| SibSp      | # of siblings/spouses aboard                  | Numeric          |
| Parch      | # of parents/children aboard                  | Numeric          |
| Fare       | Ticket fare                                   | Numeric          |
| Embarked   | Port of embarkation (S, C, Q)                 | Categorical      |

**Missing values:** `Age` (19.9%), `Cabin` (77.1%), `Embarked` (0.2%) — handled via median imputation (Age) and exclusion from deep analysis (Cabin).

**Source:** [Kaggle — Titanic: Machine Learning from Disaster](https://www.kaggle.com/c/titanic)

---

## 🔍 Key Findings

| Insight | Result |
|---|---|
| Overall survival rate | **38.4%** (342 of 891 passengers) |
| Survival rate — Female vs Male | **74.2%** vs **18.9%** |
| Survival rate — 1st vs 3rd Class | **63.0%** vs **24.2%** |
| Survival rate — Children (0–12) vs Seniors (60+) | **58.0%** vs **22.7%** |
| Survival rate — With family vs Alone | **50.6%** vs **30.4%** |
| Highest survival group | 1st Class females — **96.8%** |

**Takeaway:** Survival was not random. Gender, ticket class, and age were the strongest predictors — consistent with the "women and children first" protocol and the physical proximity of higher-class cabins to lifeboats.

---

## 📊 Power BI Dashboard

The `titanik.pbix` file contains a 3-page interactive dashboard:

1. **Overview** — KPI cards, donut chart of survival rate, bar/column charts, slicers (gender, class, embarkation port)
2. **Passenger Analysis** — deeper breakdown with a treemap and extended filtering options
3. **Destination** — analysis by port of embarkation and journey destination

> Open `titanik.pbix` in **Power BI Desktop** to explore the data interactively.

---

## 🧮 DAX Measures Used

```dax
Total Passengers = COUNT(train[PassengerId])

Survivors = SUM(train[Survived])

Deaths = [Total Passengers] - [Survivors]

Survival Rate = DIVIDE([Survivors], [Total Passengers])
```

---

## 🧩 Skills Demonstrated

- Data Cleaning
- Data Transformation
- Data Modeling
- Power Query
- DAX
- Dashboard Design
- Data Visualization
- Business Intelligence
- Storytelling with Data

---

## ⚙️ Dashboard Features

- **KPI Cards** — instant view of total passengers, survivors, deaths, and survival rate
- **Interactive Slicers** — filter by gender, class, embarkation port, and age group
- **Cross Filtering** — selecting a value in one visual dynamically filters all others
- **Multi-page Navigation** — custom buttons to move between Overview, Passenger Analysis, and Destination pages
- **Responsive Layout** — designed for both desktop and mobile Power BI views
- **Interactive Charts** — donut, bar, column, and treemap visuals with tooltips
- **Drill-through** — *(not currently implemented — planned for a future iteration)*

---

## 🌐 Live Dashboard

🚧 **Not available yet.**
This dashboard currently runs locally via **Power BI Desktop**. A published, shareable version (Power BI Service) is planned for a future update.

---

## 🛠️ Tools & Technologies

- **Python** — `pandas`, `matplotlib` (data cleaning, statistical analysis, charting)
- **Power BI Desktop** — interactive dashboard & data visualization
- **CSV / Excel** — raw data storage format

---

## ▶️ How to Reproduce

```bash
# 1. Clone the repository
git clone <repo-url>
cd titanic-survival-analysis

# 2. Install dependencies
pip install pandas matplotlib

# 3. Run the analysis
python analysis.py

# 4. Open the dashboard
# Open dashboard/titanik.pbix using Power BI Desktop
```

---

## 🚀 Future Improvements

- Build a Machine Learning model to predict survival for new passengers
- Extract passenger titles (Mr, Mrs, Master) from the `Name` column as an added feature
- Analyze `Cabin` location data for its effect on survival
- Publish the dashboard to **Power BI Service** for easier sharing
- Add drill-through pages for passenger-level detail

---

## 📄 Report

A full detailed report (in Arabic) with charts, tables, and conclusions is available in [`report/Titanic_Analysis_Report.docx`](report/Titanic_Analysis_Report.docx).

---

## ✍️ Author

Feel free to connect, share feedback, or suggest improvements — always learning! 🙌
