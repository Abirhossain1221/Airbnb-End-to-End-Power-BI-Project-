
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


## 🧩 Data Model
The Power BI data model follows a **Star Schema**, with the booking records as the central fact table and supporting dimension tables surrounding it.

FACT TABLE:
-fact_bokings

⬇️ connected to

DIMENSION TABLES:
-dim_host
-dim_property
-dim_location
-dim_date

<img width="874" height="460" alt="Screenshot 2026-09-02 170204" src="https://github.com/user-attachments/assets/828a79dd-d309-46db-8e13-83d06d01bd20" />

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
## 🧮 Key DAX Measures

Below are some of the key DAX measures used in this Power BI project.

### 💰 Total Revenue Reference Label

This measure dynamically compares the current total revenue with the previous year's revenue and displays the percentage change, previous year revenue, and variance.

```DAX
Total Revenue Ref Label =
VAR _cur = [Total Revenue]

VAR _py = [Total Revenue PY]

VAR _var = _cur - _py

VAR _pct = DIVIDE(_var, ABS(_py))

VAR _arrow =
    IF(
        _var >= 0,
        UNICHAR(9650),
        UNICHAR(9660)
    )

VAR _pctTxt =
    IF(_var >= 0, "+", "") &
    FORMAT(_pct, "0.0%")

VAR _vartext =
    IF(_var >= 0, "+$", "-$") &
    FORMAT(ABS(_var) / 1000000, "0.00") &
    "M"

RETURN
    _arrow & " " & _pctTxt
    & " | PY: $" & FORMAT(_py / 1000000, "0.00") & "M"
    & " | Var: " & _vartext
```

### 📊 What this measure displays

Example output:

`▲ +47.4% | PY: $119.25M | Var: +$56.47M`

This allows the KPI card to dynamically show:

- ▲ or ▼ performance indicator
- Percentage increase or decrease
- Previous year revenue
- Revenue variance

### 🎨 Conditional Formatting: Total Revenue Background

This measure dynamically changes the background color of the Total Revenue KPI card based on its performance compared to the previous year's revenue.

```DAX
CF Background - Total Revenue =
IF(
    ISBLANK([Total Revenue PY]),
    "#FFFFFF",
    IF(
        [Total Revenue] >= [Total Revenue PY],
        "#E8F5E9",
        "#FFEBEE"
    )
)
```

### 📊 What this measure does

The measure returns different background colors based on revenue performance:

- 🟢 **Light Green (`#E8F5E9`)** → Current revenue is greater than or equal to previous year revenue.
- 🔴 **Light Red (`#FFEBEE`)** → Current revenue is lower than previous year revenue.
- ⚪ **White (`#FFFFFF`)** → Previous year data is unavailable.

# 🛠️ Tools & Technologies

| Tool | Purpose |
|---|---|
| **Power BI** | Data visualization and dashboard development |
| **Power Query** | Data transformation and cleaning |
| **DAX** | Data analysis and KPI calculations |
| **Excel / CSV** | Data source and initial data preparation |

---


