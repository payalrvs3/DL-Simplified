# 🧠 Research Paper Recommendation System

---

# 📑 Abstract

Research papers are continuously increasing across multiple domains, making it difficult for researchers and students to efficiently discover relevant papers. Traditional keyword-based search systems often fail to capture the actual semantic meaning and contextual relationships between research papers.

This project focuses on building an intelligent **Research Paper Recommendation System** using advanced Natural Language Processing (NLP) techniques such as **TF-IDF**, **BERT Embeddings**, **FAISS Similarity Search**, and **Random Forest experimentation**. These techniques help generate context-aware recommendations by understanding the semantic meaning of research paper summaries instead of relying only on exact keyword matching.

The system aims to improve research discovery by providing faster, more relevant, and semantically accurate paper recommendations.

---

# 🌍 Context

With the rapid growth of scientific publications, manually searching for relevant research papers has become increasingly difficult and time-consuming. Researchers often struggle to find papers closely related to their topics of interest due to information overload.

Semantic recommendation systems can address this problem by understanding contextual relationships between papers and retrieving the most relevant research documents efficiently. This project demonstrates how modern NLP and vector similarity techniques can simplify research exploration and improve paper discovery.

---

# ⚙️ Methodology

---

## Project Overview

The Research Paper Recommendation System is designed to recommend semantically similar research papers using text-based analysis and vector similarity search techniques.

The project explores multiple approaches including:

- TF-IDF based recommendation
- BERT semantic embeddings
- FAISS vector similarity search
- Random Forest experimentation

These approaches are implemented to compare recommendation quality, retrieval speed, and semantic understanding.

---

## 📂 Notebooks Included

### 📄 01_preprocessing.ipynb

This notebook performs all preprocessing and cleaning operations on the dataset.

### Operations Performed

- Dataset loading
- Selecting top 5000 rows
- Handling missing values
- Removing duplicates
- Text preprocessing
- Lowercasing
- Removing special characters
- Stopword removal
- Feature preparation

---

### 📄 02_tfidf_model.ipynb

This notebook implements the recommendation system using **TF-IDF Vectorization** and cosine similarity.

### Techniques Used

- TF-IDF Vectorizer
- Cosine Similarity
- NLP text representation

### Functionality

- Converts summaries into TF-IDF vectors
- Computes similarity scores
- Generates research paper recommendations

---

### 📄 03_bert_model.ipynb

This notebook uses **BERT embeddings** for semantic understanding of research papers.

### Techniques Used

- Sentence Transformers
- BERT Embeddings
- Semantic similarity analysis

### Functionality

- Generates contextual embeddings
- Captures semantic meaning
- Produces context-aware recommendations

---

### 📄 04_faiss_search.ipynb

This notebook implements **FAISS-based semantic similarity search** for fast recommendation retrieval.

### Techniques Used

- FAISS Vector Indexing
- Similarity Search
- Nearest Neighbor Retrieval

### Functionality

- Stores vector embeddings efficiently
- Retrieves top similar papers quickly
- Performs scalable semantic search

---

# 🌲 Random Forest Experimentation

Random Forest was also used during experimentation for classification and model evaluation.

### Why Random Forest?

- Handles high-dimensional data efficiently
- Reduces overfitting
- Provides stable performance
- Useful for comparison and experimentation

---

# 📊 Features

- Research paper recommendation
- Semantic similarity search
- NLP-based analysis
- BERT contextual embeddings
- Fast FAISS retrieval
- Multiple recommendation approaches
- Interactive visualizations and EDA

---

# 🛠️ Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- NLP
- TF-IDF
- BERT
- Sentence Transformers
- FAISS

---

# 📌 Notes

- Only the top 5000 rows of the dataset were used for faster experimentation and processing.
- The project is intended for educational and research purposes.
- Multiple recommendation approaches were implemented for performance comparison and semantic analysis.

---

# 🚀 Future Improvements

- Hybrid recommendation models
- Larger dataset support
- Real-time recommendation system
- Improved ranking mechanisms
- Full-stack deployment
- Personalized recommendations

---