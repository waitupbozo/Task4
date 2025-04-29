# Breast Cancer Prediction Analysis Report

## Introduction

This report documents the analysis performed on the Breast Cancer Wisconsin (Diagnostic) dataset to build a predictive model for breast cancer diagnosis. The analysis involves data exploration, preprocessing, model training, and evaluation.

## Dataset

The dataset used is the Breast Cancer Wisconsin (Diagnostic) dataset, containing features computed from digitized images of fine needle aspirates (FNA) of breast mass. It includes characteristics like radius, texture, perimeter, area, smoothness, compactness, concavity, concave points, symmetry, and fractal dimension. The target variable is 'diagnosis', indicating whether the diagnosis is malignant (M) or benign (B).


## Data Exploration and Preprocessing

1. **Data Loading and Inspection:** The dataset was loaded using pandas and inspected using `head()`, `size`, `shape`, and `info()` methods. The dataset contains 569 instances and 33 features (including the target variable).
2. **Handling Missing Values:** The dataset was checked for missing values using `isnull().sum()`. An unnecessary column ('Unnamed: 32') was removed.
3. **Feature Engineering:** The target variable 'diagnosis' was encoded to numerical values (M: 1, B: 0) for model compatibility.


## Model Training and Evaluation

**Model Selection:** Logistic Regression was chosen as the classification model.

**Data Splitting:** The dataset was split into training and testing sets using `train_test_split` with a test size of 20% (114 samples for testing) and a random state of 42 for reproducibility.

**Data Preprocessing:**
- **Categorical Features:** One-Hot Encoding was applied using `OneHotEncoder` to handle categorical features, if any were present.
- **Numerical Features:** Standard scaling was applied using `StandardScaler` to standardize numerical features.
- **Column Transformer:** A `ColumnTransformer` was used to combine the preprocessing steps for both categorical and numerical features.
- **Pipeline:** A `Pipeline` was created to streamline the preprocessing and model training steps.


**Model Evaluation Metrics:**
- **Confusion Matrix:** A confusion matrix was generated to visualize the model's performance. The confusion matrix showed:
    - True Negative (TN): 70
    - False Positive (FP): 1
    - False Negative (FN): 2
    - True Positive (TP): 41
- **Precision, Recall, and ROC AUC Score:** The model achieved:
    - Precision: 0.98
    - Recall: 0.98
    - ROC AUC Score: 0.97
- **ROC Curve:** A Receiver Operating Characteristic (ROC) curve was plotted to visualize the trade-off between true positive rate and false positive rate at various thresholds. The ROC curve showed an area under the curve (AUC) of 0.97, indicating excellent discrimination ability.

## Threshold Optimization
**Precision-Recall Curve** Was used to optimize the model to get best classification perfromance. The optimization resulted in selecting a threshold of 0.4
**Macro-average F1 score:** Was used to assess the perfromance at the diffrent classification threshold the best threshold result in F1-Score of 0.98

## Conclusion

The Logistic Regression model achieved high accuracy in predicting breast cancer diagnosis, with a precision of 0.98, recall of 0.98, and an ROC AUC score of 0.97. The evaluation metrics and visualization provided insights into the model's performance, demonstrating its effectiveness in classifying malignant and benign cases. After threshold optimization an F1-Score of 0.98 was achieved which means  the model is very effective for this task.
