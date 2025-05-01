# 🏡 Airbnb Price Optimization – Amsterdam 🇳🇱  
*End-to-End Machine Learning + Power BI Case Study*

A full-scale data science project that simulates the responsibilities of a **Data Analyst / ML Engineer**—from data cleaning to model deployment and business storytelling.

---

## 🎯 Business Objective

Amsterdam is one of Europe's busiest Airbnb markets. However, many hosts struggle with suboptimal pricing that ignores listing quality, seasonal demand, or competition.

This project solves that by:

- 🧠 Predicting **ideal listing prices** using machine learning
- 🎯 Minimizing prediction error using **segment-based modeling**
- 📊 Presenting insights through an **interactive Power BI dashboard**
- 📈 Helping stakeholders make **data-driven pricing decisions**

---

## 💼 Business Value Delivered

✅ Increased pricing accuracy for **94% of listings under $600**  
✅ Reduced model error by segmenting high-variance luxury properties  
✅ Identified **top price drivers** like room type, location, host status  
✅ Delivered a **non-technical dashboard** to support business decisions  

This pipeline reflects how data science translates into **real business value**.

---

## 🧰 Tools & Technologies

| Category               | Tools / Technologies                                                                 |
|------------------------|--------------------------------------------------------------------------------------|
| Programming            | Python                                                                               |
| Data Processing        | Pandas, NumPy                                                                        |
| Visualization (EDA)    | Seaborn, Matplotlib                                                                  |
| Machine Learning       | Scikit-learn, XGBoost, Random Forest, AdaBoost, SVR                                  |
| Feature Engineering    | Label Encoding, One-Hot Encoding, IQR Outlier Handling                               |
| Model Tuning           | RandomizedSearchCV                                                                   |
| Evaluation Metrics     | MAE, RMSE, R² Score, Residual Analysis                                               |
| Business Intelligence  | Power BI                                                                             |
| Version Control        | Git, GitHub                                                                          |

---

## 🔍 Exploratory Data Analysis (EDA)

📂 **Dataset**: 9,600+ Airbnb listings | 75+ features

### 🔑 Key Steps:
- Detected price **outliers using IQR**
- Created **price bins** and business-relevant **segments**
- Analyzed price behavior across:
  - Room type
  - Neighborhood
  - Availability
  - Review scores
  - Host type

### 🔍 Notable Insights:
- 📉 Most listings fall below $600, but price is heavily skewed
- 🏘️ Location and room type strongly influence pricing
- ⭐ Amenities and Superhost status correlate with higher prices

📓 Notebook: `notebooks/AirBnB_price_EDA.ipynb`

---

## 🤖 Modeling & Evaluation

### 🔬 Models Tested:
- Linear Regression
- Decision Tree Regressor
- Random Forest
- AdaBoost
- **XGBoost** (Best performer)
- SVR (for experimentation)

### 📏 Evaluation Metrics:
- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)
- R² Score

### ✅ Final Model: **Tuned XGBoost**
- R² (Test): `0.5779`
- RMSE (Test): `86.22`
- MAE (Test): `59.49`

---

## 🔄 Segment-Based Strategy & Error Analysis

📉 **Challenge**: High-priced listings (> $600) caused large prediction errors and overfitting.

### 🎯 Solution:
- Created **Segment A** (≤ $557): Majority of listings with stable patterns
- Created **Segment B** (> $557): Luxury listings with high variance (excluded for now)

### 📊 Segment A (XGBoost Performance):
- R² Score: `0.5779`
- RMSE: `86.22`
- MAE: `59.49`

📌 Future work: Expand model coverage to Segment B with advanced strategies

---

## 📊 Power BI Dashboard Overview

🎯 Goal: Communicate model insights to stakeholders in a business-friendly format.

### 🔹 1. **Price Behavior Insights**
- Premium pricing by room type
- Top-earning property types
- Neighborhood-level pricing heatmap
- Superhost pricing patterns
- Availability-based scarcity pricing
- Bedrooms vs. Price, Guests vs. Price saturation zones

### 🔹 2. **Prediction Accuracy & Error Analysis**
- Actual vs. predicted prices
- Error distribution and bins
- Error by room/property type
- Map of average prediction error

📁 Power BI File: `outputs/AirBnB.pbix`  
🖼️ Screenshots: `images/Power BI Viz/`

---

## ✅ Final Recommendations

📌 Focus on **properties under $600** – high accuracy and strong predictions  
📌 Optimize based on **room type, location, superhost status, availability**  
📌 **Niche property types** (e.g., boats, cabins) require separate models  
📌 Use **Power BI dashboard** to explore underpriced listings or flag anomalies  
📌 Leverage **scarcity-based pricing** for listings with few available dates  

---

## 🔮 Future Enhancements

- Add time-series components to model seasonal trends  
- Expand segment-based modeling to **luxury listings (Segment B)**  
- Deploy as an **API or mobile dashboard** for Airbnb hosts  
- Incorporate SHAP or LIME for explainable ML insights

---

## 👋 About the Author

I’m passionate about using **data science to solve real business problems**. This project is part of my portfolio demonstrating **end-to-end expertise in analytics, modeling, and business communication**.

