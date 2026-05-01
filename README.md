# 🏡 Data-Driven Residential Property Price Analysis and Modeling

## 📌 Project Overview
This project focuses on the development of an end-to-end machine learning pipeline designed to predict residential property prices with high precision. By utilizing real-time data acquired through web scraping and robust machine learning models, this system provides accurate property valuations to assist homebuyers and real estate investors in financial planning and market analysis.

## 👥 Team Members
- **Ruchita Dighe**
- **Aishwarya Mahajan**
- **Aditya Patil**
- **Ei Han**

*Guided By: Prakash Sinha*  
*Institution: C-DAC, ACTS (Pune)*

## 🎯 Objectives
- Develop a high-precision regression model to estimate house prices based on features like living area, bedrooms, bathrooms, and location (Zipcode, City, State).
- Automate data acquisition via web scraping APIs to reflect real-world market conditions.
- Implement comprehensive Exploratory Data Analysis (EDA) and data preprocessing pipelines.
- Deploy an accessible web interface using **Streamlit** hosted on **Amazon EC2**.
- Use **MLflow** for robust experiment tracking and model management.

## 🛠️ Technology Stack
- **Data Acquisition**: Zillow Web Scraping APIs
- **Data Processing & EDA**: Python (Pandas, NumPy)
- **Machine Learning**: Scikit-Learn, XGBoost, CatBoost, LightGBM
- **Experiment Tracking**: MLflow
- **Data Visualization**: Tableau, Matplotlib, Seaborn
- **Deployment**: Streamlit, Amazon EC2

## 🚀 Methodology

### 1. Data Acquisition and Preprocessing
- **Data Collection**: Gathered raw real estate data programmatically from Zillow via APIs.
- **Exploratory Data Analysis (EDA)**: Analyzed statistical properties and handled missing values using Mean/Mode Imputation.
- **Feature Engineering**: Derived new variables such as calculating "Living Area" from "Lot Area" and encoded geographical data to capture market demand.

### 2. Modeling
Categorical variables were one-hot encoded and numerical features scaled using Standard Scaler. The data was split 80:20 for training and testing. 

The following regression models were trained and evaluated:
- **Linear Regression**: Baseline model for general trends.
- **Elastic Net**: Regularized linear model to handle multicollinearity using Lasso (L1) and Ridge (L2) penalties.
- **Decision Tree**: Non-parametric model acting as a flowchart of rules.
- **Random Forest**: Ensemble learning technique to reduce variance and capture non-linear relationships.
- **Gradient Boosting**: Sequential ensemble technique focusing on fixing errors of prior trees.
- **XGBoost**: Extreme Gradient Boosting for high-performance and high-accuracy predictions.
- **CatBoost**: Specially engineered to natively handle categorical variables using Symmetric Trees.
- **LightGBM**: Fast, memory-efficient gradient boosting framework that grows trees leaf-wise.

### 3. Evaluation & Tracking
Performance was rigorously evaluated using MAE, MSE, RMSE, and R² Score. **MLflow** was utilized to log model versions, parameters, and metrics, ensuring reproducibility and streamlined comparison of experiments.

### 4. Visualization & Deployment
- **Dashboards**: Used Tableau, Matplotlib, and Seaborn for post-prediction analysis and visual interpretation of market trends.
- **Web App**: Built a user-friendly frontend using **Streamlit**, allowing users to input property features and receive instant price predictions.
- **Cloud Hosting**: The full pipeline and application are deployed on **Amazon EC2**.

---
*This repository contains the code and resources for the PG-Diploma in Big Data Analytics project at C-DAC.*
