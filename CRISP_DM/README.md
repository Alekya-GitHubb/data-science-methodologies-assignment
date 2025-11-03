Customer Churn Prediction Using the CRISP-DM Methodology
1. Introduction

This project implements the CRISP-DM (Cross-Industry Standard Process for Data Mining) framework to build a machine learning model for predicting customer churn in the telecommunications industry.

Customer churn analysis is a critical task for telecom service providers, enabling proactive retention strategies and reduction in revenue loss.

Dataset Source:
IBM Telco Customer Churn Dataset — Kaggle
https://www.kaggle.com/datasets/blastchar/telco-customer-churn

2. Business Understanding

Telecommunication companies experience substantial losses due to customer attrition. Predicting which customers are likely to leave allows organizations to:

    Identify at-risk customers early

    Implement targeted retention strategies

    Improve customer satisfaction and revenue stability

Business Objective:
    Develop a churn prediction model to assist customer retention planning.

Success Criteria:

    Reliable prediction accuracy on unseen customer data

    Meaningful insights into churn drivers for business actionability

3. Data Understanding

The dataset consists of customer demographics, service subscription details, billing information, and churn labels. Key activities:

    Loaded and inspected dataset structure

    Analyzed data types, missing values, and distributions

    Conducted exploratory data analysis (EDA) including:

Exploratory Task	            Outcome
Class distribution analysis	    ~26% churn rate (imbalanced)
Categorical feature review	    Contract type, tenure, internet service strongly associated with churn
Correlation patterns	        Tenure, monthly charges, senior citizen status relevant

Visualizations included histograms, boxplots, bar charts, and correlation maps.

4. Data Preparation

Performed data cleaning and preprocessing:

    Handling missing values (TotalCharges)

    Encoding categorical variables using One-Hot Encoding

    Scaling numeric features with StandardScaler

    Splitting data into train, validation, and test sets

The preprocessing pipeline was implemented using ColumnTransformer and saved for future deployment.


5. Modeling

Multiple classification models were trained and evaluated:

Model	                Purpose
Logistic Regression	    Baseline model
Random Forest	        Ensemble learning baseline
XGBoost	                Gradient boosting — final selected model

Model selection was based on validation performance, interpretability, and robustness.

6. Evaluation

Evaluation metrics included:

    Accuracy

    Precision, Recall, F1-score

    ROC-AUC

    Confusion matrix

    Precision-Recall analysis

Additionally, SHAP (SHapley Additive exPlanations) was used to interpret model predictions and identify key churn drivers.
Key Features Indicating Higher Churn Likelihood:

    Month-to-Month contract customers

    Fiber optic internet users

    High monthly charges

    Lower tenure period

    Electronic check payment users

Model demonstrated strong predictive performance and aligned with known industry churn patterns.

7. Deployment

A production-ready serving pipeline was created by combining preprocessing and the trained XGBoost model, then saving it as a serialized file (final_churn_pipeline.pkl).

A sample inference function was tested on hypothetical customer data to demonstrate deployment readiness. This approach enables seamless integration into CRM and retention platforms.

8. Artifacts
Component	                File
CRISP-DM Notebook	        CRISP_DM/notebook.ipynb
Saved pipeline	            CRISP_DM/artifacts/final_churn_pipeline.pkl
Preprocessing object	    Included in final pipeline
requirements.txt	        CRISP_DM/requirements.txt
Visualizations & reports	Contained in notebook

9. Conclusion

This project successfully demonstrates the CRISP-DM methodology applied to telecom churn prediction. The final model exhibits strong predictive performance, actionable feature insights, and deployable pipeline structure.

Future work may include:

    Customer lifetime value modeling

    Uplift modeling for targeted retention campaigns

    A/B testing for retention offers

    Deployment to cloud inference platform (AWS/Streamlit/FastAPI)

10. References

    Kaggle IBM Telco Churn Dataset

    Wirth, R., & Hipp, J. (2000). CRISP-DM: Towards a Standard Process Model for Data Mining

    Lundberg & Lee (2017) — SHAP Framework


Video Demonstration
[Watch the video here](https://youtu.be/mxK2a8GlP2w)

Notebook link: https://colab.research.google.com/drive/1cjzUKRhtiI1hH81ksuwl3Weqj5gdl0DC?usp=sharing

Medium Article: https://medium.com/@alekyagudise1008/predicting-telecom-customer-churn-using-crisp-dm-python-xgboost-shap-ae114634494d

