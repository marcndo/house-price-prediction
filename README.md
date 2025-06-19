# 🏡 House Price Prediction

## 📌 Overview

This project demonstrates how to leverage machine learning techniques—specifically regression models—to solve real-world problems in the real estate domain. The goal is to help real estate professionals accurately predict house prices based on key features of properties using historical housing data.

## 📊 Dataset

- **Source**: [Melbourne Housing Dataset – Kaggle](https://www.kaggle.com/datasets)  
- **Size**: 13,579 rows × 21 columns  
- **Data Types**: Mix of integers, floats, and categorical (object) variables  
- **Target Variable**: `Price`

## 🧪 Exploratory Data Analysis (EDA)

### Key Insights:

- `SalePrice` shows a wide range → strong variability in house values.
- `LandSize` has large outliers → potential skew.
- Some features like `Distance`, `Bedroom2`, and `Bathroom` have values of 0, possibly indicating missing data.
- High standard deviations in `LandSize`, `BuildingArea`, and `PropertyCount` suggest wide spreads.
- Missing values were found in:
  - `Car`, `BuildingArea`, `YearBuilt`, `CouncilArea`
- Strong correlation (0.8) between `BuildingArea` and `YearBuilt` → missing patterns are related.
- Heatmaps revealed:
  - `Bedroom2`, `Bathroom` moderately correlate with `Price` (positive)
  - `Distance` and `YearBuilt` weakly negatively correlate
  - `YearBuilt` and `Age`: perfect negative correlation

### Handling Missing Data:

- Created binary indicators for missing values
- Imputed original values with **median** values (to prevent bias)
- Avoided dropping rows to preserve dataset size (~50% would be lost)

### Categorical Feature Insights:

- **Count Plots**: Showed frequency of `Type`, `Method`, `Regionname`, etc.
- **Box Plots**: Compared `Price` distributions across categories
- These helped identify location and property type as strong price predictors

## 🧠 Model Development

### Algorithms Tried:

- ✅ **Linear Regression**
- ✅ **Ridge Regression**
- ✅ **Lasso Regression**
- ✅ **Support Vector Regression (SVR)**
- ✅ **Random Forest Regressor**
- ✅ **Gradient Boosting Regressor**

### Model Tuning:

- Used `GridSearchCV` to optimize hyperparameters
- Compared models using RMSE
- Selected best-performing model based on cross-validation

## 🚀 Deployment

- **Live Demo**: [Launch on Hugging Face Spaces 🚀](https://huggingface.co/spaces/marcndo/ndowahmarcel-house-price-predictor)
- **Framework**: Gradio + Streamlit backend
- Users can input new house features and get predicted prices instantly

## 🛠️ Tech Stack

- Python, Jupyter Notebook
- `pandas`, `numpy`, `seaborn`, `matplotlib`, `missingno`
- `scikit-learn`, `joblib`, `pickle`
- Gradio, Hugging Face Spaces

## 📚 Key Learnings

- End-to-end project lifecycle from data cleaning to deployment
- Model evaluation & optimization using `GridSearchCV`
- Learned how feature engineering and EDA impact predictive performance
- Deployment with Hugging Face & Gradio for real-world accessibility

