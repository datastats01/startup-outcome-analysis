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

- 
