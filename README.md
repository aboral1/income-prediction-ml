# Income Prediction with Machine Learning

This project builds a binary classification model to predict whether a person's annual income is greater than $50K based on demographic and employment attributes from the UCI Adult dataset.

The workflow includes:
- Data loading and exploratory data analysis
- Cleaning missing values and feature preparation
- Comparing multiple classifiers
- Applying class imbalance handling with SMOTE
- Evaluating model performance on a held-out test set
- Saving the trained model and preprocessing artifacts
- Generating a model card for documentation

## Project Goal

Predict the target variable:
- `income == '>50K'` -> 1
- `income <= '50K'` -> 0

The notebook demonstrates how to move from raw tabular data to a deployed-style ML workflow, including model comparison and explainability.

## Dataset

Source: UCI Adult dataset

Features used include:
- Age
- Workclass
- Education
- Marital status
- Occupation
- Relationship
- Race
- Sex
- Capital gain/loss
- Hours per week
- Native country

## Model and Training Approach

The project evaluates multiple models, including:
- Logistic Regression
- Random Forest
- XGBoost

The best-performing model is XGBoost with SMOTE for class balancing. This combination improves recall for the minority class (`>50K`) while maintaining strong overall accuracy.

## Key Results

Final test-set performance of the selected model:
- Accuracy: 0.8431
- Precision: 0.6548
- Recall: 0.7815
- F1-score: 0.7126
- ROC-AUC: 0.9157

These scores indicate a strong balance between accuracy and minority-class detection, which is especially important for imbalanced income prediction tasks.

## Repository Contents

- `Unsupervised ML - Predict Income.ipynb` — main notebook with the full analysis, model training, and evaluation
- `model_card.md` — documentation of the final model, metrics, and limitations
- `income_classifier_model.pkl` — trained XGBoost model
- `scaler.pkl` — saved scaler used during preprocessing
- `label_encoders.pkl` — saved encoders used for categorical features
- `Assignment_Class_3.ipynb` — assignment notebook
- `Solution_Class_3.ipynb` — reference solution notebook

## Environment Setup

Use a Python environment with the following libraries installed:

- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
- xgboost
- shap
- imbalanced-learn
- joblib

Example install:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn xgboost shap imbalanced-learn joblib
```

## How to Run

1. Open the notebook in Jupyter or VS Code.
2. Run all cells in order.
3. The notebook automatically:
   - downloads the dataset,
   - preprocesses the data,
   - trains the models,
   - evaluates them,
   - saves the final model artifacts.

## Notes

- The dataset reflects historical 1994 U.S. income distributions and may not represent current economic patterns.
- The project includes fairness and production considerations in the model documentation.
- The notebook uses SHAP to help explain model predictions and feature importance.

## Intended Use

This is an educational and experimental project for learning:
- machine learning workflows,
- binary classification,
- feature preprocessing,
- class imbalance handling,
- model evaluation,
- and model documentation.
