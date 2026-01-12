# Retail Basket Dynamics

## Project Overview
This project explores retail transaction data to understand customer purchasing behavior, product performance, and time-based sales patterns.  
The goal of the project is to practice **end-to-end data analytics**, starting from raw data exploration to dashboard-based insights.

This project was completed as a learning exercise to strengthen practical skills in SQL, Python, and Tableau.

---

## Objectives
- Understand customer purchasing patterns and basket composition  
- Analyze product performance and revenue contribution  
- Identify time-based trends in sales activity  
- Practice feature engineering and aggregation logic  
- Communicate insights using Tableau dashboards  

---

## Dataset
- **Name:** Online Retail II Dataset  
- **Source:** Public dataset (UCI / Kaggle mirror)  
- **Type:** Transaction-level retail data  

> Raw datasets are not included in this repository due to file size constraints.  
> Dataset source and usage details are documented for reproducibility.

---

## Key Questions Explored
- Which customers and products contribute most to revenue?  
- How do sales vary across time (hour, weekday, month)?  
- How does basket size differ across countries and time periods?  
- Which products show seasonal versus stable demand?  

---

## Deliverables
- Cleaned and feature-engineered datasets (local)  
- SQL queries for aggregation and KPI creation  
- Python notebooks for analysis  
- Tableau dashboards with supporting insights  

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

Dashboard screenshots and explanations are provided in a separate Markdown file.

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
## Learning Outcomes
- Improved understanding of transactional data analysis  
- Hands-on practice with SQL and Pandas  
- Experience designing dashboards for business interpretation  
- Better understanding of how analytics supports business questions  

---

## Notes
This project focuses on **learning and practice** rather than production-level optimization.  
The analysis is descriptive and exploratory in nature.
No predictive modeling or advanced machine learning was intentionally included.


