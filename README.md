# Telecom Customer Churn Prediction

## Project Overview
This project aims to predict which customers are likely to leave a telecom company (churn) using machine learning techniques. Customer churn is a critical problem for telecom businesses because retaining existing customers is more cost-effective than acquiring new ones. By predicting churn, companies can take proactive measures to retain high-risk customers.

## Dataset
The dataset used is the **Telco Customer Churn Dataset** containing **7043 rows and 21 columns**, including:

- `customerID` – Unique customer identifier  
- `gender`, `SeniorCitizen`, `Partner`, `Dependents` – Demographics  
- `tenure` – Number of months the customer stayed  
- `PhoneService`, `InternetService`, `Contract`, `PaymentMethod` – Service information  
- `MonthlyCharges`, `TotalCharges` – Billing information  
- `Churn` – Target variable (Yes/No)  

### Preprocessing
- Removed `customerID` as it is not useful for modeling  
- Converted categorical variables using **Label Encoding** and **One-Hot Encoding**  
- Converted `TotalCharges` to numeric and filled missing values with median  
- Split dataset into **80% training** and **20% testing**  

## Exploratory Data Analysis (EDA)
- Churn distribution: ~27% of customers left  
- Month-to-month contract customers have higher churn  
- Shorter tenure and higher monthly charges are associated with higher churn  
- Features like TechSupport and OnlineSecurity reduce churn probability  

Visualizations include **histograms, countplots, and correlation heatmaps**.

## Models Used
Four machine learning models were trained and evaluated:

1. Logistic Regression  
2. Decision Tree Classifier  
3. Random Forest Classifier  
4. XGBoost Classifier  

### Evaluation Metrics
Models were evaluated using **Accuracy, Precision, Recall, F1 Score**, and **Confusion Matrix**.  

| Model                 | Accuracy | Precision | Recall  | F1 Score |
|-----------------------|---------|-----------|--------|----------|
| Logistic Regression   | 0.824   | 0.696     | 0.595  | 0.642    |
| Decision Tree         | 0.769   | 0.577     | 0.475  | 0.521    |
| Random Forest         | 0.796   | 0.672     | 0.450  | 0.539    |
| XGBoost               | 0.787   | 0.616     | 0.520  | 0.564    |

- Logistic Regression had the highest **overall accuracy**  
- XGBoost and Random Forest better handle **minority churn class**  
- Top features affecting churn: `tenure`, `Contract`, `MonthlyCharges`, `InternetService`

## Key Insights
- Short tenure, month-to-month contracts, and high monthly charges increase churn risk  
- Providing TechSupport or OnlineSecurity services can reduce churn  
- Simple models like Logistic Regression can sometimes outperform complex models on small/simple datasets  

