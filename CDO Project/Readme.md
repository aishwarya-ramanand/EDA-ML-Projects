# 📊 Machine Learning Project – Predicting Custodial Suicide

### **By Aishwarya R**

---

### **Badges**
`ML` `Data Cleaning` `Feature Engineering` `Model Evaluation` `Classification`

---

## 🧠 Overview

This repository presents a **Machine Learning Classification Project** using the *Crime in India* dataset from Kaggle.  
The goal is to **predict whether a custodial suicide occurred** based on crime indicators, demographic variables, and police department attributes.

The project covers **EDA, preprocessing, model training, evaluation, and model export**, implemented with **Python** and **Scikit-Learn**.

---

## 🗂️ Projects

---

### 1️⃣ 🔍 **Data Loading & Exploration**

- Loaded **18+ CSV files** from the Crime in India dataset.  
- Selected the **Custodial Deaths & Suicides (CDO)** dataset.  
- Performed:
  - `.info()` and `.describe()`
  - Missing value inspection
  - Data type analysis
  - Distribution checks for **`Suicide_Occurred`**

---

### 2️⃣ 🧹 **Data Preprocessing**

Preprocessing Pipeline:

#### ✔️ Numerical Features  
- Median imputation  
- StandardScaler  

#### ✔️ Categorical Features  
- Most frequent imputation  
- One-hot encoding  

