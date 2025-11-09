Roll: DA25M025

Name: Rishabh Mishra

Date: 10.11.2025

# Bike Sharing Demand Prediction - Ensemble Learning

Machine learning analysis of bike-sharing rental patterns using ensemble techniques on the Capital Bikeshare dataset (2011-2012).

## Overview

This project explores ensemble learning methods to predict hourly bike rental demand, comparing baseline models with advanced techniques including Bagging, Boosting, and Stacking.

## Dataset

- **Source**: Capital Bikeshare Dataset (Washington D.C.)
- **Records**: 17,379 hourly observations
- **Features**: 13 variables (weather, temporal, categorical)
- **Target**: Hourly bike rental count (`cnt`)

## Key Features

- **Data Preprocessing**: One-hot encoding of categorical features (season, weather, hour, etc.)
- **Feature Engineering**: Expanded from 13 to 54 features
- **Exploratory Analysis**: Temporal patterns, weather impact, seasonal trends

## Models Implemented

### Baseline Models
- Decision Tree (RMSE: 118.46)
- Linear Regression (RMSE: 100.45)

### Ensemble Methods
1. **Bagging** - Variance reduction technique
   - Bagging Decision Tree (RMSE: 112.36)
   - Bagging Linear Regression (RMSE: 100.42)

2. **Gradient Boosting** - Bias reduction technique
   - 100 estimators (RMSE: 78.00)
   - 52% bias reduction vs baseline

3. **Stacking** - Meta-learning approach
   - Base learners: KNN, Bagging, Gradient Boosting
   - Meta-learner: Ridge Regression
   - **Best Performance: RMSE 67.05 (R² = 0.858)**

## Results Summary

| Model | RMSE | Improvement |
|-------|------|-------------|
| Stacking | **67.05** | **33.3%** |
| Gradient Boosting | 78.00 | 22.3% |
| Linear Regression | 100.45 | Baseline |
| Decision Tree | 118.46 | - |

## Key Findings

- **Bagging**: Reduced variance by 70.6% for Decision Trees but minimal impact on Linear Regression
- **Boosting**: Achieved 52% bias reduction and 90% variance reduction vs Decision Tree
- **Stacking**: Outperformed all models by optimally combining diverse learners (14.1% better than Gradient Boosting)

## Bias-Variance Analysis

Comprehensive bias-variance decomposition demonstrates:
- Bagging primarily targets **variance reduction**
- Boosting primarily targets **bias reduction**
- Stacking achieves optimal **bias-variance trade-off**

## Technologies Used

- **Python 3.x**
- **Libraries**: scikit-learn, pandas, numpy, matplotlib, seaborn, mlxtend
- **Techniques**: Cross-validation, bias-variance decomposition, ensemble learning

## Visualizations

- Temporal rental patterns (seasonal, monthly, hourly)
- Weather impact analysis
- Model performance comparisons
- Actual vs Predicted scatter plots
- Bias-variance decomposition charts

## Conclusion

Stacking ensemble achieved the best predictive performance (RMSE: 67.05) by intelligently combining diverse base learners through meta-learning, demonstrating a 33.3% improvement over baseline models.
