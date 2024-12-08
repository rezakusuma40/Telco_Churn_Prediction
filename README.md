# Telco Churn Prediction

This project focuses on predicting customer churn for a telecommunications company. The goal is to identify at-risk customers and provide actionable insights to help the company retain its customers and reduce churn.

## Project Overview

Customer churn is a critical challenge for subscription-based businesses. By using historical customer data, this project builds predictive models to classify whether a customer will churn or not. It also explores key factors contributing to churn through exploratory data analysis (EDA). The insights gained can inform targeted retention strategies, such as offering incentives to high-risk customers.

### Key Objectives
1. Develop a predictive model to classify churn effectively, minimizing false negatives.
2. Understand the characteristics of customers prone to churn.
3. Highlight actionable recommendations based on insights and predictions.

## Dataset Description

The dataset, **Telco Customer Churn**, is sourced from [Kaggle](https://www.kaggle.com/blastchar/telco-customer-churn). It contains customer information, including demographic details, services used, payment patterns, and churn status.

### Key Features:
- **Numerical**:  
  - `tenure`: Number of months the customer has been with the company.  
  - `MonthlyCharges`: The amount charged to the customer per month.  
  - `TotalCharges`: Total amount charged during the customer's tenure.  

- **Categorical**:  
  - `Contract`: Type of contract (Month-to-month, One year, Two year).  
  - `PaymentMethod`: Payment method used by the customer.  
  - `InternetService`: Type of internet service (DSL, Fiber optic, None).  

- **Target**:  
  - `Churn`: Whether the customer has churned (Yes/No).  

### Dataset Size:
- Total rows: 7,043  
- Total columns: 21  

## Exploratory Data Analysis (EDA)

EDA was conducted to uncover patterns and trends in the data:  
1. **Churn Distribution**:  
   - Around 27% of customers in the dataset have churned.  

2. **Customer Behavior Analysis**:  
   - Customers with **month-to-month contracts** churn the most compared to those with longer-term contracts.  
   - **High monthly charges** correlate with higher churn rates.  
   - Many customers has **low monthly charges** and **long tenure duration**.  
   - Many customers use **Fiber-optic** but the churn rate of these users is high too.  
   - Those who pay with **electronic check** are most likely to churn compared to other methods.  
3. **Demographic Insights**:  
   - Seniors are slightly more likely to churn than younger customers.  

These findings were visualized using bar plots, box plots, histogram, and heatmaps to better understand the relationships between variables.

## Workflow

### 1. Data Preprocessing
- **Data Cleaning**: Fixed missing values in `TotalCharges` by imputing them with appropriate values.  
- **Encoding**:  
  - Dummy encoding for Logistic Regression.  
  - Ordinal encoding for tree-based models like Random Forest and XGBoost.  
- **Class Imbalance Handling**:  
  - Used SMOTE and Random Under Sampling to address the imbalance in churn labels.  

### 2. Modeling
- **Models Used**:  
  - Logistic Regression  
  - Random Forest  
  - AdaBoost  
  - XGBoost  
- **Hyperparameter Tuning**:  
  - Grid search and cross-validation were applied and performances are compared accross every model and between models with or without hyperparameter tuning.  
- **Evaluation Metrics**:  
  - **Recall**: Primary metric to minimize undetected churners.  

### 3. Model Evaluation
- The best-performing model was **AdaBoost**, achieving:  
  - Recall: **86%**  
- Unfortunatelty the models showed overfitting tendencies.  

## Tools and Libraries
- **Python Libraries**:  
  - Data handling: `pandas`, `numpy`  
  - Visualization: `matplotlib`, `seaborn`  
  - Modeling: `scikit-learn`, `imblearn`, `xgboost`  
- **Platform**: Google Colab  

## Key Insights and Recommendations
1. **Short-tenure customers with high monthly charges** are at the highest risk of churning.  
   - Action: Provide retention offers to these customers, such as discounts or incentives to switch to longer-term contracts.  

2. **Month-to-month contracts** have significantly higher churn rates.  
   - Action: Encourage customers to switch to annual contracts by offering discounts or rewards.  

3. Customers with **manual payment methods** show higher churn likelihood.  
   - Action: Promote automatic payment options through campaigns highlighting their convenience.  

By focusing on these high-risk groups, the company can effectively reduce churn and enhance customer retention.
