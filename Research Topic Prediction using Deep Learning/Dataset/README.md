# Research Paper Recommendation System Dataset

## Overview

This project uses a subset of the **arXiv Scientific Research Papers Dataset** to build a **Research Paper Recommendation System** using Natural Language Processing (NLP) techniques.

The dataset contains metadata and summaries of scientific research papers from various research domains.

---

# Dataset Source

Dataset obtained from Kaggle:

https://www.kaggle.com/datasets/sumitm004/arxiv-scientific-research-papers-dataset

---

# Dataset Size Used

The original dataset contains a large number of research papers.

For this project, only the **top 5000 rows** were used to:

- reduce preprocessing time
- improve experimentation speed
- lower memory consumption
- simplify model development

```python
df = df.head(5000)
```

---

# Columns Present in Dataset

| Column Name | Description |
|-------------|-------------|
| `id` | Unique identifier for each research paper |
| `title` | Title of the research paper |
| `category` | Main research category/domain |
| `category_code` | Encoded category label |
| `published_date` | Original publication date |
| `updated_date` | Last updated date |
| `authors` | List of authors |
| `first_author` | Primary/first author name |
| `summary` | Summary/abstract of the research paper |
| `summary_word_count` | Total number of words in summary |

---

# Features Used in Project

The following columns were mainly used for recommendation generation:

- `title`
- `summary`
- `category`
- `authors`

---

# Data Preprocessing Performed

Several preprocessing techniques were applied before training:

- Handling missing values
- Removing duplicate entries
- Text cleaning
- Lowercasing text
- Removing special characters
- Stopword removal
- Tokenization
- TF-IDF Vectorization

---

# Exploratory Data Analysis (EDA)

EDA was performed to better understand the dataset.

Visualizations included:

- Word Cloud of research summaries
- Top frequent words
- Summary length distribution
- Common title words
- Model evaluation graphs

---

# Project Objective

The objective of this dataset is to develop a:

# Research Paper Recommendation System

The system recommends similar research papers based on textual similarity between research summaries and titles.

---

# Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- NLP Techniques
- TF-IDF Vectorizer

---

# Notes

- Only a subset of the original dataset was used.
- This dataset is intended for educational and research purposes only.
- Recommendation quality depends on textual similarity and preprocessing quality.

---

# License

Please refer to the original Kaggle dataset page for licensing and usage terms.