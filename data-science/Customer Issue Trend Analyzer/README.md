# Customer Issue Trend Analyzer

## Project Overview

Companies receive large volumes of customer complaints written in free-text form. Reading these complaints manually does not scale and makes it difficult to understand which problems occur repeatedly and which issues are becoming more important over time.

This project analyzes real customer complaint text using Natural Language Processing (NLP) to identify common issue themes and study how these issues change across years. The focus of this project is learning applied NLP and extracting meaningful insights from unstructured data, not building or deploying a production system.

---

## Problem Statement

Organizations receive large volumes of unstructured customer complaints, which makes it difficult to detect recurring issues early and understand which problems are becoming more important.

**Core question:**  
What customer issues recur over time, and which problems are increasing in importance?

---

## Dataset

- **Source:** Consumer Complaint Database (CFPB / Kaggle)
- **Data type:** Unstructured customer complaint text
- **Key characteristics:**
  - Real customer language
  - Time stamped complaints
  - Large scale public dataset

Only complaints with available narrative text were used for NLP analysis.

---

## Approach (High Level)

1. **Dataset Understanding**
   - Explored the dataset structure and size
   - Identified relevant columns for analysis
   - Filtered complaints with narrative text
   - Removed exact duplicate complaint narratives

2. **Text Preprocessing and Vectorization**
   - Applied minimal text normalization
   - Avoided heavy linguistic preprocessing
   - Converted text into numerical features using TF-IDF

3. **Topic Modeling (Primary Analysis)**
   - Applied LDA topic modeling
   - Interpreted and labeled topics manually
   - Assigned a dominant topic to each complaint

4. **Trend Analysis**
   - Aggregated complaints by topic and year
   - Analyzed topic proportions over time
   - Identified persistent, declining, and growing issue categories

5. **Deep Learning Comparison**
   - Used pretrained BERT sentence embeddings
   - Clustered complaints based on semantic similarity
   - Compared embedding-based clusters with LDA topics

---

## Key Outcomes

- Identified recurring customer issue categories such as loan repayment issues, credit reporting disputes, and bank account related problems.
- Observed that **credit reporting and bureau disputes increased over time**, becoming the most dominant issue category in later years.
- Found that **loan and mortgage repayment issues gradually declined**, while **bank account and credit card issues remained consistently significant**.
- Confirmed that BERT embeddings capture semantic similarities in complaints but are less suitable for trend analysis compared to LDA.

---

## Project Structure

CUSTOMER-ISSUE-TREND-ANALYZER/
│
├── README.md
├── analysis_insights.md
│
├── data/
│   ├── raw/
│   └── processed/
|
├── notebooks/
│   ├── 01_data_understanding.ipynb
│   ├── 02_text_preprocessing_and_vectorization.ipynb
│   ├── 03_topic_modeling_lda.ipynb
│   ├── 04_trend_analysis.ipynb
│   └── 05_bert_embeddings_clustering.ipynb

---

## Tools Used

- Python
- pandas
- scikit-learn
- sentence-transformers
- matplotlib

---

## Notes

This project was created for learning purposes by a fresher. The focus is on understanding NLP workflows, making reasonable modeling choices, and carefully interpreting results rather than optimizing models or building production systems.