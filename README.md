# Breast Cancer Classification Project

## Overview
This project focuses on building and evaluating machine learning models to classify breast cancer cases based on diagnostic data. The goal is to accurately distinguish between malignant (cancerous) and benign tumours (non-cancerous) using various classification algorithms.

**Fine needle aspiration** is a biopsy procedure (dataset is based on this) that can help diagnose or rule out conditions, such as cancer. 
(This is an invasive procedure, whereas procedures like ultrasound are not invasive.)

**General Observations/Factors:** 
 
*   A basic LR model yields an accuracy of 0.956 with the training data and 0.912 with the test data, which is fatal when it comes to fields like healthcare.
*   **False-Benign** are more dangerous than **False-Malignant** as they can cost the life of a person, and hence features like precision, recall, and F1-score come in handy (including weighted precision).

## Dataset
The dataset contains features extracted from breast cancer biopsies. It includes multiple numeric variables related to tumor characteristics and a target variable indicating cancer diagnosis (malignant or benign).

## Objectives
- Preprocess and engineer features to improve model performance.
- Handle class imbalance using techniques such as class weighting.
- Train and compare multiple classification models, including:
  - Logistic Regression (LR)
  - Decision Trees (DT)
  - Random Forest (RF)
  - XGBoost
- Evaluate model performance using relevant metrics for healthcare applications:
  - Accuracy
  - Precision
  - Recall
  - F1 Score

## Methodology
1. Cleaned and preprocessed the data, including normalisation and handling missing values.
2. Applied feature engineering and removed less informative/noisy features (e.g., `fractal_dimension_mean`).
3. Balanced the classes by adjusting class weights.
4. Trained multiple classifiers and conducted cross-validation to ensure robustness.
5. Selected Logistic Regression (with modifications) as the final model based on performance metrics.

## Train Performance
- Virtually unchanged after dropping `fractal_dimension_mean`, indicating model robustness and no overfitting.
- The model maintained strong capacity without the noisy feature.

## Test Performance Improvements

| Metric    | Improvement  |
|-----------|--------------|
| Accuracy  | +0.8%        |
| Recall    | +2.5%        |
| Precision | +0.1%        |
| F1 Score  | +1.3%        |

- **Recall (97.7%)** is especially critical, reflecting the model's ability to detect almost all malignant tumours.
- Only **1 false negative** in the test data — a significant achievement, reducing the risk of missed cancer diagnoses.
- Dropping the feature `fractal_dimension_mean` improved generalisation, suggesting it was noisy or less informative.

### Final Model Highlights
- High accuracy and recall on both train and test sets demonstrate strong generalisation.
- The model balances precision and recall effectively, crucial in healthcare to reduce both false positives and false negatives.
- The refined Logistic Regression model is a reliable tool for breast cancer classification with minimal risk of dangerous misclassification.
