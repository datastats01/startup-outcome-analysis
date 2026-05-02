# Startup Outcome Prediction using Machine Learning

## One-Sentence Summary  
This project predicts startup outcomes (Failure, Acquisition, or IPO) using Logistic Regression and Random Forest models on a Kaggle dataset.

---

## Overview  
This project predicts startup outcomes, specifically whether a startup will fail, get acquired, or go public (IPO). The problem is treated as a multi-class classification task using a dataset containing features such as funding, revenue, team size, and market size. Logistic Regression and Random Forest models are trained to learn patterns associated with each outcome class. Random Forest achieves the strongest performance with an accuracy of approximately 73.6%, while Logistic Regression achieves 68.6%. The results indicate that financial and growth-related features such as revenue and product traction are the most influential predictors, while IPO prediction remains challenging due to class imbalance.

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

- **Numerical Feature Distributions**
    - IPO startups show the highest averages in funding rounds, founder experience, team size, and revenue.
    - Acquisition startups sit in the middle range across most financial metrics.
    - Failure startups consistently show the lowest values in revenue and funding.
    - Market size and burn rate are relatively similar across all classes.

<!-- Numerical Feature Distribution Plot -->
<figure>
<img src="/visualizations/startup_outcome_analysis_num_features.png" alt="Numerical Features Histograms">
<figcaption></figcaption>
</figure>

---

- **Categorical Feature Analysis**
    - Certain sectors like Health and SaaS show higher IPO representation.
    - Tier 2 VC funding appears most frequently across all outcomes.
    - First-time founders are more associated with Failure outcomes.
    - Founder background has weaker separation power compared to financial features.

<!-- Categorical Feature Plot -->
<figure>
<img src="/visualizations/startup_outcome_analysis_cat_features.png" alt="Categorical Features Histograms">
<figcaption></figcaption>
</figure>

---

- **Class Imbalance Check**
    - The dataset is imbalanced, with Failure being the dominant class.
    - IPO represents a very small portion of the dataset.
    - This imbalance affects model performance, especially for IPO prediction.

    | Outcome     | Count |
    |-------------|-------|
    | Failure     | 22,145 |
    | Acquisition | 13,141 |
    | IPO         | 2,952  |

---

### Preprocessing  
- Verified no missing values or duplicates  
- Encoded categorical variables  
- Scaled numerical features  
- Split dataset into training and testing sets  

---

### Problem Setup  
This is a multi-class classification problem.

- **Input:** Startup features (funding, revenue, etc.)  
- **Output:** Startup outcome (Failure, Acquisition, IPO)

**Models Used:**
- Logistic Regression  
- Random Forest  

**Settings:**
- Logistic Regression: `max_iter=5000`  
- Random Forest: `n_estimators=200`  

---

### Training  
- Implemented using Python and scikit-learn  
- Models trained on CPU  
- Training completed quickly  
- Minimal hyperparameter tuning required  

---

### Model Performance

| Model               | Accuracy  | Precision   | Recall    | F1 Score  | ROC AUC   |
|---------------------|----------|-------------|-----------|-----------|-----------|
| Logistic Regression | 0.68575  | 0.721400    | 0.68575   | 0.697992  | 0.845781  |
| Random Forest       | 0.73620  | 0.734517    | 0.73620   | 0.729080  | 0.859523  |

- **Logistic Regression** achieves an accuracy of **68.6%**.
- **Random Forest** achieves an accuracy of **73.6%**, slightly outperforming Logistic Regression in all metrics except for recall.

---

### ROC Curve (IPO Class)

<!-- ROC Curve Plot -->
<figure>
<img src="/visualizations/startup_outcome_analysis_roc_curves.png" alt="ROC Curves">
<figcaption></figcaption>
</figure>

- Random Forest shows slightly better ranking ability (higher AUC).
- Logistic Regression performs more consistently but with lower separation power.

---

### Feature Importance

<!-- Feature Importance Plot -->
<figure>
<img src="/visualizations/startup_outcome_analysis_feature_importance.png" alt="Feature Importance">
<figcaption></figcaption>
</figure>

- Revenue is the strongest predictor of startup outcome.
- Product traction is the second most important feature.
- Founder background and investor type have low predictive influence.
- Financial metrics dominate model decisions overall.

---
 
### Conclusions  
- Both models achieve moderate predictive performance, with Random Forest outperforming Logistic Regression (73.6% vs. 68.6% accuracy).  
- Model performance is largely driven by financial and usage-based features such as revenue and product traction.  
- Logistic Regression provides more balanced but weaker overall predictive performance compared to Random Forest.  
- IPO prediction remains the most difficult class to model due to severe class imbalance and limited representation in the dataset.  
- Overall, startup outcomes appear to be strongly influenced by measurable business performance metrics rather than qualitative factors such as founder background or investor type.  

---

### Future Improvements  
- Apply oversampling to improve IPO detection  
- Use XGBoost or LightGBM for better performance  
- Improve feature engineering (ratios like revenue/burn rate)  
- Add time-based or external economic features  

---

## How to Reproduce Results  

1. Clone the repository  
2. Download dataset from Kaggle:  
   https://www.kaggle.com/datasets/dhrubangtalukdar/startup-funding-and-outcome-dataset  
3. Place dataset in `/data` folder  
4. Install dependencies:
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