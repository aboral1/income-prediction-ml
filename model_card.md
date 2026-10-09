
# Income Classification Model Card

## Model Overview
- **Algorithm**: XGBoost with SMOTE
- **Task**: Binary Classification (Income >50K prediction)
- **Training Date**: 2026

## Model Performance
- **Test Accuracy**: 0.8431
- **Test Precision**: 0.6548
- **Test Recall**: 0.7815
- **Test F1-Score**: 0.7126
- **ROC-AUC**: 0.9157

## Features Used
- Age, Workclass, Education, arital Status
- Occupation, Relationship, Race, Sex
- Capital Gain/Loss, Hours per Week
- Native Country

## Preprocessing
- Categorical Encoding: Label Encoding
- Numerical Scaling: StandardScaler
- Imbalance Handling: SMOTE (Synthetic Minority Over-Sampling)

## Known Limitations
- Dataset is from 1994, may not reflect current income distribution
- Geographic Bias based on native country istribution
- Does not capture dynamic career progression

## Production Considerations
- Monitor model performance on new data (data drift)
- Retrain monthly with new data
- Log all predictions for auditing
- Implement fairness checks for protected attributes
