# Startup Outcome Prediction using Machine Learning

## One-Sentence Summary  
This project predicts startup outcomes (Failure, Acquisition, or IPO) using Logistic Regression and Random Forest models on a Kaggle dataset.

---

## Overview  
This project predicts whether a startup will fail, get acquired, or go public (IPO). It uses a dataset with features such as funding, revenue, team size, and market size, treated as a multi-class classification problem. Both Logistic Regression and Random Forest models were trained, achieving around 74% accuracy. Financial features like revenue and product traction play a major role in the predictions, while predicting IPOs is more challenging due to class imbalance.

---

## Summary of Work Done

### Data Exploration
- **Type:** Tabular dataset (CSV file)  
- **Features:** Funding rounds, revenue (millions), team size, market size (billions), sector, investor type, founder background, founder experience (years), burn rate (millions), product traction (users), outcome
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

<!---[Visualizations](/visualizations/startup_outcome_analysis_num_features.png)--->
<figure>
<img src="/visualizations/startup_outcome_analysis_num_features.png" alt="Numerical Features Histograms">
<figcaption> </figcaption>
</figure>

- **Compared categorical features across startup outcomes**
    - Climate has the highest number of IPO startups (310), followed by Health (303), with AI having the lowest count in IPO (260).
    - Tier 2 VCs invest in the most startups across all outcomes, while angel investors have the lowest involvement in IPO startups (553).
    - First-time founders have the highest counts for Failure and Acquisition startups, while academic founders have the lowest representation in   IPO startups (419).
    - AI and Crypto sectors have fewer IPO startups, while Health, SaaS, and Climate are more represented in the IPO category.
        
<!---[Visualizations](/visualizations/startup_outcome_analysis_cat_features.png)--->
<figure>
<img src="/visualizations/startup_outcome_analysis_cat_features.png" alt="Categorical Features Histograms">
<figcaption> </figcaption>
</figure>

- **Checked class imbalance in the target variable**
    - The Outcome variable is imbalanced, with more instances of Failure startups than Acquisition or IPO.
    - The Failure class has the highest count, indicating most startups in the dataset ended in failure.
    - Acquisition and IPO have fewer instances, with IPO being the least represented outcome.

        | Outcome     | Count |
        |-------------|-------|
        | Failure     | 22,145 |
        | Acquisition | 13,141 |
        | IPO         | 2,952  |

---

### Preprocessing  
- Checked for missing values and duplicate records (none found)  
- Converted categorical features into numbers  
- Scaled numerical features  
- Split data into training and testing sets
  
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

### Training  
- Built using Python and scikit-learn  
- Models trained on CPU  
- Training was fast (only a few seconds)  
- No complex tuning was required  

---

### Model Performance

| Model               | Accuracy | Precision (weighted) | Recall (weighted) | F1 Score (weighted) | ROC AUC |
|---------------------|----------|----------------------|-------------------|---------------------|---------|
| Logistic Regression | 0.7447   | 0.7417               | 0.7447            | 0.7403              | 0.745   |
| Random Forest       | 0.7362   | 0.7345               | 0.7362            | 0.7291              | 0.786   |

Both models show similar performance, with Random Forest slightly better at ranking but not at recall.

**ROC Curves (IPO Class)**
<!---[Visualizations](/visualizations/startup_outcome_analysis_roc_curves.png)--->
<figure>
<img src="/visualizations/startup_outcome_analysis_roc_curves.png" alt="ROC Curves"> 
<figcaption> </figcaption>
</figure>

- **Key insights from ROC Curves (IPO Class):**
    - Random Forest shows a higher ROC AUC, indicating better overall ranking/separation across classes.
    - Logistic Regression performs slightly lower but more consistently.

**Feature Importance Bar Chart**
<!---[Visualizations](/visualizations/startup_outcome_analysis_feature_importance.png)--->
<figure>
<img src="/visualizations/startup_outcome_analysis_feature_importance.png" alt="Feature Importance">
<figcaption> </figcaption>
</figure>

- **Key insights from Feature Importance Bar Chart:** 
    - Revenue is the most important feature, meaning startups with higher revenue strongly influence predictions.
    - Product traction is the second most important feature, showing user growth matters a lot.
    - Founder background and investor type contribute less to the model compared to financial and usage-based features.
      
---

### Conclusions  
- The models achieve moderate performance (~74% accuracy).  
- Both models behave very similarly overall.  
- IPO prediction is the hardest because there are very few IPO examples in the data.  
- The results suggest that startup outcomes are primarily driven by measurable financial performance such as revenue and user traction, rather than founder or investor characteristics.

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
   - 1_data_eda.ipynb -> exploratory data analysis 
   - 2_data_visualizations.ipynb -> data visualizations based on original dataset
   - 3_data_preprocessing.ipynb -> data preprocessing for machine learning
   - 4_data_models.ipynb -> machine learning models based on data
   - 5_data_model_evaluations.ipynb -> in-depth evaluation on models and charts