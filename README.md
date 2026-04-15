# Telecom Churn Prediction Modeling

## 📌 Project Overview
This repository contains a comprehensive Jupyter Notebook (`Telecom Churn Prediction Modeling.ipynb`) focused on predicting customer churn for a telecommunications company. The project implements an end-to-end machine learning pipeline, progressing from data cleaning and feature selection to the implementation of advanced ensemble techniques.

The primary objective is to identify customers at risk of leaving (churning) by analyzing their demographics, account information, and service usage patterns. The project evaluates several individual classifiers and combines them using **Voting** and **Stacking** methods to achieve robust predictive performance.

## 🛠️ Project Workflow
The notebook follows a structured end-to-end data science pipeline:

1.  **Data Loading & Initial Exploration**:
    * Loading the telecom churn dataset (`telecom_churn.xlsx`).
    * Performing descriptive statistical analysis to understand data distributions and identify potential issues.
2.  **Pre-processing & Cleaning**:
    * **Column Removal**: Dropping unnecessary identifiers like `customerID`.
    * **Target Encoding**: Converting the categorical target variable (`Churn`) into a numerical format.
    * **Missing Value Handling**: Checking for and addressing null values within the dataset.
3.  **Model-Specific Feature Engineering**:
    * Implementing specific feature selection logic for linear and distance-based models (Logistic Regression and KNN) using correlation thresholds to manage multicollinearity and relevance.
4.  **Model Training & Hyperparameter Optimization**:
    * Training baseline models: Logistic Regression, KNN, Random Forest, XGBoost, CatBoost, and LightGBM.
    * Utilizing **Optuna** for automated hyperparameter tuning to find the best configuration for each algorithm.
5.  **Ensemble Methods**:
    * **Voting Classifier**: Combining multiple models using both Hard and Soft voting strategies.
    * **Stacking Classifier**: Implementing a meta-model approach (`passthrough=True`) to learn how to best combine the predictions of base learners.
6.  **Explainability**:
    * Using **SHAP (SHapley Additive exPlanations)** and feature importance plots to interpret the decisions of the best-performing tree-based models.

## ⚠️ Methodology & Computational Constraints
* **Task-Related Thresholds**: During the feature selection phase for Logistic Regression and KNN, specific thresholds were applied (e.g., target correlation > 10% and inter-feature correlation < 70%). These thresholds were determined based on the **specific requirements of this task** and may vary from standard industry defaults depending on the dataset's noise levels and the desired model sensitivity.
* **Hardware Limitations**: Because the complex tree-based models (Random Forest, XGBoost, CatBoost, and LightGBM) and the extensive Optuna optimization trials were carried out on a **local machine**, the model performances may be "not ideal." Limited computational resources prevented more exhaustive hyperparameter searches or deeper training cycles that could potentially yield higher accuracy.

## 💻 Technologies Used
-   **Python 3.x**
-   **Data Analysis**: Pandas, NumPy
-   **Visualization**: Matplotlib, Seaborn
-   **Machine Learning**: Scikit-Learn, XGBoost, LightGBM, CatBoost
-   **Optimization**: Optuna
-   **Explainability**: SHAP
-   **Statistical Analysis**: Statsmodels (VIF)

## 🚀 How to Use
1.  **Dataset**: Ensure the file `telecom_churn.xlsx` is located in the same directory as the notebook.
2.  **Dependencies**: Install the required libraries via pip:
    ```bash
    pip install pandas numpy seaborn matplotlib scikit-learn optuna xgboost lightgbm catboost shap openpyxl statsmodels
    ```
3.  **Execution**: Open `Ensemble Models Task.ipynb` in Jupyter Lab, Jupyter Notebook, or VS Code and run the cells sequentially to reproduce the analysis and model results.

---

*Created as part of a professional development exercise in Ensemble Modeling & Customer Analytics.*
