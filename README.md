# 💳 Fraud Detection System (Machine Learning)

## 📌 Overview
This project presents an end-to-end fraud detection system built on real-world financial transaction data. The system is designed to identify fraudulent transactions in highly imbalanced datasets using advanced machine learning techniques and explainability tools.

---

## 🚀 Problem Statement
Financial fraud detection is a critical challenge due to:
- Extreme class imbalance (~0.17% fraud cases)
- High cost of missed fraud (false negatives)
- Customer friction due to false positives

The goal is to build a robust system that maximizes fraud detection while minimizing false alarms.

---

## 🧱 Project Architecture
Data → Cleaning → Feature Engineering → Modeling → Evaluation → Explainability

---

## 📊 Dataset
- European Card Transactions Dataset
- Total Transactions: 284,807
- Fraud Cases: 492 (~0.17%)
- Features: PCA-transformed (V1–V28), Time, Amount

---

## ⚙️ Key Features

### ✅ Data Preprocessing
- Removed duplicate records
- Validated schema and data integrity
- Handled missing values (none present)

### ✅ Feature Engineering
- Extracted `Hour` from transaction time
- Scaled `Amount` using StandardScaler
- Maintained consistency between training and inference pipelines

### ✅ Handling Class Imbalance
- Stratified train-test split
- Applied class weighting in models
- Evaluated using precision-recall metrics instead of accuracy

---

## 🤖 Models Used

### 🔹 Logistic Regression (Baseline)
- Established initial benchmark
- Highlighted imbalance challenges

### 🔹 Logistic Regression (Class Balanced)
- Improved recall but increased false positives

### 🔹 XGBoost (Final Model)
- Achieved optimal balance between precision and recall
- Tuned using class imbalance ratio (`scale_pos_weight`)

---

## 📈 Model Performance

| Model | Precision | Recall | ROC-AUC |
|------|----------|--------|--------|
| Logistic (Baseline) | 0.85 | 0.59 | 0.95 |
| Logistic (Balanced) | 0.06 | 0.87 | 0.96 |
| **XGBoost** | **0.65** | **0.80** | **0.97** |

---

## 🧠 Explainability (SHAP)

- Identified key drivers of fraud predictions
- Top features: **V14, V4, V12, V10**
- Provided both global and local interpretability

---

## 🔍 Key Insights

- Fraud detection depends on **behavioral patterns**, not just transaction amount
- PCA features (V1–V28) carry significant predictive power
- Threshold tuning is critical for balancing business trade-offs

---

## 💼 Business Impact

- Improved fraud detection recall from **59% → 80%**
- Reduced false positives significantly compared to naive balancing
- Enabled interpretable decision-making for financial systems

---

## 🛠 Tech Stack

- Python
- Pandas, NumPy
- Scikit-learn
- XGBoost
- SHAP
- Matplotlib, Seaborn

---

## 📌 Future Improvements

- Real-time streaming pipeline
- API deployment (FastAPI)
- Model monitoring and drift detection

---
