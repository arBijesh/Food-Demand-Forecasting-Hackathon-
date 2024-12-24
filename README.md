# Food Demand Forecasting Hackathon 🍽️

## Project Overview
This project was created as part of the **Genpact Machine Learning Hackathon**, focusing on forecasting food demand for a meal delivery company operating in multiple cities. The goal is to predict demand for the next 10 weeks to help fulfillment centers optimize raw material procurement and staffing schedules efficiently.

Accurate forecasting is crucial for minimizing waste of perishable raw materials and ensuring adequate staffing for smooth operations.

---

## Table of Contents
1. [Problem Statement](#problem-statement)
2. [Key Challenges](#key-challenges)
3. [Data Description](#data-description)
4. [Key Features](#key-features)
5. [Data Analysis](#data-analysis)
6. [Feature Engineering](#feature-engineering)
7. [Modeling and Evaluation](#modeling-and-evaluation)
8. [Performance](#performance)
9. [Future Enhancements](#future-enhancements)
10. [Contributing](#contributing)
11. [License](#license)

---

## Problem Statement
The client is a **meal delivery company** with fulfillment centers in multiple cities. They need to forecast demand for the next 10 weeks for specific center-meal combinations. This will enable centers to optimize raw material stock levels and manage staffing efficiently.

---

## Key Challenges
1. **Perishable Raw Materials**:
   - Raw materials are replenished weekly, and they are perishable.
   - Overestimating demand leads to waste, while underestimating results in stock shortages.
   
2. **Staffing Efficiency**:
   - Predicting demand allows fulfillment centers to manage staff schedules effectively.

---

## Data Description
The project involves three primary datasets:
- **Train Dataset**: Historical demand data for 145 weeks.
- **Test Dataset**: Data for which predictions are required (Weeks 146–155).
- **Supplementary Datasets**:
  - **Meal Information**: Includes details about meals such as category, sub-category, base price, and discount.
  - **Fulfillment Center Information**: Includes center area, city, and region information.

---

## Key Features
- **Unified Data**:
  - Merged datasets (train, meal, and fulfillment center information) for a comprehensive view.
- **Temporal Features**:
  - Extracted time-based attributes, including week number, seasonal patterns, and yearly trends.
- **Price Insights**:
  - Computed price differences between `base_price` and `checkout_price` to identify discounts, taxes, or additional charges.
- **Marketing Impact**:
  - Assessed the influence of email promotions and homepage features on demand.
- **Geographical Aggregates**:
  - Generated region- and center-specific demand metrics for enhanced predictions.

---

## Data Analysis
### Univariate Analysis
- Examined distributions of key variables such as demand (`num_orders`), price differences, and geographical metrics.
- Identified skewness in demand distribution and applied transformations for normalization.

### Bivariate Analysis
- Analyzed relationships between features like price categories, marketing efforts, and demand.
- Explored geographical impacts (region and center types) on order volumes.

---

## Feature Engineering
- **Aggregations**:
  - Created statistical aggregates (min, mean, median, std, max) for center, region, category, and meal-specific demand.
- **Seasonality**:
  - Incorporated seasonal trends using sine and cosine transformations of the week feature.
- **Categorical Encoding**:
  - Encoded categorical variables such as `meal_category` and `center_type` for use in machine learning models.

---

## Modeling and Evaluation
- Implemented multiple machine learning models, including:
  - **Linear Regression**
  - **Random Forest Regressor**
  - **Gradient Boosting Regressor**
- Applied logarithmic transformation to the target variable to reduce skewness.
- Used K-Fold Cross-Validation to ensure robust model performance.
- Conducted hyperparameter tuning using RandomizedSearchCV and GridSearchCV for optimal results.

---

## Performance
- **Evaluation Metric**:
  - Root Mean Squared Logarithmic Error (RMSLE) was used to measure prediction accuracy.
- **Best Results**:
  - Achieved an RMSLE of `X.XXX` using Gradient Boosting with optimized hyperparameters.

---

## Future Enhancements
1. **Incorporate External Data**:
   - Add external features like weather, holidays, and events for improved predictions.
2. **Deep Learning Models**:
   - Experiment with LSTMs or Transformers for capturing temporal dependencies in demand.
3. **Real-Time Predictions**:
   - Integrate the model into a live data pipeline for dynamic demand forecasting.

---
