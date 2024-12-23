# Kaggle Competition: Child Mind Institute — Problematic Internet Use

## Team CRUD

### Contributors
- Nguyễn Đức Khánh - 22028196
- Ngô Lê Hoàng - 22028042
- Hoàng Duy Hưng - 22028115

## Introduction
This repository contains the collective work of our team during the Kaggle competition aimed at predicting problematic internet use among young participants. It includes:

- **Project Report**: A detailed document outlining our approach, methodology, and results.
- **Exploratory Data Analysis (EDA)**: Code and analyses that investigate the dataset to uncover patterns and insights.
- **Notebook Versions**: Jupyter notebooks demonstrating different modeling approaches and experiments conducted throughout the competition.

## Overview
The project focuses on predicting the Severity Impairment Index (sii) associated with problematic internet use among participants aged 5 to 22 years, utilizing the Healthy Brain Network (HBN) dataset. This dataset encompasses physical activity data collected from accelerometers and information on internet usage behaviors.

## Methodology

### Version 0
**1. Data Processing**:
   - Removed rows missing the Severity Impairment Index (sii).
   - Converted categorical columns into numerical representations.
   - Resulted in 2736 training rows and 20 test rows after preprocessing.

**2. Model**:
   - Implemented CatBoostClassifier as a baseline model without hyperparameter tuning.

**3. Results**:
   - Achieved a baseline score of 0.259.

### Version 1
**1. Data Processing**:
   - Identified key features based on high correlation with PCIAT-PCIAT_Total.
   - Reduced features from 55 to 19 by eliminating those with low correlation.
   - Removed columns missing more than 70% of values.
  
**2. Model**:
   - Used XGBoost to predict PCIAT-PCIAT_Total.
   - Applied Stratified Cross Validation to avoid overfitting.

**3. Results**: Achieved a score of 0.431.

### Version 2
**1. Data Processing**:
   - Shifted to features extracted from actigraphy data.
   - Discontinued the correlation-based filtering from Version 1.

**2. Model**:
   - Utilized LightGBM with optimized hyperparameters.

**3. Results**: Achieved a score of 0.435.

### Version 3
**1. Data Processing**:
   - Incorporated feature extraction from actigraphy (time-series data).

**2. Model**:
   - Implemented a Voting Regressor to combine predictions from LightGBM, XGBoost, and CatBoost.
   - Employed Hyperopt for automated hyperparameter optimization.

**3. Results**: Achieved the highest score of 0.447.
