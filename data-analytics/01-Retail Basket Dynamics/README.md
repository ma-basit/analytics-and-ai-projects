# Retail Basket Dynamics  
**End-to-End Retail Analytics using SQL, Python, and Tableau**

---

## Project Overview

Retail Basket Dynamics is an end-to-end retail analytics project built on real transactional data.  
The goal of the project is to understand customer behavior, product performance, basket composition, time-based sales patterns, and geographic demand using a realistic analytics workflow.

The project is intentionally structured around concrete business questions rather than open-ended exploratory analysis. Each question is answered using the most appropriate tool (Python or Tableau).

---

## Dataset

- **Source:** Online Retail II transactional dataset  
- **Granularity:** Line-item level transactions  
- **Time span:** December 2009 – December 2011  
- **Scale:** ~1 million rows  
- **Storage:** SQLite database (`retail.db`)  

The dataset contains multi-item invoices, repeat customers, and international transactions, making it suitable for real-world retail analytics.

---

## Business Questions

1. Which customer segments generate the highest revenue and purchase frequency?  
2. Which products are the strongest and weakest performers based on revenue and demand volume?  
3. What time-based patterns affect sales (hour, weekday, month)?  
4. Which product combinations are most frequently purchased together?  
5. Which countries contribute the most revenue, and how does purchasing behavior differ across regions?  
6. How does average basket size vary across time periods and countries?  
7. Which products show strong seasonality versus stable year-round demand?  
8. Which products act as traffic drivers rather than revenue drivers?

---

## Project Structure

    notebooks/
    ├── setup.ipynb
    ├── data_preprocessing_and_feature_engineering.ipynb
    └── insights_and_analysis.ipynb

    data/
    ├── online_retail_II.csv
    ├── retail.db
    └── retail_features.csv

    README.md
    
---

## Notebook 1 — Setup (SQL & Database)

**Objective**  
Create a clean and reliable database-backed data source.

**What was done**
- Loaded raw transactional CSV data into SQLite using SQLAlchemy
- Created a cleaned SQL view to:
  - Remove cancelled invoices
  - Remove negative quantities and prices
  - Remove rows with missing customer IDs
- Verified row counts and schema consistency

This step ensures that all downstream analysis is based on valid transactions only.

---

## Notebook 2 — Data Preprocessing & Feature Engineering

**Objective**  
Create an analysis-ready dataset with meaningful business features.

**Key steps**
- Loaded cleaned SQL data into pandas
- Fixed data types for dates and numeric fields
- Created the core revenue metric:  
  `TotalPrice = Quantity × UnitPrice`

**Feature engineering**
- Time-based features: hour, weekday, month, year
- Basket-level features: invoice total, basket size, unique products per invoice
- Customer-level features: total spend, purchase frequency
- Product-level features: revenue, demand volume
- Country-level features: revenue, customer count, invoice count

**Output**
- `retail_features.csv`  
  This file is used for both Python analysis and Tableau dashboards.

---

## Notebook 3 — Insights & Analysis (Python)

Python is used for analysis that requires:
- Custom logic
- Explicit assumptions
- Reproducible calculations

### Questions Answered Using Python

**Q1. Customer segmentation**
- Identified high-value and low-value customer segments
- Compared revenue contribution and purchase frequency

**Q2. Product performance**
- Identified strongest and weakest products using revenue and demand volume
- Highlighted long-tail product behavior

**Q4. Market basket analysis**
- Identified frequently co-purchased product pairs
- Revealed natural product bundles

**Q8. Traffic driver products**
- Identified products that are frequently purchased but generate relatively low revenue
- Differentiated traffic drivers from revenue drivers

Each analysis includes concise visualizations and written interpretations.

---

## Tableau Dashboards

Tableau is used where **interactive exploration**, **filtering**, and **visual comparison** add value.

All dashboards use `retail_features.csv`.

---

### Dashboard 1 — Time-Based Sales Patterns

**Business Question**  
What time-based patterns affect sales?

**Visuals**
- Monthly revenue trend (line chart)
- Revenue by weekday (bar chart)
- Revenue by hour of day (bar chart)

**Filters**
- Year
- Country

**Purpose**
Shows when sales occur across different time granularities and highlights operationally important periods.

---

### Dashboard 2 — Geographic Revenue & Customer Purchasing Patterns

**Business Question**  
Which countries contribute the most revenue, and how does purchasing behavior differ?

**Visuals**
- Revenue concentration by country (bar chart)
- Revenue by country (map)
- Average invoice value by country (bar chart)

**Filters**
- Year
- Top N Countries (parameter)

**Purpose**
Separates total revenue dominance from average basket value to avoid misleading conclusions.

---

### Dashboard 3 — Average Basket Size Patterns

**Business Question**  
How does average basket size vary across time periods and countries?

**Visuals**
- Average basket size by country (bar chart)
- Average basket size by month (line chart)

**Filters**
- Year
- Top N Countries (parameter)

**Purpose**
Focuses on basket composition rather than revenue, highlighting differences in purchasing behavior.

---

### Dashboard 4 — Product-Level Seasonality Insights

**Business Question**  
Which products show strong seasonality versus stable demand?

**Visuals**
- Monthly revenue trend for Top N products (line chart)
- Monthly revenue heatmap by product (heatmap)

**Filters**
- Year
- Top N Products (parameter)

**Purpose**
Identifies seasonal products and stable year-round sellers using visual pattern recognition.

---

## Key Takeaways

- Revenue is highly concentrated among a subset of customers and products
- Purchasing behavior varies significantly across countries
- Basket size increases toward year-end, indicating seasonal buying behavior
- Some products act as traffic drivers rather than revenue generators
- Product seasonality is clearly visible at the monthly level

---

## Tools & Technologies

- Python (pandas, matplotlib)
- SQL (SQLite)
- SQLAlchemy
- Tableau Public
- Jupyter Notebook

---

## Project Status

This project is complete.

The focus was on:
- Correct metrics
- Transparent assumptions
- Business relevant insights

No predictive modeling or advanced machine learning was intentionally included.
