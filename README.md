#  Hybrid Regression-Classification Model for Credit Default Risk

##  Overview

This project tackles a real-world financial problem: **credit default risk analysis**. Rather than stopping at a simple classification (will a borrower default?), we go a step further and estimate the **financial loss** a bank might face by calculating the **Expected Loss**.

> **Expected Loss = P(Default) × Default Amount**

By combining classification and regression, this hybrid machine learning model provides deeper insights for more informed and financially sound decisions.

---

##  Dataset

**Source:** [UCI Credit Card Default Dataset](https://archive.ics.uci.edu/ml/datasets/default+of+credit+card+clients)

-  30,000 rows of anonymized credit card client data
-  Target variable: `default.payment.next.month` (1 = default, 0 = non-default)

---

##  Objectives

1. **Classification:** Predict the probability of default (P(Default))
2. **Regression:** Estimate the financial loss if default occurs (Default Amount)
3. **Combined Metric:** Calculate Expected Loss = P(Default) × Predicted Default Amount

---

## 🛠️ Methodology

###  Data Preprocessing
- Created a new `default_amount` column = `LIMIT_BAL` if defaulted, else 0
- Standardized features with `StandardScaler`
- Handled class imbalance via model evaluation

###  Classification Models
- Logistic Regression
- Random Forest Classifier

**Metrics Used:**
- Accuracy
- Precision / Recall / F1-Score
- ROC-AUC Score

###  Regression Model
- Linear Regression (on defaulters only)

**Metrics Used:**
- RMSE (Root Mean Squared Error)
- R² Score

---

##  Expected Loss Estimation

For each customer:
- **P(Default):** Predicted using Random Forest
- **Default Amount:** Predicted using Linear Regression
- **Expected Loss:** Computed as the product of both

---

##  Visualizations

-  Distribution of Expected Loss (Overall & Defaulters)
-  Top 20 High-Risk Customers by Expected Loss
-  Risk Scatter Plot: Credit Limit vs Expected Loss
-  Correlation Heatmap of Features

---

##  Project Structure
├── Hybrid_Credit_Risk_Model.ipynb # Main notebook
├── UCI_Credit_Card.csv # Dataset
├── README.md # This file
└── output/
└── expected_loss_results.csv # (Optional) Saved top-risk customers


---

## 🚀 Future Work

- Add other regressors like Ridge, SVR
- Use SMOTE for class balancing
- Build a Streamlit dashboard for interactive risk filtering
- Try Gradient Boosting or XGBoost for better accuracy

---

## ✨ Key Takeaways

- A hybrid ML approach reflects real-world credit scoring logic used in banks.
- Combining classification + regression gives richer, risk-based insights.
- Expected Loss is a powerful business metric, not just a prediction.

---

## 🔗 Connect with Me

**Author:** Yashika Gupta  
🎓 Mahindra University, Hyderabad  
🐍 Passionate about ML & AI

---



