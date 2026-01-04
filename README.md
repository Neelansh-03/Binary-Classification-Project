# Predictive Binary Classifier for Customer Conversion

## 🎯 Project Overview

This project aims to optimize banking marketing efforts by predicting which customers are likely to subscribe to a term deposit. Instead of "cold calling" every client, the bank can use this **Logistic Regression** model to target high-probability leads, significantly reducing operational costs and increasing conversion rates.

## 📊 The Problem Statement

Direct marketing campaigns are expensive and time-consuming. The goal is to build a binary classifier to predict the target variable `y` (Yes/No), representing whether the client subscribed to a term deposit.

## 🛠️ Technical Stack

* **Language:** Python 3.x
* **Libraries:** `pandas`, `numpy`, `scikit-learn`, `matplotlib`, `seaborn`
* **Environment:** Jupyter Notebook / Google Colab

---

## 🏗️ Model Pipeline Architecture

The solution utilizes a professional **Scikit-Learn Pipeline** to ensure clean code and prevent data leakage.

### 1. Data Preprocessing

* **Numerical Features:** Imputed missing values with the `median` and standardized using `StandardScaler`.
* **Categorical Features:** Imputed missing values with the `most frequent` strategy and transformed using `OneHotEncoder`.
* **Handling Imbalance:** The dataset is naturally skewed toward "No" responses. This model uses **Cost-Sensitive Learning** (`class_weight='balanced'`) to penalize mistakes on the minority "Yes" class more heavily.

### 2. The Model

A **Logistic Regression** classifier was chosen for its interpretability. It allows us to mathematically see which features (age, balance, etc.) most strongly drive a customer's decision.

---

## 📈 Evaluation Metrics

The model is evaluated using a **Confusion Matrix** and a **Classification Report**.

* **Precision:** Measures the accuracy of "Yes" predictions (how many called customers actually subscribed).
* **Recall:** Measures the model's ability to find all potential subscribers.
* **F1-Score:** The harmonic mean of Precision and Recall, used to balance the two.

---

## 🚀 How to Run

1. **Prepare the Data:** Ensure `bank.csv` is in the same directory as your script or uploaded to your Colab environment.
2. **Install Dependencies:**
```bash
pip install pandas numpy scikit-learn matplotlib seaborn

```


3. **Execute:** Run the provided Python script or Jupyter Notebook cells.

## 💡 Key Insights

The model extracts the **Top 3 Features** that influence a "Yes" prediction. Typically, these include:

1. **Duration:** The length of the last contact (higher duration correlates strongly with interest).
2. **Poutcome_Success:** If the previous campaign was successful, the current one is likely to be too.
3. **Month:** Specific seasonal trends in banking behavior.

---
