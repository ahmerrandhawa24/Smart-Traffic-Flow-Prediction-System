Smart Traffic Flow Prediction System

## Project Overview
This project is an **industrial-level Machine Learning system** designed to predict traffic conditions on a highway based on historical and environmental data.

The system analyzes patterns such as:
- Weather conditions 🌦️  
- Time-based features ⏰  
- Previous traffic trends 🚗  

### And predicts:
- ✔ Future traffic volume (Regression)  
- ✔ Traffic congestion level (Classification)  
- ✔ Traffic trend (Increasing / Decreasing)  
- ✔ Alert level (Safe / Moderate / High Traffic)


---

## Objectives
- Predict next hour traffic volume  
- Classify traffic into:
  - Low  
  - Medium  
  - High  
- Detect traffic trends 📈  
- Provide real-time insights through an interactive UI  

---

## Dataset Description
The dataset contains **48,000+ records** of highway traffic data.

### Features used:
- holiday  
- temp  
- rain_1h  
- snow_1h  
- clouds_all  
- weather_main  
- is_weekend  
- is_rush_hour  
- traffic_lag1 (previous hour traffic)  

### Time-based features:
- hour_sin, hour_cos  
- day_sin, day_cos  
- month_sin, month_cos  
- hour  

### Target:
- traffic_volume  

---

## Data Preprocessing
The following steps were performed:
- Handling missing values  
- Encoding categorical features  
- Feature engineering:
  - Time-based cyclic encoding (sin/cos)  
  - Rush hour detection  
  - Weekend detection  
- Creation of lag feature (`traffic_lag1`)  
- Feature scaling (Standardization)  

---

## Exploratory Data Analysis (EDA)

### Key insights:
- Traffic peaks during rush hours  
- Weather conditions affect traffic flow  
- Strong correlation between previous traffic and future traffic  

---

## Model Building

### Models Tested:
- Linear Regression  
- Decision Tree  
- Random Forest ✅ (Selected)  
- XGBoost  

### Final Model:
**Random Forest Regressor**

### Performance:

| Model              | MAE | RMSE |
|--------------------|-----|------|
| Linear Regression  | 470 | 671  |
| Decision Tree      | 186 | 315  |
| Random Forest      | 158 | 272  |
| XGBoost            | 171 | 284  |

---

## Feature Importance

Top contributing features:
- traffic_lag1 (Most important)  
- hour_cos  
- hour_sin  
- day_sin  

This shows that **previous traffic and time patterns** are the strongest predictors.

---

## Streamlit Application

An interactive web app was built using **Streamlit**.

### Features:
- User input for traffic conditions  
- Real-time prediction  
- Traffic level classification  
- Trend detection
- Alert system

- - ## Example Output
- Predicted Traffic: 847.61
- Traffic Level: LOW
- Trend: INCREASING 📈
- Alert: SAFE
