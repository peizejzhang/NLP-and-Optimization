# Spam Detection with Accuracy–Latency Trade-off Analysis

## Overview
This project focuses on detecting spam comments on YouTube channels using content-based machine learning models. Beyond maximizing detection accuracy, the project emphasizes **practical deployment considerations**, particularly the trade-off between predictive performance and inference latency in large-scale spam filtering systems.

---

## Problem Setting
- **Task**: Binary classification  
  - `1`: Spam comment  
  - `0`: Non-spam comment
- **Data**: YouTube comments (text-only, no metadata)
- **Evaluation metric**: F1 score (due to class imbalance)， inference time
- **Validation**: Stratified 10-fold cross-validation

---

## Models and Text Representations
We systematically compared multiple combinations of n-grams, text embeddings and classifiers:

### N-gram Tokenizations
- n from 1 to 10

### Text Embeddings
- Bag-of-Words (BoW)
- TF-IDF
- n-gram representations with varying n

### Classifiers
- Naive Bayes
- Support Vector Machine (SVM)
- Random Forest

The Random Forest model with 5-gram TF-IDF embedding achieved the **highest F1 score of 0.962** among all candidate configurations.

---

## Accuracy–Latency Trade-off Analysis
I reframed model selection as a **multi-objective optimization problem** and developed a **two-axis visualization tool**:
- **x-axis**: Inverse standardized inference time  
- **y-axis**: Standardized F1 score  

This geometric representation allowed us to:
- Identify **Pareto-optimal model–embedding combinations**
- Quantify trade-offs between accuracy and efficiency
- Enable **dynamic model selection** based on platform-specific requirements

---

## Authors and Contributions

This project was completed collaboratively by:

- **Huy Dang** — Topic proposal, model implementation, dataset and preprocessing design, tokenization and text representation methods, n-gram analysis, and conclusion.
- **Peize Zhang** — Accuracy–latency trade-off proposal, model architecture, evaluation metrics, n-gram and text representation comparisons, and overall model performance analysis.
- **Henry Ren** — Data visualization and manuscript revision.
- **Yunshu Zhang** — Introduction, literature review, and references.

The repository preserves the complete commit history of the original collaborative project.
