# Flight Delay Propagation Prediction

## Project Overview

This project analyzes and predicts flight delay propagation using operational airline data.

Delay propagation occurs when an aircraft arrives late and that delay spreads to its next scheduled departure. The objective of this project is to understand the drivers of delay propagation and build a predictive model using features available before departure.

The project focuses on:

- Data cleaning and preparation  
- Target definition  
- Feature engineering  
- Exploratory analysis  
- Model training and evaluation  
- Interpretation of results  

---

## Problem Statement

Can delay propagation be predicted using operational information available before a flight departs?

The task is framed as a binary classification problem:

- 1 → Delay propagation occurred  
- 0 → No delay propagation  

The goal is to identify patterns and operational factors that contribute most strongly to delay spread.

---

## Dataset

The dataset used in this project comes from the U.S. Department of Transportation (DOT) On-Time Performance database.

It contains detailed operational records for commercial flights, including scheduled times, actual arrival and departure times, delay components, aircraft tail numbers, airport information, and route distance.

The dataset enables analysis of delay causes and aircraft rotation effects across flight segments.

---

## Project Structure

```
├── data/
│   ├── raw/
│   └── processed/
├── notebooks/
│   ├── 01_data_loading_cleaning.ipynb
│   ├── 02_target_definition.ipynb
│   ├── 03_feature_engineering.ipynb
│   └── 04_modeling_and_evaluation.ipynb
├── modeling_insights.md
└── README.md
```

---

## Methodology

### 1. Data Cleaning
- Removed cancelled and diverted flights
- Removed duplicate records
- Ensured structural consistency

### 2. Target Definition
Delay propagation was defined using the `LateAircraftDelay` column:
- Propagation = 1 if LateAircraftDelay > 0
- Otherwise = 0

The original column was removed to prevent data leakage.

### 3. Feature Engineering
Operational features created include:

- Departure hour  
- Day of week  
- Route distance group  
- Airport hourly traffic (congestion proxy)  
- Previous arrival delay (aircraft rotation effect)  
- Departure delay and 15+ minute indicator  

Feature engineering significantly improved predictive performance.

### 4. Modeling
Models evaluated:
- Logistic Regression  
- Random Forest  

Random Forest achieved the strongest balance between precision and recall.

Key performance (refined model):
- Accuracy ≈ 94%
- ROC-AUC ≈ 0.97

---

## Key Findings

- Departure delay is the strongest driver of propagation.
- Aircraft rotation effects play a major role.
- Time-of-day shows moderate influence.
- Airport-level congestion has weaker impact than aircraft-level factors.
- Weekly patterns and route distance show limited influence.

---

## Limitations

- Weather conditions not explicitly modeled
- Turnaround buffer time not available
- Crew scheduling constraints not included
- Congestion approximated using hourly departure counts
- Model predicts occurrence, not delay magnitude

---

## Tools & Libraries

- Python  
- Pandas  
- NumPy  
- Scikit-learn  
- Matplotlib  

---

## Purpose

This project was developed to explore delay propagation dynamics and demonstrate end-to-end machine learning workflow, from data cleaning to model interpretation.

---

## Note on Data

Raw and processed datasets are not included in this repository due to size constraints.  
See the `data/` folder for additional details.