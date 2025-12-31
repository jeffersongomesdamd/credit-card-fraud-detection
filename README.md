# 💳 Credit Card Fraud Detection  
### From Model Performance to Business Impact

## 📌 Project Overview

This project presents an end-to-end machine learning pipeline for detecting fraudulent credit card transactions, with a strong focus on real-world business decision-making.

Rather than optimizing only traditional metrics such as accuracy or ROC-AUC, the project emphasizes:

- Handling highly imbalanced datasets  
- Threshold tuning and decision analysis  
- Risk segmentation  
- Financial cost optimization  

The final goal is to demonstrate how machine learning models can support business decisions, not just generate predictions.

---

## 🎯 Business Problem

Credit card fraud detection is an asymmetric classification problem:

- ❌ **False Negatives (missed fraud)** result in direct financial loss  
- ⚠️ **False Positives (legitimate transactions blocked)** create customer friction and operational cost  

Using a fixed classification threshold (e.g., 0.5) often leads to suboptimal outcomes.  
This project evaluates how adjusting thresholds impacts precision, recall, and total business cost.

---

## 📊 Dataset

- **Source:** Public credit card transactions dataset  
- **Observations:** ~284,000 transactions  
- **Fraud rate:** ~0.17% (highly imbalanced)  
- **Features:**
  - `Time`
  - PCA-transformed variables (`V1`–`V28`)
  - `Amount`
- **Target:**
  - `Class` (0 = Legitimate, 1 = Fraud)

---

## 🧠 Project Structure

```text
├── data/
│   └── creditcard.csv
│
├── notebooks/
│   ├── 01_eda.ipynb
│   ├── 02_modeling.ipynb
│   ├── 03_threshold_analysis.ipynb
│   └── 04_fraud_scoring_business_impact.ipynb
│
├── models/
│   └── best_model.pkl
│
├── Executive_Summary.md
│
└── README.md
```
---

## 🔍 Notebook Breakdown

### 1️⃣ Exploratory Data Analysis (EDA)

- Class imbalance analysis  
- Transaction amount distribution  
- Fraud vs non-fraud behavioral patterns  
- Insights to guide modeling decisions  

---

### 2️⃣ Modeling & Evaluation

Models trained and evaluated:

- Logistic Regression (baseline)
- Random Forest Classifier
- Gradient Boosting Classifier

**Key techniques applied:**

- Stratified train-test split  
- Class imbalance handling  
- ROC-AUC as the primary evaluation metric  

**Best-performing model:** Gradient Boosting Classifier  
The trained model is saved and reused in downstream notebooks.

---

### 3️⃣ Threshold & Decision Analysis

This notebook moves beyond default classification thresholds and explores:

- Precision vs Recall trade-offs  
- False Positives vs False Negatives  
- ROC and Precision-Recall behavior across thresholds  

**Key insight:**  
Lower thresholds significantly improve recall, reducing missed fraud cases at the cost of increased false positives.

---

### 4️⃣ Fraud Scoring & Business Impact

This notebook simulates how the model would be used in production:

- Converts predicted probabilities into **fraud scores (0–100)**  
- Segments transactions into **Low, Medium, and High Risk**  
- Simulates business costs:
  - False Negative: **$500**
  - False Positive: **$5**
- Identifies the **financially optimal decision threshold**

**Result:**  
The optimal threshold is significantly lower than 0.5, minimizing total financial loss.

---

## 💼 Business Takeaways

- The best ML model alone is not sufficient  
- Threshold tuning is a business-driven decision  
- Cost-aware evaluation leads to better outcomes than accuracy alone  
- Machine learning should support decision-making, not replace it  

---

## 🛠️ Tech Stack

- Python  
- Pandas, NumPy  
- Scikit-learn  
- Matplotlib, Seaborn  
- Joblib  

---

## 🚀 How to Run

1. Clone the repository  
2. Create and activate a virtual environment  
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
4. Run the notebooks in order:
- 01_eda.ipynb
- 02_modeling.ipynb
- 03_threshold_analysis.ipynb
- 04_fraud_scoring_business_impact.ipynb

---

## 📎 Final Note

This project reflects a real-world data science workflow by connecting:

   Data → Model → Decision → Business Impact

It is particularly relevant for roles involving:

- Fraud detection
- Risk modeling
- Applied machine learning
- Business-oriented data science

---
