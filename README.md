# Customer-Churn-Prediction-
# 📊 Customer Churn Prediction using Logistic Regression & SHAP Explainability

## Project Overview

Customer churn is one of the most critical business problems faced by subscription-based companies such as telecom providers, banks, insurance companies, and SaaS platforms. Acquiring a new customer is significantly more expensive than retaining an existing one.

The objective of this project is to build an interpretable Machine Learning model capable of predicting whether a customer is likely to leave the telecom company (churn) based on demographic information, service subscriptions, billing information, and customer behavior.

Unlike many churn prediction projects that focus solely on prediction accuracy, this project also emphasizes **model interpretability** using **SHAP (SHapley Additive Explanations)** to understand *why* the model predicts churn for individual customers.

---

# Business Problem

Telecom companies lose significant revenue when customers discontinue their services.

The objective is to identify customers at high risk of churn **before they actually leave**, allowing the company to proactively:

- Offer personalized discounts
- Improve customer support
- Upgrade service quality
- Launch retention campaigns

A highly interpretable model is preferred since business managers need to understand the reasons behind each prediction.

---

# Dataset

**Dataset:** IBM Telco Customer Churn Dataset

The dataset contains information about telecom customers including:

- Demographic Information
- Internet Services
- Phone Services
- Billing Information
- Contract Details
- Customer Tenure
- Payment Methods

Target Variable:

**Churn**

- Yes
- No

---

# Features Used

The dataset contains features such as:

### Customer Information

- Gender
- Senior Citizen
- Partner
- Dependents
- Tenure

### Telecom Services

- Phone Service
- Multiple Lines
- Internet Service
- Online Security
- Online Backup
- Device Protection
- Tech Support
- Streaming TV
- Streaming Movies

### Billing Information

- Contract Type
- Paperless Billing
- Payment Method
- Monthly Charges
- Total Charges

---

# Data Preprocessing

The following preprocessing steps were performed:

- Missing value handling
- Converted TotalCharges from object to numeric
- One-Hot Encoding for categorical variables
- Removed multicollinearity using drop_first=True
- Standardized numerical features using StandardScaler
- Train-Test Split

---

# Why Logistic Regression?

Although several tree-based ensemble models were explored, Logistic Regression provided:

- Better ROC-AUC
- Better calibrated probabilities
- Higher interpretability
- Simpler decision boundaries
- Easier business explanation

Logistic Regression models the probability of customer churn using the sigmoid function:

P(churn)=σ(wTx+b)

where

- w = learned feature weights
- x = customer feature vector
- b = bias term

The weights are learned by minimizing Binary Cross Entropy Loss using maximum likelihood estimation.

---

# Model Performance

| Metric | Score |
|---------|-------|
| Accuracy | 76.19% |
| Precision | 53.99% |
| Recall | 70.59% |
| F1 Score | 61.18% |
| ROC-AUC | 0.832 |

Since churn prediction is an imbalanced classification problem, **ROC-AUC** and **Recall** were prioritized over accuracy.

---

# Model Interpretation using SHAP

One of the major objectives of this project was to understand **why** the model predicts churn.

SHAP (SHapley Additive Explanations) was used to explain both:

- Global Feature Importance
- Individual Customer Predictions

### Global SHAP Summary Plot

The summary plot ranks features according to their average impact on model predictions.

Important observations include:

- Short tenure increases churn probability.
- Fiber optic customers historically show higher churn than DSL customers.
- Month-to-month contracts increase churn.
- Long-term contracts reduce churn.
- High monthly charges generally increase churn risk.

These relationships represent **patterns present in the historical dataset** rather than causal relationships.

---

### Individual SHAP Waterfall Plot

For a single customer, SHAP decomposes the prediction into individual feature contributions.

Prediction = Base Value + Feature Contributions

Each feature either:

- pushes the prediction towards churn
- pushes the prediction towards retention

This allows complete transparency of every individual prediction.

---

# Why SHAP?

Traditional Machine Learning models often behave as black boxes.

SHAP provides:

- Local explanations
- Global explanations
- Feature importance
- Business interpretability
- Customer-specific reasoning

making the model suitable for real-world decision making.

---

# Streamlit Dashboard

A Streamlit dashboard was developed for interactive prediction.

Features include:

- Customer input form
- Churn probability prediction

---

# Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- SHAP
- Streamlit
- Joblib

---

# Project Workflow

Dataset

↓

Data Cleaning

↓

Feature Engineering

↓

One-Hot Encoding

↓

Feature Scaling

↓

Train-Test Split

↓

Logistic Regression

↓

Model Evaluation

↓

SHAP Explainability

↓

Streamlit Dashboard

---

# Key Learnings

This project provided practical understanding of:

- Binary Classification
- Logistic Regression
- Maximum Likelihood Estimation
- Cross Entropy Loss
- Feature Scaling
- ROC-AUC
- Threshold Optimization
- Model Explainability
- SHAP Values
- Streamlit Deployment
- Git & GitHub

---

# Future Improvements

- Hyperparameter Optimization
- Probability Calibration
- XGBoost Comparison
- Customer Retention Recommendation System
- Cost-sensitive Learning
- Automated Retraining Pipeline

---

# Author

Garima Singh

Machine Learning | Data Science | AI
