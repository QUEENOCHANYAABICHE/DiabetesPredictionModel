
# Diabetes Prediction Project 🩺

A machine learning project that predicts diabetes diagnosis using patient health data. The project covers end-to-end data analysis — from cleaning and exploration to model building and evaluation.

---

## 📁 Project Structure

```
DiabetesPredictionProject/
│
├── DiabetesPredictionProject.ipynb   # Main notebook
├── diabetes_prediction_dataset.csv   # Dataset
└── README.md
```

---

## 📊 Dataset

- **Source:** diabetes_prediction_dataset.csv
- **Size:** 96,146 patient records (after deduplication)
- **Features:** Age, BMI, HbA1c level, blood glucose level, hypertension, heart disease, gender, smoking history
- **Target:** Diabetes (0 = No, 1 = Yes)
- **Class distribution:** 91.78% non-diabetic, 8.22% diabetic

---

## 🔍 Project Workflow

### 1. Data Cleaning
- Checked for nulls, duplicates, and data types
- Removed duplicate records
- Checked for skewness in numerical columns

### 2. Exploratory Data Analysis (EDA)
Key questions explored:
- What is the distribution of diabetes diagnoses?
- Does age, BMI, or smoking history affect diabetes risk?
- Are hypertension and heart disease associated with diabetes?
- Which risk factor combinations are most dangerous?

### 3. Data Pre-processing
- One-hot encoding for categorical variables (gender, smoking history)
- Train/test split (80/20) with stratification
- StandardScaler applied to training data only (to prevent data leakage)

### 4. Modelling
Two models were built and compared:
- Logistic Regression
- Random Forest (tuned with GridSearchCV)

### 5. Evaluation
- Classification Report
- Confusion Matrix
- ROC Curve
- Precision-Recall Curve
- Cross-Validation (5-fold)

---

## 📈 Key EDA Findings

- **HbA1c level and blood glucose** are the strongest predictors of diabetes (r = 0.42 each)
- The **71–80 age group** has the highest diabetes prevalence at ~21%
- **Former smokers** show a higher diabetes rate (17.1%) than current smokers
- **Heart disease** is ~5x more prevalent in diabetic patients (14.9% vs 3%)
- High HbA1c (≥6.5%) alone can drive ~50% diabetes rates, even with normal BMI

---

## 🤖 Model Results

| Metric | Logistic Regression | Random Forest |
|---|---|---|
| Accuracy | 88% | 90% |
| Recall (Diabetic) | 88% | 90% |
| ROC-AUC | 0.96 | 0.97 |
| Average Precision | 0.82 | 0.87 |
| CV Mean Recall | — | 90.8% ± 0.006 |

**✅ Best Model: Random Forest**

---

## 💡 Key Insight

In a medical screening context, **recall matters more than precision** — it is far safer to flag a healthy patient for further testing than to miss an actual diabetic case. Both models prioritise this, with Random Forest achieving 90% recall validated across 5 cross-validation folds.

---

## 🛠️ Tools & Libraries

- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Plotnine
- Janitor

---

## 👤 Author

**[Your Name]**  
[LinkedIn Profile](https://linkedin.com/in/yourprofile) | [GitHub](https://github.com/yourusername)
