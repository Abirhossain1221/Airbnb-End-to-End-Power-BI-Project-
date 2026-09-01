
# 🏠 Airbnb End-to-End Power BI Project

**Power BI | Power Query | DAX**
 
## 📊 Project Overview

This project is an end-to-end data analytics and business intelligence project focused on analyzing Airbnb booking, revenue, occupancy, pricing, property types, host performance, and customer review trends.

The interactive dashboard was built to provide an executive-level overview of Airbnb business performance and help stakeholders identify important trends across different years, property types, neighborhoods, and hosts.

The project includes two main dashboard pages:

- **Executive Overview**
<img width="778" height="435" alt="Screenshot 2026-09-01 173323" src="https://github.com/user-attachments/assets/c2beaa2e-5263-4a39-9757-787b89c972f2" />

---
 
- **Host & Property Analysis**
<img width="779" height="434" alt="Screenshot 2026-09-01 141547" src="https://github.com/user-attachments/assets/748cfbe3-dc22-444c-870e-9f770ea33875" />
---

## 🎯 Business Objectives

The main objectives of this project are to:

- Analyze total Airbnb revenue and booking performance
- Track revenue trends across different months and years
- Monitor occupancy and cancellation rates
- Compare average nightly rates
- Analyze customer review scores
- Identify high-performing neighborhoods
- Analyze bookings by room and property type
- Compare Superhost and regular host performance
- Evaluate individual host performance
- Understand revenue distribution across different property categories

---

# 📌 Dashboard Preview

## Executive Overview

The Executive Overview dashboard provides a high-level summary of Airbnb business performance.

### Key KPIs

- 💰 Total Revenue
- 💵 Average Nightly Rate
- 🏠 Occupancy Rate
- ⭐ Average Review Score
- ❌ Cancellation Rate

### Key Visualizations

- Monthly revenue trend by year
- Total bookings by neighborhood
- Total bookings by room type
- Monthly occupancy rate
- RevPAR vs Average Nightly Rate

---

## Host & Property Analysis

The Host & Property dashboard provides deeper insights into property categories and host performance.

### Key Visualizations

- Total bookings by property type
- Superhost vs Regular Host bookings
- Superhost vs Regular Host revenue
- Average nightly rate vs review score
- Host performance table
- Revenue analysis by:
  - Neighborhood
  - Room Type
  - Property Type
  - Superhost Status

---
📊 Dashboard Features
Interactive Filters

The dashboard includes interactive slicers for:

Room Type
Year

Users can dynamically filter the dashboard to analyze Airbnb performance across different segments.

---

## 📈 Key Metrics

| Metric | Description |
|---|---|
| Total Revenue | Total revenue generated from Airbnb bookings |
| Total Bookings | Total number of reservations |
| Avg Nightly Rate | Average price per night |
| Occupancy Rate | Percentage of available properties occupied |
| Avg Review Score | Average customer review rating |
| Cancellation Rate | Percentage of cancelled bookings |
| RevPAR | Revenue Per Available Room |

---

# 📊 Key Insights

Some of the business insights generated from the dashboard include:

- Revenue performance varies across different months and years.
- Entire homes/apartments generate a significant portion of total bookings.
- Certain neighborhoods contribute significantly more bookings and revenue than others.
- Superhosts generate a large share of overall Airbnb revenue.
- Property type has a strong relationship with nightly pricing and customer review scores.
- Host performance varies significantly based on booking volume and revenue generation.
- Occupancy rates remain relatively stable throughout the year.
- Premium property types generally have higher average nightly rates.

---
🧮 Exclusive KPI Calculations

Total Revenue Ref Label = VAR _cur = [Total Revenue]
VAR _py = [Total Revenue PY]
VAR _var = _cur - _py
VAR _pct = DIVIDE(_var, ABS(_py))
VAR _arrow = IF(_var >= 0 , UNICHAR(9650), UNICHAR(9660))
VAR  _pctTxt = IF( _var >= 0,"+","") & FORMAT(_pct, "0.0%")
VAR _vartext = IF(_var >= 0 , "+$","-$") & FORMAT(ABS(_var) / 1000000, "0.00") & "M"
RETURN
    _arrow & " " & _pctTxt 
    & "  | PY: $ " & FORMAT(_py/ 1000000, "0.00") & "M"
    & "  | Var: " & _vartext


# 🛠️ Tools & Technologies

| Tool | Purpose |
|---|---|
| **Power BI** | Data visualization and dashboard development |
| **Power Query** | Data transformation and cleaning |
| **DAX** | Data analysis and KPI calculations |
| **Excel / CSV** | Data source and initial data preparation |

---



