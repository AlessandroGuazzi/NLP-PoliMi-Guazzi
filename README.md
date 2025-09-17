# Natural Language Processing's Project - A.Y. 2024-2025

## 🚀 Project Overview

This project was developed as part of the **Natural Language Processing** course and focused on applying NLP techniques to a real-world dataset. The assignment required each group to:

* **Work in teams of 4–5 students** to collaboratively analyse and model a publicly available dataset.
* **Develop a Python notebook** that is self-contained and self-explanatory, documenting every step of the analysis, the models implemented, and the conclusions drawn.
* **Record a 5-minute screen-capture video** in which the group presents the notebook, discussing the most interesting parts of the work (without using slides).
* **Submit deliverables** in both `.ipynb` and `.html` format via the course platform, including a link to the presentation video inside the notebook.

---

## 📊 Dataset

We selected the **PubMedQA** dataset:

* Source: [Hugging Face – PubMedQA](https://huggingface.co/datasets/qiaojin/PubMedQA)
* Size: \~273K medical questions with answers extracted from PubMed publications
* Subsets:

  * **PQA-L** (labeled)
  * **PQA-A** (artificially generated)
  * **PQA-U** (unlabeled)

This dataset is designed for **Medical Question Answering**, where the task is to predict an answer (“yes”, “no”, or “maybe”) given a biomedical question and supporting context.

---

## 📝 Project Notebook

The notebook is named **`NLP - Notebook`** and was developed in **Python** using **Google Colab**.
It is divided into several sections:

### 1. Data Import and Preliminary Analysis

* Loading and inspecting the three subsets of PubMedQA
* Data cleaning: lowercasing, stopword removal, punctuation and number removal
* Descriptive statistics: document length, vocabulary size, distributions

### 2. Clustering

* TF-IDF representation of documents
* K-Means and Mini-Batch K-Means clustering on **PQA-U**
* Visualization of intrinsic patterns in the data

### 3. Indexing

* Construction of search indices using **TF-IDF** and **BM25**
* Efficient retrieval of relevant documents for a given query

### 4. Word Embeddings

* Training a **Word2Vec** model on the dataset
* Exploration of semantic relationships between terms
* Visualization of embeddings in 3D

### 5. Models – Classification Task

Goal: classify biomedical questions into **Yes/No** answers

* BiLSTM with custom preprocessing
* BiLSTM with **BioBERT tokenizer**
* **BioBERT** fine-tuning (multiple strategies: Fine-tuning, Transfer Learning, Retraining)
* Evaluation: Accuracy, Precision, Recall, F1-score, ROC curves

### 6. Models – Q\&A Task

Goal: generate natural language answers to biomedical questions

* Testing **LLaMA2** in **zero-shot**, **one-shot**, and **few-shot** settings
* Fine-tuning LLaMA2 on PubMedQA for structured answers (“yes/no” + explanation)
* Evaluation using **ROUGE**, **BERTScore**, and classification metrics

### 7. Extensions

* **Semi-supervised learning**: pseudo-labeling with PQA-U and retraining
* **Interactive Q\&A Chatbot**: a conversational agent for medical question answering

---

## 📈 Results & Key Findings

* Word2Vec embeddings successfully captured biomedical semantic relations
* BiLSTM models provided a solid baseline for classification, but **BioBERT fine-tuning** achieved the best performance
* LLaMA2 showed promising results in few-shot Q\&A, but required fine-tuning to achieve consistent accuracy
* Semi-supervised training with pseudo-labeling further improved classification results
* The interactive chatbot demonstrates practical application of the models

---

## 👥 Group Members

Frageri Martina, Guazzi Alessandro, Lei Leonardo, Mantegazza Niccolò, Moiana Laura
