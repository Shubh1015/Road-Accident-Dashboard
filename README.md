# 🚦 Road Accident Analytics Dashboard

[![Excel](https://img.shields.io/badge/Microsoft_Excel-217346?style=flat-square&logo=microsoft-excel&logoColor=white)](https://www.microsoft.com/en-us/microsoft-365/excel)
[![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=flat-square&logo=powerbi&logoColor=black)](https://powerbi.microsoft.com/)
[![Domain](https://img.shields.io/badge/Domain-Public_Safety-orange?style=flat-square)]()
[![Status](https://img.shields.io/badge/Status-Complete-brightgreen?style=flat-square)]()

> A road safety analytics dashboard that dissects accident casualty data by severity, vehicle type, road surface, light condition, and location — enabling traffic authorities and urban planners to identify high-risk patterns and design targeted interventions.

---

## 📌 Problem Statement

Road traffic accidents represent one of the leading causes of preventable death and injury globally. Traffic authorities and urban planners need analytical tools to move beyond raw accident counts toward understanding the *conditions* that make roads dangerous: time of day, road type, vehicle type, weather, and surface condition.

Without a consolidated analytical view, safety interventions are applied broadly rather than being targeted at the highest-risk conditions — reducing their effectiveness and wasting limited public safety resources.

---

## 💡 Solution Overview

The Road Accident Dashboard transforms raw accident records into a decision-support tool. It supports two primary use cases:

1. **Operational reporting** — Year-over-year casualty trends for executive stakeholders
2. **Root cause analysis** — Drill-down by vehicle type, road condition, and location for safety engineers

The dashboard was designed with a focus on **actionability**: every chart answers a specific question that a road safety officer or policy-maker would actually ask.

---

## ✨ Features

- **Executive KPI Summary**:
  - Total Casualties (YTD)
  - Fatal Casualties count and % of total
  - Serious Casualties count and % of total
  - Slight Casualties count and % of total
  - Year-over-Year change for each KPI

- **Monthly Casualty Trend** — Line chart comparing current year vs. prior year by month; highlights seasonal risk peaks

- **Casualties by Vehicle Type** — Breakdown by car, motorcycle, bus, truck, bicycle, pedestrian — shows which road user groups are most vulnerable

- **Road Surface Condition Analysis** — Casualties by dry / wet / icy / flood surface; directly informs gritting and maintenance scheduling

- **Road Type Distribution** — Single carriageway vs. dual carriageway vs. roundabout vs. slip road comparison

- **Light Condition Analysis** — Day / darkness with streetlights / darkness without streetlights; informs streetlight investment decisions

- **Geographic Distribution** — Spatial view of accident hotspots (where location data is available)

---

## 🏗️ Dashboard Architecture

```
Raw Accident Data (CSV / Excel — UK Road Safety Dataset)
          │
          ▼
Data Cleaning Layer (Excel / Power Query)
├── Standardized column names
├── Date parsing: Accident_Date → Date type
├── Null removal: Rows with missing severity excluded
├── Categorical normalization: Vehicle_Type, Road_Surface standardized
└── Derived columns: Year, Month, Quarter, Severity_Group
          │
          ▼
Analytical Model
├── Pivot Tables: Casualties by Severity × Month, Vehicle Type, Road Type
├── Calculated Metrics:
│   ├── Fatal % = Fatal Casualties / Total Casualties
│   ├── YoY Change % = (CY - PY) / PY
│   └── Monthly Rolling Total
└── Slicers: Year, Severity, Vehicle Type, Road Type
          │
          ▼
Dashboard Layout
├── Row 1: KPI Cards (Total, Fatal, Serious, Slight + YoY deltas)
├── Row 2: Monthly Trend Line (CY vs. PY dual-line)
├── Row 3 Left: Casualties by Vehicle Type (horizontal bar)
├── Row 3 Right: Road Surface + Light Condition (donut/bar)
└── Row 4: Road Type distribution + geographic map (if available)
          │
          ▼
Final Output: Excel Dashboard (.xlsx) with embedded charts
```

---

## 🧰 Tech Stack

| Tool | Purpose |
|---|---|
| **Microsoft Excel** | Primary dashboard design, pivot analysis, KPI cards |
| **Power Query** | Data cleaning, column standardization, null handling |
| **Excel Pivot Tables** | Aggregation engine for all charts |
| **Excel Slicers** | Interactive filtering across all dashboard elements |
| **Conditional Formatting** | KPI color-coding (red = worse YoY, green = better) |

---

## 🚀 Getting Started

### Prerequisites

- Microsoft Excel 2016 or later (for full slicer and Power Query support)

### Setup

```bash
git clone https://github.com/Shubh1015/Road-Accident-Dashboard.git
cd Road-Accident-Dashboard
```

Open the Excel workbook. Enable macros if prompted (for slicer refresh).

> **Data Source:** UK Department for Transport road accident data, available at [data.gov.uk](https://www.data.gov.uk/dataset/road-accidents-safety-data)

---

## 📸 Dashboard Preview

![Road Accident Dashboard](Accident%20Dashboard.png)

---

## 📊 Key Analytical Findings

*(Based on UK Road Safety dataset patterns)*

- **Cars** account for the largest share of casualties by vehicle type — reflecting their dominance in overall road usage
- **Single carriageways** are involved in the majority of serious and fatal accidents despite being lower-speed roads — suggesting intersection design and overtaking are key risk factors
- Casualties on **wet road surfaces** are disproportionately represented in serious injury outcomes compared to dry conditions
- **Darkness without streetlights** correlates with a significantly higher fatality rate per accident than daylit conditions — a strong argument for streetlighting investment in rural areas
- **Motorcyclists** have a fatality rate per casualty approximately 3–4x higher than car occupants

---

## 🔮 Future Enhancements

- [ ] Migrate to Power BI for enhanced interactivity and mobile responsiveness
- [ ] Add geographic hotspot clustering (using Power BI Maps or QGIS)
- [ ] Include weather condition data for precipitation-adjusted risk analysis
- [ ] Build a predictive risk score model using historical patterns

---

## 🤝 Contributing

Analytical enhancements and visualization improvements are welcome. Open an issue to discuss before contributing.

---

## 📄 License

MIT License. Road accident data sourced from publicly available UK government open data.

---

## 🏷️ Topics

`excel` `power-bi` `road-safety` `accident-analytics` `public-safety` `data-visualization` `dashboard` `kpi` `business-intelligence` `data-analysis`
