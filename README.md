# 🛵 Food Delivery ETA Prediction

## 📌 Project Objective
Predicting the estimated time of arrival (ETA) for food deliveries using historical data. This project solves a regression problem by predicting delivery times based on geospatial coordinates, traffic conditions, and temporal features.

## 📊 Dataset Overview
* **Size:** 45,593 delivery records.
* **Key Features:** Delivery partner age & ratings, restaurant and delivery coordinates, order time, weather conditions, and road traffic density.
* **Target Variable:** `Time_taken(min)`

## 🛠️ Tech Stack
* **Data Manipulation:** `pandas`, `numpy`
* **Data Visualization:** `matplotlib`, `seaborn`
* **Machine Learning:** `scikit-learn` (Linear Regression, Decision Tree, Random Forest)

## 🚀 Key Methodologies & Workflow
1. **Data Cleaning & Imputation:** Handled `NaN` string anomalies and imputed missing numeric/categorical values using median and mode strategies respectively.
2. **Geospatial Feature Engineering:** Implemented a vectorized **Haversine formula** to calculate the great-circle distance between restaurants and delivery locations. 
3. **Outlier Detection:** Identified and removed 1% of data points with >100km distances caused by hemisphere coordinate recording errors.
4. **Data Leakage Prevention:** Applied `StandardScaler` strictly *after* the 80/20 train-test split to ensure test data remained entirely unseen.
5. **Model Evaluation:** 
   * **Linear Regression:** Baseline model (RMSE: 6.22, R2: 0.56)
   * **Decision Tree Regressor:** Identified heavy overfitting (Train MSE: ~0.001 vs Test RMSE: 5.45)
   * **Random Forest Regressor:** Implemented an ensemble approach with 100 estimators to resolve overfitting and capture non-linear relationships. *(Final R2 Score: [0.816])*
