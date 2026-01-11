# Airline Operational Reliability Analysis

## Project Overview

This is a SQL-first analytics project focused on analyzing airline operational reliability using real-world flight operations data.

The project emphasizes:
- Data modeling with SQL
- Operational KPI design
- Time-based and volume-based analysis
- Industry-style analytics workflow

The dataset is provided as a production-style SQLite database, not pre-cleaned CSV files.

---

## Project Goals

- Analyze airline delays and operational stress patterns
- Design reusable SQL views for operational KPIs
- Validate metrics before visualization
- Communicate insights through Tableau dashboards

The project is intentionally realistic and avoids exaggerated or predictive claims.

---

## Dataset Description

- Source: Airline operations database (`travel.sqlite`)
- Format: SQLite relational database
- Core fact table: `flights`
- Grain: One row per flight

Key fields include:
- Scheduled and actual departure/arrival timestamps
- Departure and arrival airports
- Flight status
- Aircraft code

Missing actual timestamps are stored as the string `'\N'`, reflecting real operational data quality issues.

---

## Tools Used

- **SQLite** — primary data storage  
- **SQL** — KPI logic and data modeling  
- **Python (sqlite3)** — SQL execution only  
- **Excel** — KPI validation and sanity checks  
- **Tableau** — final dashboards and storytelling  

No pandas transformations were used.  
All business logic lives in SQL.

---

## Data Modeling Approach

All analytics are built on a single base SQL view.

### Base Analytical View — `analytics_flights_base`

**Purpose**
- Centralize timestamp normalization
- Handle missing values consistently
- Compute delay metrics once
- Preserve one row per flight

**Key logic**
- Timezone information removed for SQLite compatibility
- Delays computed only for valid, non-cancelled flights
- Departure and arrival delays calculated in minutes

**Validation results**
- Total flights: **33,121**
- Flights with departure delay data: **16,765**
- Flights with arrival delay data: **16,707**

This view acts as the single source of truth for all downstream analysis.

---

## KPI Views Created

### 1. Airport-Level Delay KPIs (`airport_delay_kpis`)
**Business question**  
Which airports experience the highest average delays?

- Aggregates departure and arrival delays by airport
- Reports average delays and flight counts
- Identifies airport-level operational bottlenecks

---

### 2. Time-Based Operational Stress KPIs  
(`time_stress_kpis_month`, `time_stress_kpis_weekday`)

**Business question**  
When are airline operations most stressed?

- Monthly and weekday aggregations
- Highlights seasonal and mid-week stress patterns
- Shows that high volume periods are not always the worst-performing

---

### 3. Volume vs Delay KPIs (`volume_vs_delay_kpis`)
**Business question**  
Is higher flight volume associated with worse on-time performance?

- Daily flight volume compared to average delays
- Reveals weak correlation between volume and delay
- Emphasizes the role of operational execution over congestion

---

### 4. Short-Haul vs Long-Haul Reliability (`haul_reliability_kpis`)
**Business question**  
Do flight types differ in operational reliability?

- Uses aircraft type as a practical proxy for haul length
- Compares average departure and arrival delays
- Includes explicit assumption documentation
- Shows short-haul flights experience slightly higher delays

---

## Excel Validation

Before dashboarding, selected SQL KPI views were exported to a multi-sheet Excel workbook and validated using basic sorting and pivot checks.

Excel was used strictly for:
- Sanity-checking aggregations
- Verifying delay calculations
- Confirming trends observed in SQL

No transformations or recalculations were performed in Excel.  
SQL remains the single source of truth.

---

## Tableau Dashboards

The analysis is presented through multiple Tableau dashboards, each mapped to a specific business question:

1. **Airport Reliability**  
   Identifies airports with the highest average delays.

2. **Time-Based Operational Stress**  
   Shows monthly and weekday delay patterns.

3. **Flight Volume vs Operational Reliability**  
   Demonstrates that higher volume does not consistently lead to higher delays.

4. **Short-Haul vs Long-Haul Reliability**  
   Compares operational performance across flight types and confirms consistency between departure and arrival delays.

Dashboards focus on clarity, minimal filters, and realistic interpretation rather than visual complexity.

---

## Project Status

- SQL data modeling: ✅ Complete  
- KPI views: ✅ Complete  
- Excel validation: ✅ Complete  
- Tableau dashboards: ✅ Complete  

---

## Key Takeaway

Airline delays are driven more by **operational execution, airport constraints, and timing** than by raw flight volume alone.  
A SQL-first approach enables consistent, transparent analysis suitable for real-world operational decision-making.
