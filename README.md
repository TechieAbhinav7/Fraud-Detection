# 💳 Fraud Detection Using Machine Learning & Ensemble Models

![Python](https://img.shields.io/badge/Python-3.10-blue)
![Machine Learning](https://img.shields.io/badge/Machine-Learning-orange)
![XGBoost](https://img.shields.io/badge/Model-XGBoost-green)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

---

## 📌 Overview

This project focuses on detecting fraudulent financial transactions using multiple machine learning models and ensemble techniques.

The dataset contains approximately **9 million transactions**, making scalability and imbalance handling key challenges.

The primary objective is to **maximize fraud detection (recall)** while maintaining acceptable precision.

---

## 📊 Problem Statement

Fraud detection is a highly imbalanced classification problem where fraudulent transactions represent a very small fraction of total data.

Key challenges:
- Extreme class imbalance
- Large-scale dataset (~9M records)
- Minimizing false negatives (missed fraud cases)

---

## ⚙️ Data Preprocessing

### 🔹 Sampling Strategy

To handle imbalance and reduce computational cost:

- All fraud cases were retained
- Legitimate transactions were randomly undersampled
- Final ratio maintained at approximately **1 : 1.5 (fraud : legitimate)**

This ensured:
- Reduced training time
- Preservation of fraud patterns
- Balanced learning distribution

---

## 🧠 Feature Selection

Feature importance was evaluated using multiple models:

- Decision Tree  
- Random Forest  
- Extra Trees  
- Gradient Boosting  
- XGBoost  
- Logistic Regression  

### 📌 Final Features Used

- Transaction Amount  
- Transaction Category  
- Transaction Hour  
- Merchant  
- City  
- Customer Age  
- Occupation  
- State  

---

## 🔧 Feature Engineering

### 🌳 Tree-Based Models
- Ordinal Encoding
- Robust Scaling

Models:
- Decision Tree
- Random Forest
- Extra Trees
- Gradient Boosting
- XGBoost

---

### 📈 Linear Models
- One-Hot Encoding
- Robust Scaling

Model:
- Logistic Regression

---

## 🤖 Machine Learning Models

- Decision Tree  
- Random Forest  
- Extra Trees  
- Gradient Boosting  
- XGBoost  
- Logistic Regression  

---

## 🧪 Model Training Strategy

1. Train-test split using `train_test_split`
2. Hyperparameter tuning using:
   - GridSearchCV
   - Cross-validation
3. Evaluation metric:
   - F1 Score (individual models)
   - Recall (ensemble models)
4. Final validation on unseen dataset (`fraudTest`)

---

## 🔀 Ensemble Learning

Weighted voting ensembles were built to improve fraud detection performance.

### Ensemble Variants Tested

- Dual Model Recall Ensemble  
- Tri Model Recall Ensemble  
- Four Model Recall Ensemble  
- Five Model Recall Ensemble  

---

### ⚖️ Weight Optimization

A custom framework was used to:
- Generate valid weight combinations
- Remove redundant configurations
- Normalize equivalent weight sets
- Evaluate ensemble performance

---

### 🎯 Optimization Objective

- Individual models → optimized using **F1 Score**
- Ensembles → optimized using **Recall**

Goal: **Minimize false negatives (missed fraud cases)**

---

## 🏆 Best Performing Model

### ⭐ Dual Model Recall Ensemble

**Models used:**
- XGBoost  
- Extra Trees  

This combination outperformed larger ensembles in recall-based evaluation.

---

## 📈 Final Model Performance (Test Set)

### Confusion Matrix Summary

- True Positives: 2,064  
- False Positives: 10,014  
- False Negatives: 81  
- True Negatives: 543,560  

---

### 📊 Metrics

| Metric | Value |
|--------|------:|
| Recall | **96.22%** |
| Precision | **17.09%** |
| F1 Score | **29.03%** |
| Accuracy | **98.20%** |

---

## 📌 Key Insights

- Model successfully captures **96%+ of fraud cases**
- Low precision is expected due to extreme class imbalance
- System prioritizes **fraud detection over false positive reduction**
- Dual-model ensemble performed better than larger ensembles

---

## 💾 Model Persistence

All trained models were saved using `Joblib` for:

- Fast inference
- Reproducibility
- Efficient experimentation
- Deployment readiness

---

## Limitations & Future Work

- No threshold optimization applied (future improvement)
- Precision-Recall AUC not evaluated
- Class-weighted training not explored on full dataset
- Temporal behavioral features not included
- Advanced anomaly detection methods can improve performance

---

## 🚀 Conclusion

This project demonstrates a scalable fraud detection system using multiple machine learning models and ensemble learning.

The final system achieves **high recall (96.22%)**, making it effective for real-world fraud detection where minimizing missed fraud is critical.

---

## 📂 Tech Stack

- Python
- Pandas, NumPy
- Scikit-learn
- XGBoost
- PySpark (data handling)
- Joblib

---

## Author Notes

Designed as a fraud detection system focusing on **recall optimization in highly imbalanced datasets** with large-scale data processing considerations.
