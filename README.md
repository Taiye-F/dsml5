# Telecom Customer Churn Prediction & Segmentation

## Project Overview
This project performs a full-cycle data science analysis on a telecom company's customer dataset. The goal is twofold:
1.  **Supervised Learning:** Predict which customers are likely to churn (leave the service).
2.  **Unsupervised Learning:** Segment the customer base into meaningful groups to optimize marketing and retention strategies.

By combining classification models with clustering analysis, this project provides actionable insights to reduce customer attrition and improve revenue.

## Dataset
The dataset used is the **Telco Customer Churn** dataset.
*   **Source:** [IBM / GitHub Raw Link](https://raw.githubusercontent.com/IBM/telco-customer-churn-on-icp4d/master/data/Telco-Customer-Churn.csv)
*   **Size:** 7,043 rows, 21 columns.
*   **Key Features:**
    *   **Demographics:** Gender, SeniorCitizen, Partner, Dependents.
    *   **Services:** Phone, Internet (DSL/Fiber), Security, Backup, Streaming, etc.
    *   **Account Info:** Tenure, Contract type, Payment method, Paperless Billing.
    *   **Financials:** MonthlyCharges, TotalCharges.
    *   **Target:** Churn (Yes/No).

## Methodology

### 1. Data Cleaning & Preprocessing
*   Handling missing values (specifically in `TotalCharges`).
*   Data type conversion (Object to Numeric).
*   Encoding categorical variables (One-Hot & Label Encoding).
*   Scaling numerical features for machine learning models.

### 2. Feature Engineering
Created 5+ new features to improve model performance and interpretability:
*   **Tenure Grouping:** Categorized tenure into cohorts (e.g., 0-12 months, 1-2 years, etc.).
*   **Avg Monthly Charges:** Normalized costs based on the number of active services.
*   **Service Flags:** Binary indicators for `Has_Internet`, `Has_Streaming`, `Multiple_Services`.
*   **Interaction Features:** Combined `Contract` type with `MonthlyCharges` to weight value per contract type.

### 3. Exploratory Data Analysis (EDA)
*   Visualized churn rates across demographic and service categories.
*   Correlation heatmaps to identify drivers of churn.
*   Distribution analysis of Monthly and Total Charges.

### 4. Model Building (Supervised)
We trained and evaluated multiple models to predict Churn:
*   **Logistic Regression** (Baseline)
*   **Decision Trees**
*   **Random Forest**
*   **XGBoost / Gradient Boosting**

**Performance Metrics Used:** Accuracy, Precision, Recall, F1-Score, and ROC-AUC.

### 5. Customer Segmentation (Unsupervised)
*   Used **K-Means Clustering** to group customers based on tenure, spending, and service usage.
*   Determined the optimal number of clusters using the **Elbow Method** and **Silhouette Score**.
*   Profiled clusters to identify personas (e.g., "High-Value Loyalists" vs. "New Risk Users").



---
