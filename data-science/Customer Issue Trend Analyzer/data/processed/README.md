## Processed Data

This folder contains intermediate datasets created during different stages of the analysis.

The processed files are **not included in this repository** due to their large size.

### Files created during the project

- `complaints_step1_filtered.csv`  
  Cleaned version of the raw dataset containing only relevant columns and complaints with available narrative text. Exact duplicate complaint narratives were removed.

- `complaints_step2_cleaned.csv`  
  Dataset after text preprocessing and normalization, used for feature extraction and modeling.

- `complaints_with_topics.csv`  
  Complaint data with an assigned dominant topic from the LDA topic modeling step. This file is used for trend analysis.

- `tfidf_matrix.pkl`  
  Saved TF-IDF feature matrix generated from complaint text.

- `tfidf_vectorizer.pkl`  
  Saved TF-IDF vectorizer used to transform complaint text into numerical features.

### Note

These files can be recreated by running the notebooks in order:
1. `01_data_understanding.ipynb`
2. `02_text_preprocessing_and_vectorization.ipynb`
3. `03_topic_modeling_lda.ipynb`
4. `04_trend_analysis.ipynb`
5. `05_bert_embeddings_clustering.ipynb`
