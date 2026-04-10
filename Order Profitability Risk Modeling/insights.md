## Business Insights & Conclusion

### Key Findings

- Profitability risk is primarily driven by pricing and discount related factors.
- Features such as discount percentage, total discount, and average price per item have the highest influence on risk.
- Geographic and operational features (region, market, shipping mode) contribute very little in this dataset.

---

### Risk Patterns Observed

- Orders with high discounts are more likely to result in low or negative profit.
- Low-margin orders (low profit despite reasonable sales) contribute significantly to risk.
- Pricing strategy plays a more critical role than location or shipping factors.

---

### Model Insights

- Logistic Regression achieved higher recall (~54%), making it better at identifying risky orders.
- Random Forest achieved better precision but failed to detect many risky orders.
- Both models show moderate performance (ROC-AUC ~0.56), indicating limited predictive power.

---

### Business Recommendations

- Monitor and control high discount orders, as they are a major driver of profitability risk.
- Introduce rules or alerts for orders with unusually high discount percentages.
- Review pricing strategies for products that frequently generate low-profit orders.
- Use model predictions as a support tool rather than a fully automated decision system.

---

### Limitations

- The dataset does not include important variables such as product cost, logistics cost, or operational expenses.
- Model performance is limited by available features rather than algorithm choice.
- The model is not strong enough for direct production deployment.

---

### Final Conclusion

This project demonstrates that predicting profitability risk is challenging with limited data. While meaningful patterns were identified, the models built here provide moderate performance.

With richer data (including cost and operational details), a more reliable and production ready system could be developed.


