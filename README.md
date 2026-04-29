# Startup Outcome Prediction using Machine Learning

## One Sentence Summary
Predicts startup outcomes (Failure, Acquisition, IPO) using Logistic Regression and Random Forest on a Kaggle dataset.

---

## Overview
This project predicts startup outcomes using structured features (funding, revenue, team size, market size, etc.). The task is framed as a multi-class classification problem.

Two models are used:
- Logistic Regression (baseline)
- Random Forest (non-linear model)

Both achieve ~74% accuracy. Revenue and user traction are strong predictors. IPO prediction is hardest due to class imbalance.

---

## Summary of Work Done

### Data
- **Type:** Tabular (CSV)
- **Input:** Funding, revenue, team size, market size, sector, investor type, founder background
- **Output:** Outcome (Failure, Acquisition, IPO)
- **Size:** ~100,000 rows
- **Split:** 80/20 (stratified)

---

### Preprocessing / Clean Up
- Removed duplicates
- No missing values found
- Label Encoding for categorical features
- StandardScaler for numerical features
- Train/test split
- Feature-target separation

---

### Data Visualization
- Histograms of numerical features
- Outcome-based comparisons
- Categorical distributions

**Key Insight:**
Higher revenue and user traction correlate with successful outcomes.

---

### Problem Formulation
- **Input:** Startup features
- **Output:** Multi-class label

**Models:**
- Logistic Regression
- Random Forest

**Hyperparameters:**
- Logistic Regression: `max_iter=5000`
- Random Forest: `n_estimators=200`

---

### Training
- Python (scikit-learn)
- CPU only
- Training time: seconds
- No early stopping needed

---

### Performance Comparison

**Metrics:**
- Accuracy
- Precision
- Recall
- F1 Score

| Model | Accuracy | Precision | Recall | F1 |
|------|--------|---------|-------|----|
| Logistic Regression | ~0.74 | ~0.74 | ~0.74 | ~0.74 |
| Random Forest | ~0.73 | ~0.73 | ~0.73 | ~0.73 |

---

### Conclusions
- Moderate predictability of startup outcomes
- Similar model performance → limited non-linear gain
- IPO hardest due to imbalance
- Financial features are most important

---

### Future Work
- Try XGBoost / Gradient Boosting
- Handle class imbalance (SMOTE, weights)
- Improve feature engineering
- Add external economic data

---

## How to Reproduce Results

1. Clone the repository

2. Download dataset:  
   https://www.kaggle.com/datasets/dhrubangtalukdar/startup-funding-and-outcome-dataset

3. Place the dataset in a `/data` folder

4. Software Setup (Required libraries):
- pandas
- numpy
- matplotlib
- scikit-learn
- shap

Install all dependencies:
- ```bash pip install -r requirements.txt

5. Run notebooks in order:
- 1_data_eda.ipynb → Exploratory Data Analysis
- 2_data_visualizations.ipynb → Visualizations
- 3_data_preprocessing.ipynb → Data cleaning and preprocessing
- 4_data_models.ipynb → Model training
- 5_data_modelevaluations.ipynb → Model evaluation