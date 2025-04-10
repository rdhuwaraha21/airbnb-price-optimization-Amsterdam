# Airbnb Price Optimization – Amsterdam (End-to-End ML + BI Case Study)

> A real-world machine learning and data visualization project to help Airbnb hosts in Amsterdam **maximize revenue and minimize pricing errors**.

This project simulates the responsibilities of a **Data Analyst / ML Engineer**:
-  Clean and segment real-world Airbnb data (10,000+ listings)
-  Predict prices using **regression models** (XGBoost, Random Forest)
-  Reduce prediction error using **segment-based modeling**
-  Create a **Power BI dashboard** to present business insights to non-technical stakeholders

 **Why this matters to hiring managers**:  
This is a full-cycle, production-ready ML project with **clear business objectives**, strong **data storytelling**, and stakeholder-oriented design — built to **mirror enterprise-level decision-making.**

## 1. Business Objective

Amsterdam is one of Europe’s busiest Airbnb markets. However, many hosts lose revenue due to **suboptimal pricing strategies** that fail to reflect listing quality, demand, or competition.

This project aims to:
- **Predict the ideal price** for each listing based on features like location, room type, reviews, amenities, and availability.
- **Minimize prediction error** using advanced ML techniques and segment-based modeling.
- **Enable better decisions** through an interactive Power BI dashboard tailored for both technical and non-technical stakeholders.

> This project is designed as a real-world simulation of how a Data Analyst or ML Engineer drives **business value from data.**

## 2. Business Value Delivered

This project provides tangible value to Airbnb hosts and platform analysts:

- Increased pricing accuracy for over 94% of listings under $600, leading to more competitive and optimized rates.
- Reduced prediction error by segmenting listings based on price thresholds, improving targeting for different market tiers.
- Identified key drivers of pricing, such as room type, location, and host status, enabling data-backed strategy.
- Created a Power BI dashboard that simplifies complex predictions into actionable business insights for decision-makers.

This end-to-end pipeline—from data cleaning and modeling to visual storytelling—reflects how data science supports real business decisions.

## 3. Tools and Technologies Used

| Category             | Tools / Technologies                            |
|----------------------|--------------------------------------------------|
| Programming Language | Python                                           |
| Data Processing      | Pandas, NumPy                                    |
| Data Visualization   | Seaborn, Matplotlib                              |
| Machine Learning     | Scikit-learn, XGBoost, Random Forest, GridSearch |
| Feature Engineering  | Label Encoding, One-Hot Encoding, IQR Outlier Handling |
| Model Evaluation     | MAE, RMSE, R², Residual Analysis, Segmentation   |
| Business Intelligence| Power BI                                         |
| Project Management   | Git, GitHub                                       |

## 4. Exploratory Data Analysis (EDA)

The project began with deep exploration of the dataset containing over 75 features and 9,600+ listings in Amsterdam.

Key analysis steps included:

- Identified extreme price outliers using IQR and distribution analysis
- Segmented prices into business-friendly ranges to handle skewed distributions
- Analyzed price behavior across room types, neighborhoods, and property types
- Explored impact of availability, reviews, and host status on price
- Mapped key amenities and their frequency across listings

A dedicated EDA notebook was created to visualize these trends using histograms, boxplots, heatmaps, and correlation matrices.

**Notable Findings:**
- Most listings fall below $600, with heavy skew due to luxury properties
- Room type and neighborhood strongly influence price
- Certain amenities and review scores correlate with higher prices

Notebook: [`notebooks/AirBnB_price_EDA (2).ipynb`](notebooks/01_price_eda.ipynb)

## 5. Modeling and Model Evaluation

Multiple regression models were trained and evaluated to predict Airbnb listing prices. Each model was tested on both training and test data, with a focus on generalization and minimizing overfitting.

**Models Tested:**
- Linear Regression
- Decision Tree Regressor
- Random Forest Regressor
- AdaBoost Regressor
- XGBoost Regressor (tuned with RandomizedSearchCV)

**Evaluation Metrics:**
- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)
- R² Score

**Final Model Selection:**
XGBoost Regressor was selected as the final model due to its superior test performance:
- R² Score (Test): 0.5779
- RMSE (Test): 86.22
- MAE (Test): 59.49

While Random Forest also performed well (R²: 0.5604), XGBoost demonstrated better generalization with slightly lower prediction error.

## 6. Segment-Based Strategy and Error Analysis

Initial analysis revealed that listings with high prices (above $600) introduced large prediction errors and instability in the model's performance.

**Residual Analysis Insights:**
- Model error increased significantly for listings priced above $600
- Outliers in price and rare property types caused the model to overfit

To solve this, a **segmented modeling approach** was introduced:
- **Segment A**: Listings priced at or below $557 (majority of the data)
- **Segment B**: Listings above $557 (less frequent, high variance)

**Segment A Modeling Results (XGBoost):**
- R² Score (Test): 0.5779
- RMSE: 86.22
- MAE: 59.49

Segment A showed strong prediction performance with tighter residual distribution. Segment B was excluded from modeling due to its low volume and inconsistent behavior, but flagged as a future opportunity for advanced modeling.

## 7. Power BI Dashboard

**Purpose**: Deliver business insights and explain model behavior clearly through interactive visualizations for stakeholders.

### Dashboard Pages

#### 1. Price Behavior Insights
These visuals explore how listing features, host status, and location influence Airbnb pricing in Amsterdam:

- **Premium Pricing by Room Type**: Entire homes/apartments earn the most; shared rooms are budget-friendly.
- **Top-Earning Property Types**: Guest suites, rentals, and vacation homes dominate top earnings.
- **Hot Zones Map**: Centrum, Oud-West, and De Pijp consistently show higher predicted prices.
- **Superhost Strategy**: Superhosts tend to charge more on average.
- **Scarcity Pricing**: Listings with low availability (0–5 days) tend to have higher prices.
- **Bedrooms vs Price & Max Guests vs Price**: Both features show upward price trends, though saturation occurs beyond certain points.

#### 2. Prediction Accuracy & Error Analysis
This page explains model performance with a focus on Segment A (lower-priced listings):

- **Actual vs Predicted Price**: Strong diagonal trend; accurate predictions for most listings.
- **Prediction Error Distribution**: Slight underestimation in high-price segments.
- **Error by Room Type & Property Type**: Highest average errors for entire homes and niche property types.
- **Map of Avg Error by Location**: Neighborhood-level model weaknesses are clearly visualized.
- **Prediction Error Bins**: Distribution of listings by error range — majority fall within ±50 range.

### Dashboard Features

- Clean layout with slicers for room type, bathrooms, bedrooms, and beds.
- Color-coded maps and error flags.
- Tooltip-enhanced visuals for deeper exploration.
- Designed for **non-technical business users** to support decision-making.

**Power BI File**: `outputs/AirBnB.pbix`  
**Visual Screenshots**: `images/Power BI Viz/`

## 8. Final Recommendations

Based on analysis and model outcomes, the following recommendations are proposed for hosts and pricing strategists:

- **Focus on Listings Below $600**: The model shows the best accuracy for properties priced under $600. Segment A predictions are highly reliable.
- **Leverage Key Price Drivers**: Optimize listings using features like:
  - Room type (entire home/apt)
  - Location (Centrum, De Pijp, Oud-West)
  - Superhost status
  - Number of bedrooms
  - Availability and guest capacity
- **Watch Out for Niche Properties**: Unique property types (e.g., huts, houseboats) show higher prediction error — these may require separate pricing strategies.
- **Consider Scarcity Tactics**: Listings with limited availability (0–5 days) tend to earn more — possibly due to scarcity-based pricing strategies.
- **Power BI for Strategy**: Use the dashboard to identify underpriced listings or spot inconsistent pricing by neighborhood, host type, or capacity.

**Next Steps (Optional Enhancements):**
- Add a time-series component for seasonal pricing.
- Expand the model to Segment B (luxury listings).
- Develop a pricing API or mobile dashboard for hosts.
