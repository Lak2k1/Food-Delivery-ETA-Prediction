# 🛵 Food Delivery ETA Prediction

## 📌 Project Objective
Predicting the estimated time of arrival (ETA) for food deliveries using historical data. This project solves a regression problem by predicting delivery times based on geospatial coordinates, traffic conditions, and temporal features.

## 📊 Dataset 
* **Size:** 45,593 delivery records.
* **Source:** [Click here to view the dataset](https://www.kaggle.com/datasets/gauravmalik26/food-delivery-dataset)

## 🛠️ Tech Stack
* **Data Manipulation & Visualization:** `pandas`, `numpy`, `matplotlib`, `seaborn`
* **Machine Learning:** `scikit-learn`, `xgboost` (Linear Regression, Random Forest, XGBoost)

## 🚀 Key Methodologies & Workflow
1. **Data Cleaning:** Handled hidden `NaN` string anomalies and imputed missing fields using statistical measures.
2. **Geospatial Feature Engineering:** Implemented a vectorized **Haversine formula** to calculate the actual distance between restaurants and delivery locations. 
3. **Outlier Detection:** Filtered out erroneous data points with >100km distances caused by hemisphere coordinate recording errors.
4. **Data Leakage Prevention:** Applied `StandardScaler` strictly *after* the train-test split to ensure test data remained entirely unseen.
5. **Model Evaluation:** 
   * **Linear Regression (Baseline):** $R^2$: 0.56 | RMSE: 6.22 mins
   * **XGBoost Regressor:** $R^2$: 0.82 | RMSE: 3.98 mins *(Massive 26% absolute improvement over baseline)*

## 💡 How to View
Simply open the `.ipynb` file in this repository to view the full Exploratory Data Analysis (EDA) and model training pipeline.
