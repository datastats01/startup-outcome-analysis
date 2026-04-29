# startup-outcome-analysis

## One Sentence Summary
This repository explores predicting startup outcomes (Failure, Acquisition, IPO) using machine learning models trained on a Kaggle startup funding dataset.

## Overview


## Summary of Work Done


### Data
- **Type:** Tabular dataset (CSV file)
- **Input:** Startup features including features like funding, revenue, market size, team size, sector, investor type, and founder background
- **Output:** Startup outcome (Failure, Acquisition, IPO)
- **Size:** ~100,000 rows
- **Split:** 80% training, 20% testing (stratified split)

#### Preprocessing / Clean Up
- **Missing Values:** Checked and confirmed no missing values
- **Duplicate Records:** Removed duplicate records (if any)
- **Label Encoding:** Encoded categorical variables using Label Encoding
- **Feature Scaling:** Scaled numerical features using StandardScaler
- **Train and Test Split:** Split dataset into train/test (80/20 stratified split)
- **Feature Separation:** Separated features (X) and target variable (y)

#### Data Visualizations
Exploratory analysis included:

Key observation: startups with higher revenue and product traction users are more likely to succeed.

### Problem Formulation
- The problem defined was to learn what features contributed to a startup's outcome

### Performance Comparison



### Conclusions


### Future Work

## How to reproduce results



## Overview of Files in Repository
- Notebooks folder
  - 1_data_eda.ipynb
  - 2_data_visualizations.ipynb
  - 3_data_preprocessing.ipynb
  - 4_data_models.ipynb
  - 5_data_modelevaluations.ipynb


 ## Software Setup
 - Libraries Used (imported):
   - Pandas
   - Numpy
   - Matplotlib

## Data Source
- Link: https://www.kaggle.com/datasets/dhrubangtalukdar/startup-funding-and-outcome-dataset
- Preprocessing steps can be found in notebook 3

## Training:
---

## Overview
The task is to analyze a structured dataset of startup-related features (such as funding, revenue, team size, and market size) and predict the final outcome of a startup: Failure, Acquisition, or IPO. This is formulated as a multi-class classification problem. The approach taken in this repository applies two machine learning models: Logistic Regression and Random Forest. Logistic Regression is used as a baseline interpretable model, while Random Forest is used to capture non-linear relationships between features. Both models are evaluated and compared using standard classification metrics. The results show that both models achieve similar performance (around 74% accuracy). Feature analysis indicates that financial indicators such as revenue, burn rate, and market size are strong predictors of startup success. However, the IPO class remains difficult to predict due to class imbalance.

---

## Summary of Work Done

---

## Data

- **Type:** Tabular dataset (CSV file)
- **Input:** Startup features including funding, revenue, market size, team size, sector, investor type, and founder background
- **Output:** Startup outcome (Failure, Acquisition, IPO)
- **Size:** ~[insert dataset size]
- **Split:** 80% training, 20% testing

---

## Preprocessing / Clean Up

- Removed duplicate rows
- Handled missing values (if present)
- Encoded categorical variables using Label Encoding
- Standardized numerical features using StandardScaler
- Split dataset into training and testing sets

---

## Data Visualization

Exploratory analysis included:
- Histograms of numerical features
- Comparison of features across outcome classes
- Distribution analysis of key financial variables

Key observation: startups with higher revenue and market size are more likely to succeed or be acquired.

---

## Problem Formulation

- **Input:** Startup features (financial + categorical attributes)
- **Output:** Multi-class label (Failure, Acquisition, IPO)

### Models Used:
- Logistic Regression (baseline linear model)
- Random Forest (non-linear ensemble model)

No custom loss function was used. Standard classification loss was applied internally by sklearn models.

---

## Training

- Implemented using Python (scikit-learn)
- Models trained on 80% training data
- No GPU required (CPU training only)
- Hyperparameters:
  - Logistic Regression: max_iter=5000
  - Random Forest: n_estimators=200
- Training was fast and completed in seconds
  
---

## Performance Comparison

### Metrics Used:
- Accuracy
- Precision
- Recall
- F1-score

| Model               | Accuracy | Precision | Recall | F1 Score |
|--------------------|----------|-----------|--------|----------|
| Logistic Regression | ~0.74    | ~0.74     | ~0.74  | ~0.74    |
| Random Forest       | ~0.73    | ~0.73     | ~0.73  | ~0.73    |

---

## Conclusions

- Startup outcomes can be moderately predicted using structured financial and company features.
- Both models perform similarly, indicating limited separability in the dataset.
- IPO prediction is the most challenging due to class imbalance.

---

## Future Work

- Use advanced models such as XGBoost or Gradient Boosting
- Address class imbalance using SMOTE or class weighting
- Improve feature engineering
- Add external macroeconomic indicators

---

## How to Reproduce Results

1. Clone repository
2. Download dataset from Kaggle:
   https://www.kaggle.com/datasets/dhrubangtalukdar/startup-funding-and-outcome-dataset
3. Place dataset in `/data` folder
4. Install dependencies:
```bash
pip install -r requirements.txt
