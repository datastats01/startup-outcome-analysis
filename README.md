# Startup Outcome Prediction using Machine Learning

## One-Sentence Summary  
This project predicts startup outcomes (Failure, Acquisition, or IPO) using Logistic Regression and Random Forest models on a Kaggle dataset.

---

## Overview  
This project uses machine learning to predict whether a startup will fail, get acquired, or go public (IPO). The dataset includes information such as funding, revenue, team size, market size, and other business-related features. This is treated as a multi-class classification problem. Two models are used: Logistic Regression as a simple baseline model and Random Forest as a more advanced model. Both models achieve around 74% accuracy. The results show that financial features like revenue and user traction are the most important for prediction, while predicting IPOs is difficult because there are very few IPO examples in the dataset.

---

## Summary of Work Done

### Data Exploration
- **Type:** Tabular dataset (CSV file)  
- **Features:** Funding rounds, revenue (millions), team size, market size (billions), sector, investor type, founder background, founder experience (years), burn rate (millions), product traction users, outcome
- **Target:** Startup outcome (Failure, Acquisition, IPO)  
- **Size:** ~100,000 rows  
- **Split:** 80% training, 20% testing (stratified split)

---

### Data Visualization  
- **Plotted distributions of numerical features**
    - IPO startups have the highest average funding rounds (3.00), founder experience (15.54 years), team size (172.09), and revenue (2.12M USD).
    - Acquisition startups have moderate values for funding rounds (2.35), founder experience (13.53 years), and team size (159.24).
    - Failure startups have the lowest funding rounds (1.70), founder experience (10.75 years), team size (143.46), and revenue (536K USD).
    - Market size and burn rate show little variation across outcomes, with IPO startups having the highest product traction (547K users).

<!---[Data Visualizations](/visualizations/startup_outcome_analysis_num_features.png)--->
<figure>
<img src="/visualizations/startup_outcome_analysis_num_features.png" alt="Numerical Features Histograms">
<figcaption> </figcaption>
</figure>

- **Compared categorical features across startup outcomes**
  - Climate has the highest number of IPO startups (310), followed by Health (303), with AI having the lowest count in IPO (260).
  - Tier 2 VCs invest in the most startups across all outcomes, while angel investors have the lowest involvement in IPO startups (553).
  - First-time founders have the highest counts for Failure and Acquisition startups, while academic founders have the lowest representation in IPO startups (419).
  - AI and Crypto sectors have fewer IPO startups, while Health, SaaS, and Climate are more represented in the IPO category.
    
<!---[Data Visualizations](/visualizations/startup_outcome_analysis_cat_features.png)--->
<figure>
<img src="/visualizations/startup_outcome_analysis_cat_features.png" alt="Categorical Features Histograms">
<figcaption> </figcaption>
</figure>

- **Checked class imbalance in the target variable**
The Outcome variable is imbalanced, with more instances of Failure startups than Acquisition or IPO.
The Failure class has the highest count, indicating most startups in the dataset ended in failure.
Acquisition and IPO have fewer instances, with IPO being the least represented outcome.

    | Outcome     | Count |
    |-------------|-------|
    | Failure     | 22,145 |
    | Acquisition | 13,141 |
    | IPO         | 2,952  |

**Key insight:** Startups with higher revenue and higher user traction are more likely to succeed.

---
### Problem Setup  
This is a multi-class classification problem.

- **Input:** Startup features (funding, revenue, etc.)  
- **Output:** Outcome (Failure, Acquisition, IPO)

**Models used:**
- Logistic Regression  
- Random Forest  

**Settings:**
- Logistic Regression: `max_iter=5000`  
- Random Forest: `n_estimators=200`  

---

### Preprocessing  
- Checked for missing values and duplicate records (none found)  
- Converted categorical features into numbers  
- Scaled numerical features  
- Split data into training and testing sets  

---

### Training  
- Built using Python and scikit-learn  
- Models trained on CPU  
- Training was fast (only a few seconds)  
- No complex tuning was required  

---

### Model Performance

| Model               | Accuracy | Precision | Recall | F1 Score |
|---------------------|----------|-----------|--------|----------|
| Logistic Regression | ~0.74    | ~0.74     | ~0.74  | ~0.74    |
| Random Forest       | ~0.73    | ~0.73     | ~0.73  | ~0.73    |

Both models perform similarly, with Logistic Regression performing slightly better.

<!---[Data Visualizations](/visualizations/startup_outcome_analysis_feature_importance.png)--->
<figure>
<img src="/visualizations/startup_outcome_analysis_feature_importance.png" alt="Feature Importance">
<figcaption> </figcaption>
</figure>

- Revenue is the most important feature, meaning startups with higher revenue strongly influence predictions.
- Product traction is the second most important feature, showing user growth matters a lot.
- Features like founder background and investor type have low importance, meaning they do not strongly affect predictions.
- Financial and performance-based metrics are more important than categorical features.
  
---

### Conclusions  
- The models achieve moderate performance (~74% accuracy).  
- Both models behave very similarly overall.  
- IPO prediction is the hardest because there are very few IPO examples in the data.  
- Revenue and user traction are the most important features for predicting startup outcomes.  
- Financial features are more useful than founder or investor-related features.

---

### Future Improvements  
- Try better models like XGBoost or Gradient Boosting  
- Improve handling of class imbalance (especially for IPOs)  
- Improve feature engineering  
- Add external data like economic conditions or industry trends  

---

## How to Reproduce Results  

1. Clone the repository  
2. Download dataset from Kaggle:  
   https://www.kaggle.com/datasets/dhrubangtalukdar/startup-funding-and-outcome-dataset  
3. Place dataset in the `/data` folder  
4. Install required libraries:
   - pandas  
   - numpy  
   - matplotlib  
   - scikit-learn  
   - shap  
5. Run notebooks in order:
   - 1_data_eda.ipynb  
   - 2_data_visualizations.ipynb  
   - 3_data_preprocessing.ipynb  
   - 4_data_models.ipynb  
   - 5_data_model_evaluations.ipynb