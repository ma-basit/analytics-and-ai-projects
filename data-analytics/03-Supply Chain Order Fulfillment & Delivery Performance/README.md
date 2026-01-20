# Supply Chain Order Fulfillment & Delivery Performance  
**Business Intelligence Practice Project (Excel + Power BI)**

## Project Overview
This project analyzes historical supply chain data from **DataCo Global** to understand **order fulfillment performance, delivery delays, and shipping behavior**.

The main objective is to practice **Business Intelligence and dashboard design** by exploring how delivery performance varies across regions, shipping modes, and time, and how delays relate to profitability.

This is a **descriptive analysis project** focused on reporting and insight generation, not prediction or automation.

---

## Business Questions
The analysis is structured around the following questions:

1. How efficiently are orders fulfilled across different regions?  
2. Which shipping modes balance delivery speed and cost most effectively?  
3. How do delivery delays impact profitability?  
4. How do order volumes and delivery performance change over time?  
5. Which regions show high demand but weaker delivery reliability?

Each question is answered using a dedicated Power BI dashboard.

---

## Dataset
**Source:** Kaggle — DataCo Smart Supply Chain Dataset  

**Files used:**
- `DataCoSupplyChainDataset.csv`  
- `DescriptionDataCoSupplyChain.csv`  

**Rows:** 180,520  
**Data type:** Structured transactional data

Each row represents **one order item**.  
Multiple rows can belong to the same order, so aggregation is required for order-level analysis.

---

## Project Scope
- Focused on **order fulfillment, delivery performance, and delays**
- Product-level, customer behavior, and clickstream analysis are intentionally excluded
- Uses **historical data** only for reporting and learning purposes

---

## Tools Used
- **Excel** — basic data validation, formatting, and feature creation  
- **Power BI** — data modeling, simple DAX measures, and dashboards  

No SQL, Python, or machine learning is used in this project.

---

## Work Completed

### Data Understanding
- Reviewed dataset structure and column descriptions
- Identified delivery, geographic, and financial fields relevant to the analysis
- Confirmed that the dataset is at **order-item level**, while dashboards operate at **order level**

---

### Excel Data Preparation
Excel was used only for **basic preprocessing** before loading data into Power BI.

Steps completed:
- Preserved the original dataset
- Removed or hid columns not required for this analysis
- Corrected data types for date and numeric fields
- Created simple derived columns:
  - **Delay Days**
  - **Delay Flag** (On-time vs Delayed)
  - **Delay Severity** (1–2 days late, 3–5 days late)
- Verified delay calculations with basic checks

No aggregation, filtering, or visualization was performed in Excel.

---

### Power BI Analysis
In Power BI, the following steps were completed:
- Created basic DAX measures:
  - Total Orders
  - Total Sales
  - Total Profit
  - Average Delivery Days
  - Delay Rate / On-Time Rate
- Built **five dashboards**, each focused on one business question
- Used bar charts, line charts, scatter plots, tables, and KPI cards
- Focused on clarity and readability rather than complex visuals

---

## Current Status
- Excel preprocessing completed  
- Power BI dashboards completed  
- Insights documented in `dashboard-insights.md`

---

## Notes
This project is part of a learning process to improve:
- Data preparation skills
- Understanding of business metrics
- Dashboard design and storytelling in Power BI

The emphasis is on **clear thinking and correct analysis**, not advanced or automated solutions.
