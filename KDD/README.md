Customer Review Outcome Prediction Using the KDD Methodology
1. Introduction

This project applies the KDD (Knowledge Discovery in Databases) methodology to predict negative customer reviews in an e-commerce environment. The goal is to identify orders likely to receive low ratings so that customer experience teams can intervene proactively and prevent dissatisfaction.

Dataset Source:
Brazilian E-Commerce Public Dataset — Olist (Kaggle)
https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce

The dataset contains multiple inter-related tables describing orders, customers, sellers, products, payments, and review outcomes, making it suitable for a comprehensive KDD pipeline.

2. Problem Definition

Objective:
Predict whether a customer review for an order will be negative (rating ≤ 3).

Type:
Binary classification

Target Variable:

    1 → low review / dissatisfied customer

    0 → high review / satisfied customer

This problem closely reflects real-world customer experience analytics and service quality monitoring within online retail platforms.

3. KDD Framework Implementation
3.1 Data Selection

Relevant tables extracted:

Table	                Purpose
orders	                Order lifecycle details
customers	            Customer identification & location
order_reviews	        Target variable (review score)
order_items	            Product-level details per order
order_payments	        Payment type and value
products	            Product metadata

Only completed (non-cancelled) orders were retained for modeling.


3.2 Data Pre-processing

    Merged datasets using keys: order_id and customer_id

    Handled null or incomplete order fields

    Removed cancelled orders and incomplete deliveries

    Converted date-time columns to datetime types

    Ensured correct numeric formatting for monetary values

    Created binary target variable:
        review_score <= 3 → 1, otherwise 0

3.3 Data Transformation & Feature Engineering

Engineered features to capture logistics, payment, and customer behavior patterns:

Feature	                        Description
review_score_binary	            Target label
delivery_time_days	            Delivered date – purchase date
delay_flag	                    Delivered past estimated date
num_items	                    Number of products in order
total_price	                    Sum of item prices per order
freight_value_total	            Total shipping cost
payment_installments	        Number of payment installments
payment_type	                Encoded payment method
customer_city/state	            Location-based features

Used One-Hot Encoding for categorical attributes and StandardScaler for continuous variables.

3.4 Data Mining / Modeling

Models trained & compared:

Model	                Notes
Logistic Regression	    Baseline classifier
Random Forest	        Non-linear ensemble model
XGBoost	                Final selected model due to best validation performance

Data split: Train 70% / Validation 15% / Test 15%

3.5 Interpretation / Evaluation

Evaluated on unseen test data using:

    Accuracy

    Precision & Recall

    F1-score

    ROC-AUC

    Confusion Matrix

Used SHAP to understand key drivers of negative reviews.

Most influential factors:

Feature	            Influence
Delivery delay	    Significant positive indicator for negative feedback
Delivery time	    Longer delivery → higher complaint likelihood
Payment type	    Certain methods correlate with dissatisfaction
Freight + product   price	High freight relative to cost → dissatisfaction
Customer location	Geography impacts logistics experience

These insights align with known e-commerce service failure patterns (late delivery, cost concerns, customer logistics geography).

4. Artifacts

Component	        Location
KDD notebook	    KDD/notebook.ipynb
Model file	        KDD/artifacts/kdd_final_pipeline.pkl
Preprocessor	    Included inside model pipeline
requirements.txt	KDD/requirements.txt

Screenshots & plots	In notebook and screenshots folder

5. Conclusion

The KDD methodology effectively structured a large-scale multi-table retail dataset into a predictive problem. The final model demonstrated strong performance in predicting negative reviews and provided actionable insights into customer dissatisfaction drivers, particularly delivery timeliness and logistics cost-to-value ratio.

Future enhancements:

    Text analysis of review comments

    Customer lifetime value integration

    Advanced time-based feature extraction

    Deployment using Streamlit / FastAPI


6. References

    Kaggle — Olist Brazilian E-Commerce Dataset

    Fayyad et al. (1996) — Knowledge Discovery in Databases

    Lundberg, S.M., & Lee, S.I. — SHAP Explainability Framework


Video Demonstration
[Watch the video here]:((https://drive.google.com/file/d/15s9P3lxOt3i54NsDHXFI1hO7lVYQXj-z/view?usp=sharing))

Notebook link: https://colab.research.google.com/drive/1ObFyg9Fvy7IpokvDJTIGIn9dQOR5RmXS?usp=sharing

Medium Article: https://medium.com/@alekyagudise1008/applying-kdd-methodology-to-predict-customer-dissatisfaction-in-e-commerce-olist-dataset-python-e50ad74fda11
