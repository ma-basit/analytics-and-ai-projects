# Order Profitability Risk Modeling

## Overview

This project focuses on identifying orders that are likely to generate low or negative profit. While revenue may appear strong, businesses often lose money due to heavy discounts, pricing issues, and low margin products.

The goal of this project is to build a machine learning model to predict profitability risk and understand the key drivers behind it.

---

## Problem Statement

Organizations process thousands of orders across different products, regions, and customer segments. A subset of these orders generates low or negative profit.

This project aims to:
- Predict which orders are risky
- Understand why they become unprofitable
- Identify patterns that impact profitability

---

## Dataset

- Source: Kaggle (DataCo Smart Supply Chain Dataset)
- Contains order level and product-level information
- Includes pricing, discount, customer, and operational features

---

## Approach

### 1. Data Understanding & Cleaning
- Identified data structure and granularity
- Removed irrelevant and leakage columns
- Aggregated data at order level

### 2. Exploratory Data Analysis
- Analyzed profit distribution
- Studied impact of discount, quantity, and pricing
- Identified patterns related to low-profit orders

### 3. Feature Engineering
- Created business-relevant features:
  - Discount percentage
  - Average price per item
  - Discount per item
- Encoded categorical variables

### 4. Modeling
- Logistic Regression (baseline)
- Random Forest (improved model)
- Compared models based on recall, precision, and ROC-AUC

---

## Key Results

- Logistic Regression achieved higher recall (~54%), making it better at identifying risky orders
- Random Forest achieved higher precision but missed many risky orders
- Overall model performance is moderate (ROC-AUC ~0.56)
- There is a clear trade-off between recall and precision across models

---

## Key Insights

- Profitability risk is mainly driven by pricing and discount behavior
- High discounts significantly increase the likelihood of low-profit orders
- Geographic and shipping related features have limited impact

---

## Limitations

- Missing important variables such as product cost and logistics cost
- Moderate model performance due to limited feature richness
- Model performance is not strong enough for direct production deployment

---

## Conclusion

This project highlights the importance of pricing strategy in managing profitability. While machine learning helps identify patterns, data quality and feature availability play a critical role in model performance.

---

## Future Improvements

- Include cost and operational data
- Improve feature engineering
- Build a more robust prediction system
- Add deployment layer (API or UI) if model performance improves

For detailed business insights and conclusions, see [insights.md](insights.md)
