# 📊 Machine Learning Project – Predicting Custodial Suicide  
**By Aishwarya Maiya**

Badges:  
`ML` `Data Cleaning` `Feature Engineering` `Model Evaluation` `Classification`

---

## 🧠 Overview

This repository showcases a **Machine Learning Classification Project** built using the *Crime in India* dataset from Kaggle.  
The goal is to **predict whether a custodial suicide occurred** based on crime indicators, demographics, and police data.

The project includes **EDA, preprocessing, model training, evaluation, and model export**, implemented using Python and Scikit-Learn.

---

## 🗂️ Projects

### 1️⃣ 🔍 **Data Loading & Exploration**

- Loaded 18+ CSV files from the Crime in India dataset.
- Selected the **Custodial Deaths & Suicides (CDO)** dataset.
- Performed:
  - `.info()`, `.describe()`
  - Missing value analysis
  - Data type inspection
  - Distribution checks for `Suicide_Occurred`

---

### 2️⃣ 🧹 **Data Preprocessing**

Preprocessing Pipeline:

#### ✔️ Numerical Features
- Median imputation  
- StandardScaler  

#### ✔️ Categorical Features
- Most frequent imputation  
- One-hot encoding  

Combined using:

```python
ColumnTransformer(
    transformers=[
        ("num", num_transformer, numerical_features),
        ("cat", cat_transformer, categorical_features)
    ]
)
