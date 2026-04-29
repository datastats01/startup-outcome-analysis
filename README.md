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
