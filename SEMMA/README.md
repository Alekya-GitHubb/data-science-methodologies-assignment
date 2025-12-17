Heart Disease Prediction Using the SEMMA Methodology

1. Introduction

This project applies the SEMMA (Sample–Explore–Modify–Model–Assess) data mining methodology to develop a predictive model for heart disease diagnosis using a real-world healthcare dataset.

The primary objective is to identify whether a patient is likely to have heart disease based on demographic, clinical, and physiological features. Early detection of heart disease plays a critical role in prevention, treatment planning, and reducing mortality rates.

Dataset Source:
Heart Failure Prediction Dataset — Kaggle
https://www.kaggle.com/datasets/fedesoriano/heart-failure-prediction


2. Problem Definition

The task is a binary classification problem, where the target variable indicates the presence or absence of heart disease:

    HeartDisease = 1 → Patient has heart disease

    HeartDisease = 0 → Patient does not have heart disease

The dataset contains clinically relevant factors, including age, cholesterol level, chest pain type, resting blood pressure, maximum heart rate, and electrocardiographic results.

The study aims to:

    Build a predictive model using machine learning techniques

    Evaluate model performance using appropriate metrics

    Provide interpretability of results using SHAP-based feature importance


3. SEMMA Methodology Implementation
3.1 Sample

    Imported dataset from Kaggle

    Conducted an initial quality check (no missing values present)

    Split the dataset into:

        Training set: 70%

        Validation set: 15%

        Testing set: 15%

    Ensured balanced representation of classes in each subset through stratified sampling

3.2 Explore

Performed exploratory data analysis (EDA) to understand variable distributions and relationships:

    Descriptive statistics and summary metrics

    Correlation heatmap among numerical variables

    Histograms and boxplots for distribution analysis

    Comparative analysis of key features against the target variable (HeartDisease)

Key Observations:

    Higher age, lower maximum heart rate (MaxHR), elevated Oldpeak, and certain chest pain types correlate strongly with heart disease

    The dataset is balanced and suitable for supervised learning without the need for imbalance handling techniques

3.3 Modify

Pre-processing and feature preparation included:

    One-Hot Encoding of categorical variables

    Standardization of numerical features using StandardScaler

    Creation of a ColumnTransformer-based preprocessing pipeline

    Saved preprocessing pipeline for reproducibility and deployment consistency

3.4 Model

Trained and compared multiple machine learning models:

Model	                            Purpose
Logistic Regression	                Baseline classifier
Random Forest Classifier        	Ensemble-based model
XGBoost Classifier	                Gradient boosting algorithm

The full modeling pipeline was constructed using scikit-learn Pipeline, combining preprocessing and model stages.

The XGBoost classifier demonstrated the highest performance on the validation dataset and was selected as the final model.

3.5 Assess

Final evaluation was performed on the previously unseen test dataset.
Evaluation metrics included:

    Accuracy

    Precision

    Recall

    F1-score

    ROC-AUC score

    Confusion matrix

To enhance interpretability, SHAP (SHapley Additive exPlanations) values were computed to analyze the contribution of each feature to model predictions.

Top predictive features identified:

    ST depression induced by exercise (Oldpeak)

    Maximum heart rate achieved (MaxHR)

    Type of chest pain

    Age

    ST segment slope

These findings align with established clinical knowledge, providing validation for the model’s behavior.

4. Artifacts

    Notebook: SEMMA/notebook.ipynb

    Saved model pipeline: SEMMA/artifacts/heart_disease_final_pipeline.pkl

    Preprocessing pipeline: Included within model

    Plots and evaluation figures: Located in project notebook

    Environment file: requirements.txt


5. Conclusion

The SEMMA methodology was successfully applied to the heart disease prediction problem, demonstrating its effectiveness for structured data mining workflows. The final model achieved strong predictive performance and provided clinically relevant insights.

The integration of preprocessing and model training into a single pipeline ensures reproducibility and deployment readiness. Future work may include:

    Hyperparameter optimization

    Feature selection techniques

    Comparison with deep learning models

    Development of a web-based inference interface (FastAPI/Streamlit)

6. References

    Kaggle Heart Disease Dataset: https://www.kaggle.com/datasets/fedesoriano/heart-failure-prediction

    SAS Institute Inc. SEMMA Methodology

    Lundberg, S.M., & Lee, S.I. (2017). A Unified Approach to Interpreting Model Predictions (SHAP)
   

Video Demonstration
[Watch the video here](https://drive.google.com/file/d/1lVB8jxs1BiyrshiD8noePu_ALBHoWSzd/view?usp=sharing)

Notebook link: https://colab.research.google.com/drive/15BkG0nGoIhG0iWBXRlbo3SC-tnWtqneV?usp=sharing

Medium Article: https://medium.com/@alekyagudise1008/heart-disease-prediction-using-semma-framework-python-xgboost-shap-ab2fc72f70f3
