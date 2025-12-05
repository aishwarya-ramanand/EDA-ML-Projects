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

### 3️⃣ Train-Test Split

X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.20, random_state=42, stratify=y
)

### 4️⃣ Modeling

#### Logistic Regression (Baseline)

logpipe = Pipeline(
    steps=[
        ("pre", preprocessor),
        ("logreg", LogisticRegression(class_weight="balanced", random_state=42))
    ]

#### Random Forest (Final Model)

rfpipe = Pipeline(
    steps=[
        ("pre", preprocessor),
        ("rf", RandomForestClassifier(random_state=42))
    ]
)
best_model = rfpipe
joblib.dump(best_model, "custodial_suicide_rf_pipeline.pkl")

📈 Evaluation

Confusion Matrix

Generated using a custom plotting function.

ROC Curve

Compared Logistic Regression vs Random Forest.

Cross-Validation

cv_scores = cross_val_score(logpipe, X, y, cv=5, scoring="f1")

🧾 Project Structure

📂 CDO.ipynb                          → ML workflow notebook  
📂 datasets/                           → Crime in India dataset  
📄 README.md                           → Documentation  
🗂️ custodial_suicide_rf_pipeline.pkl  → Trained Random Forest model

)

🔧 Technologies Used

Python • Pandas • NumPy • Scikit-Learn • Matplotlib • Seaborn • Joblib

🚀 Results
	•	Random Forest outperformed Logistic Regression.
	•	Better performance across F1-score and ROC–AUC.
	•	Pipeline approach ensured clean preprocessing and stable predictions.
	•	Final model exported for deployment.

📌 Future Improvements
	•	Hyperparameter tuning (GridSearchCV/RandomizedSearchCV)
	•	SMOTE for oversampling
	•	Explainability via SHAP / LIME
	•	Merging additional datasets for richer feature sets

🙌 Acknowledgements

Dataset Source: Kaggle – Crime in India (Salman Tokhi)
Tools: Python, Jupyter Notebook, Scikit-Learn
