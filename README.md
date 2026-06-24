# Predicting Involuntary Churn: A Payment Failure Risk Model for Subscription Retention

## 📋 Overview

This project analyzes **involuntary churn** in SaaS businesses — customers who leave due to failed payments, not poor product quality. Using machine learning, I built a model to identify at-risk customers and quantify the financial impact of payment failures on subscription retention.

**Business Impact:** $783,750 annual cost from high-risk churn. Implementing prevention strategies yields 450-600% ROI.

---

## 🎯 Problem Statement

SaaS companies lose customers in two ways:
1. **Voluntary churn** — customer chooses to leave (product quality, competition)
2. **Involuntary churn** — customer *wants* to stay but can't (failed payment, expired card)

**20-40% of all churn is involuntary and preventable.** This project identifies which customers are at highest risk and quantifies the business impact.

---

## 📊 Key Findings

### Risk Segmentation
- **High-Risk Customers (812 people):** 77.2% churn rate
- **Medium-Risk Customers (2,359 people):** 13.3% churn rate  
- **Low-Risk Customers (6,829 people):** 1.2% churn rate

### Financial Impact
- **Current annual churn cost:** $783,750 (revenue loss + reacquisition)
- **Preventing 50% of high-risk churn:** $278,160 net benefit annually
- **ROI of intervention:** 450-600% across 5 recommended strategies

### Recommendations (Prioritized by ROI)
1. **VIP Retention Specialist Program** (600% ROI) — 1-2 weeks to implement
2. **Proactive Payment Dunning** (450% ROI) — 2-3 weeks to implement
3. **Early Churn Warning System** (400% ROI) — 6-8 weeks to implement
4. **Onboarding Improvement** (350% ROI) — 8-12 weeks to implement

---

## 🛠️ Technical Approach

### 1. Data Cleaning
- Removed duplicates (0 found — clean dataset)
- Handled missing values (filled `complaint_type` with "Unknown")
- Encoded categorical features (gender, country, payment method, etc.)
- Scaled numeric features (age, tenure, monthly fees) to 0-1 range

### 2. Machine Learning Model
**Algorithm:** Random Forest Classifier with class weighting

Why Random Forest?
- Handles imbalanced data (only 10.21% churn)
- Identifies non-linear patterns (payment failures don't linearly predict churn)
- Provides feature importance (shows what matters most)

**Class Weighting Adjustment:**
Since churners are rare (10% of data), I penalized the model for missing actual churners 10x more than false alarms. This improved churn detection from 1% recall → 32% recall.

### 3. Model Performance
- **Accuracy:** 83% (correctly predicts 83 out of 100 customers)
- **ROC-AUC:** 0.78 (good discrimination between churners/non-churners)
- **Recall (Churners):** 32% (catches 32 out of 100 actual churners)

### 4. Feature Importance (Top Predictors)
1. **CSAT Score** (0.17) — Customer satisfaction is the strongest signal
2. **Tenure Months** (0.14) — New customers churn more
3. **Avg Resolution Time** (0.038) — Slow support drives churn
4. **Last Login Days Ago** (0.038) — Inactive users are at-risk

---

## 📁 Project Structure










---

## 🚀 How to Run This Project

### Prerequisites
- Python 3.8+
- Git (for cloning)
- Jupyter Notebook or VS Code with Jupyter extension

### Step 1: Clone the Repository
```bash
git clone https://github.com/ekpedemevictor/involuntary-churn-prediction.git
cd involuntary-churn-prediction
```

### Step 2: Install Dependencies
```bash
pip install -r requirements.txt
```

### Step 3: Open the Notebook
```bash
jupyter notebook churn_analysis.ipynb
```

Or in VS Code:
- Open the folder
- Click on `churn_analysis.ipynb`
- Click "Run All" to execute all cells

### Step 4: View Results
- Charts are saved as PNG files in the project folder
- Key findings printed in notebook output
- Full analysis visible in markdown cells

---

## 💡 How to Adapt This Framework

This is a **reusable template** for any SaaS churn analysis:

1. **Replace the dataset** — Use your company's customer data (same column structure)
2. **Adjust assumptions** — Change `monthly_arpu` and `annual_cac` to your business metrics
3. **Re-train the model** — Run all cells; model auto-adjusts to your data
4. **Get new recommendations** — Framework automatically prioritizes by ROI

---

## 📈 Business Applications

- **Customer Success:** Identify at-risk customers for proactive outreach
- **Finance:** Quantify revenue impact of churn; justify retention budget
- **Product:** Understand support/satisfaction gaps causing involuntary churn
- **Executive:** Make data-driven decisions on retention strategy ROI

---

## 🔍 Key Assumptions

- Monthly ARPU: $100/customer
- Annual CAC: $50/customer
- Monthly retention cost: $10/customer
- Dataset represents typical SaaS (B2B software subscription)

Adjust these in the notebook's "Financial Impact" section for your business.

---

## 📚 Data Source

Dataset: [Customer Churn Prediction Business Dataset](https://www.kaggle.com/datasets/miadul/customer-churn-prediction-business-dataset)
- 10,000 customers
- 32 features (demographics, usage, billing, support, churn label)
- No missing values (except complaint_type: 20%)

---

## ✉️ Questions?

This project demonstrates:
- **End-to-end ML workflow** (cleaning → modeling → business analysis)
- **Business acumen** (translating model outputs to financial impact)
- **Communication skills** (explaining technical work to non-technical audiences)

Feel free to fork, adapt, or ask questions.

---

**Author:** Babaloke (Ekpedeme Victor)  
**Date:** June 2026  
**License:** MIT