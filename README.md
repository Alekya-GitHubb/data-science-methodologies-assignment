Data Mining Methodologies Assignment

A Comparative Study Using CRISP-DM, SEMMA, and KDD Frameworks
1. Introduction

This repository contains three independent machine learning projects implemented using three foundational data-mining methodologies:

    CRISP-DM (Cross-Industry Standard Process for Data Mining)

    KDD (Knowledge Discovery in Databases)

    SEMMA (Sample, Explore, Modify, Model, Assess)

Each methodology is applied to a different real-world dataset and demonstrates systematic end-to-end data science execution, including:

    Problem identification

    Data preprocessing

    Feature engineering

    Model development and evaluation

    Deployment readiness and explainability (SHAP)

The goal of this assignment is to understand, compare, and practically apply three industry-recognized data-mining frameworks using modern machine learning workflows.


2. Project Structure

Root Folder
│── CRISP_DM/
│   ├── notebook.ipynb
│   ├── artifacts/
│   ├── README.md
│   ├── requirements.txt
│── SEMMA/
│   ├── notebook.ipynb
│   ├── artifacts/
│   ├── README.md
│   ├── requirements.txt
│── KDD/
│   ├── notebook.ipynb
│   ├── artifacts/
│   ├── README.md
│   ├── requirements.txt
│── README.md (Master file)

Each folder includes a Jupyter Notebook, model artifacts, requirements, and methodology-specific documentation.

3. Methodologies Overview
3.1 CRISP-DM
Phase	                        Activities Completed
Business Understanding	        Defined churn prediction objective
Data Understanding	            Exploratory data analysis, distribution checks
Data Preparation	            Encoding, scaling, train-test split
Modeling	                    Logistic Regression, Random Forest, XGBoost
Evaluation	                    Accuracy, Confusion Matrix, ROC-AUC, SHAP
Deployment	                    Final ML pipeline saved

Dataset: IBM Telco Customer Churn (Kaggle)
Objective: Predict telecom customer churn

3.2 SEMMA
Phase	        Activities Completed
Sample	        Stratified data split into train/val/test
Explore	        Visualizations & statistical analysis
Modify	        Preprocessing pipeline creation
Model	        Random Forest, XGBoost (final)
Assess	        Classification metrics, SHAP, ROC curve

Dataset: Heart Disease Prediction (Kaggle)
Objective: Predict heart disease presence based on clinical indicators

3.3 KDD
Step	            Activities Completed
Selection	        Extracted multiple tables from Olist dataset
Pre-processing	    Merging, cleaning, missing handling
Transformation	    Feature engineering, encoding, scaling
Data Mining	        Logistic Regression, XGBoost (final)
Interpretation	    SHAP feature importance, confusion matrix

Dataset: Brazilian Olist E-commerce (Kaggle)
Objective: Predict whether a customer will leave a low product review

4. Tools & Technologies
Category	    Tools
Language	    Python
Libraries	    Pandas, NumPy, Scikit-Learn, XGBoost, SHAP, Matplotlib, Seaborn
Environment	    Google Colab / Jupyter Notebook
Versioning	    Git / GitHub

5. Key Deliverables

✅ Three methodology-specific machine learning projects
✅ Fully reproducible notebooks
✅ Deployment-ready sklearn pipelines
✅ SHAP explainability for all models
✅ Train/validation/test methodology followed
✅ Professional documentation for each methodology
✅ Final model artifacts stored in repository
✅ requirements.txt files for reproducibility

6. Comparative Summary
| Aspect           | CRISP-DM            | SEMMA             | KDD                            |
| ---------------- | ------------------- | ----------------- | ------------------------------ |
| Primary Use      | General Data Mining | SAS Data Mining   | Database Knowledge Extraction  |
| Focus            | Business & Process  | Modeling workflow | Data transformation & patterns |
| Dataset          | Telecom churn       | Heart disease     | E-commerce reviews             |
| Final Model      | XGBoost             | XGBoost           | XGBoost                        |
| Interpretability | Yes (SHAP)          | Yes (SHAP)        | Yes (SHAP)                     |

7. Results (High-Level Performance)
| Project  | Task                       | Model   | Performance (Approx)            |
| -------- | -------------------------- | ------- | ------------------------------- |
| CRISP-DM | Churn prediction           | XGBoost | ~80–85% accuracy                |
| SEMMA    | Heart disease prediction   | XGBoost | ~85–90% accuracy                |
| KDD      | Negative review prediction | XGBoost | Balanced metrics; strong recall |


| No. | Experiment | Open in Colab |
|:--:|:--|:--|
| 1️⃣ | **CRISPDM** | [Open Colab 1](https://colab.research.google.com/drive/1cjzUKRhtiI1hH81ksuwl3Weqj5gdl0DC?usp=sharing) |
| 2️⃣ | **KDD** | [Open Colab 2](https://colab.research.google.com/drive/1AsFTE3ceZ6rFl7KUratQQCu6aVvTn7zg?usp=sharing) |
| 3️⃣ | **SEMMA** | [Open Colab 2](https://colab.research.google.com/drive/15BkG0nGoIhG0iWBXRlbo3SC-tnWtqneV?usp=sharing) |


8. How to Run
Install Dependencies
    pip install -r requirements.txt

Run Jupyter Notebook
    jupyter notebook


Each methodology folder contains its own:

    Notebook

    Model pipeline files

    Environment specification

9. Academic Integrity Statement

All analysis, modeling steps, and documentation were completed independently using CRISP-DM, SEMMA, and KDD methodologies as part of an academic data-mining assignment. External tools like ChatGPT were used only for iterative guidance and refinement, with all code verified and executed manually.

10. References

    Fayyad, U., Piatetsky-Shapiro, G., & Smyth, P. (1996). Knowledge Discovery in Databases

    Wirth, R. & Hipp, J. (2000). CRISP-DM Standard Process Model

    SAS Institute: SEMMA Methodology

    Kaggle Datasets (Telco Churn, Heart Disease, Olist Ecommerce)

    SHAP Explainability: Lundberg & Lee (2017)
