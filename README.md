# 🚁 Multi-UAV Conflict Risk Analysis

## 📌 Overview
This project was developed as **Homework 1** for the *Machine Learning* course (A.Y. 2022/2023) at Sapienza.  
The goal was to analyze flight scenarios with **5 UAVs** in a 2D space, addressing two different tasks:

- **Classification Task** → Predict whether a collision will occur (5 possible classes).  
- **Regression Task** → Predict the minimum *Closest Point of Approach (CPA)* among the UAVs.  

This was my **first-ever project in Machine Learning**, and it was carried out strictly using **linear models** and classic machine learning methods, as required by the professor.  
👉 It is important to highlight that **neural networks or more advanced models could not be used**, as it was explicitly forbidden.  
This means that while the results are valid for the homework, they could be significantly improved by adopting modern deep learning techniques or more sophisticated approaches.

---

## ⚙️ Preprocessing
- Tested several normalization methods:
  - Min-Max Scaler (0–1) ✅ best performing  
  - Unit Norm  
  - Standardization  
  - Robust Scaler  
- Dataset split into **train/test** (67/33).

---

## 📊 Models Used

### 🔹 Classification
- **Logistic Regression**
- **Support Vector Classifier (SVC)**
- Comparison between **accuracy** and **f1_weighted** metrics to deal with the **imbalanced dataset** (many samples with 0 collisions).  
- Attempts to improve performance with:
  - `class_weight` in Logistic Regression  
  - Hyperparameter tuning via `GridSearchCV`  
  - **Adaboost** as ensemble  

### 🔹 Regression
- **Linear Regression**
- **Support Vector Regressor (SVR)**
- Feature engineering: evaluated the impact of the *num_collisions* variable.  
- With SVR and `GridSearchCV`, a **positive regression score (R² ≈ 0.47)** and **MSE ≈ 0.01** were achieved.

---

## 📈 Results & Limitations
- The imposed linear models showed clear limitations:  
  - **Data not linearly separable** → Logistic Regression and SVC struggled to capture the complexity.  
  - **Imbalanced dataset** → poor prediction of the most relevant collision classes.  
- Nevertheless, SVR provided encouraging results for regression.  

⚠️ **Important Note**:  
The use of **linear models only** was a **mandatory requirement by the professor**.  
Thus, modern approaches (e.g., neural networks, Random Forests, Gradient Boosting, etc.) were not allowed but would likely lead to significantly better results.

---
