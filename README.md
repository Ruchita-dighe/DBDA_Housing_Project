# 🏡 Data-Driven Residential Property Price Analysis and Modeling

## 📌 Project Overview
This project focuses on the development of an end-to-end machine learning pipeline designed to predict residential property prices with high precision. By utilizing real-time data acquired through web scraping and robust machine learning models, this system provides accurate property valuations to assist homebuyers and real estate investors in financial planning and market analysis.


## 🎯 Objectives
- Develop a high-precision regression model to estimate house prices based on features like living area, bedrooms, bathrooms, and location (Zipcode, City, State).
- Automate data acquisition via web scraping APIs to reflect real-world market conditions.
- Implement comprehensive Exploratory Data Analysis (EDA) and data preprocessing pipelines.
- Deploy an accessible web interface using **Streamlit** hosted on **Amazon EC2**.
- Use **MLflow** for robust experiment tracking and model management.

## 🛠️ Technology Stack
- **Data Acquisition**: Zillow Web Scraping APIs (Scrapeak)
- **Data Processing & EDA**: Python (Pandas, NumPy), EDA on Zillow dataset, **PySpark** (for large-scale data processing)
- **Machine Learning**: Scikit-Learn, XGBoost, CatBoost, LightGBM, PySpark MLlib
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
- **Random Forest**: Ensemble learning technique to reduce variance and capture non-linear relationships. **(Achieved ~99% R² score on 1-2 Lakh dataset)**.
- **Gradient Boosting**: Sequential ensemble technique focusing on fixing errors of prior trees.
- **XGBoost**: Extreme Gradient Boosting for high-performance and high-accuracy predictions.
- **CatBoost**: Specially engineered to natively handle categorical variables using Symmetric Trees.
- **LightGBM**: Fast, memory-efficient gradient boosting framework that grows trees leaf-wise.

### 3. Big Data Processing with PySpark
To test the pipeline's scalability, the model was trained on a significantly larger dataset of **~10 Lakh (1 million) records**:
- **Implementation**: **PySpark** was utilized for efficient, distributed data handling and model training.
- **Results**: Using **Gradient Boosting** within the PySpark environment, the model successfully achieved an **~89% R² score**, demonstrating robust performance and scalability on massive data volumes.

### 4. Evaluation & Tracking
Performance was rigorously evaluated using MAE, MSE, RMSE, and R² Score. **MLflow** was utilized to log model versions, parameters, and metrics, ensuring reproducibility and streamlined comparison of experiments.

### 5. Visualization & Deployment
- **Tableau Dashboards**: Created interactive business intelligence dashboards to visualize KPIs and market insights.
  - **1) Market Analysis**: Focuses on feature-price relationships. *KPIs: Average Living Area (2,245) & Average Price ($823K).* Includes Living Area vs Price charts and Avg Price by Beds/State.
  - **2) Property Characteristics**: Features geospatial analysis with Map Charts. *KPIs: Average Living Area (2,245), Average Price ($823K), Price per SqFt ($366) & Total Property Count (180,000).* Includes Top 10 Cities by Avg Price and Price Distributions.
- **Web App**: Built a user-friendly frontend using **Streamlit**, allowing users to input property features and receive instant price predictions.
- **Cloud Hosting**: The full pipeline and application are deployed on **Amazon EC2**.

## 📂 Project Structure
```text
📦 DBDA_Housing_Project
├── 📂 Data Acquisition
│   ├── 📄 WebScrapping_zillow.ipynb             # Scraping real estate data via APIs
│   └── 📄 synthetic_datagenerator.ipynb         # Generating synthetic data
├── 📂 Data Preprocessing & EDA
│   ├── 📄 Data_Cleaning.ipynb                   # Data cleaning and imputation
│   ├── 📄 Unclean_combined_dataset.csv          # Raw dataset
│   ├── 📄 clean_house_price_dataset.csv         # Intermediate cleaned dataset
│   └── 📄 clean_houseprice_data_1.csv           # Final cleaned dataset (1-2 Lakh records)
├── 📂 Visualization
│   ├── 📄 Data_Visualization.ipynb              # EDA and chart generation
│   └── 📄 House_Price_Prediction_analysis.twbx  # Tableau Dashboard
├── 📂 Modeling
│   ├── 📄 Model_Training.ipynb                  # Standard model training (Random Forest, etc.)
│   ├── 📄 ModelTrainingUsingPyspark.ipynb       # Distributed training with PySpark
│   ├── 📄 House_price_Model_Train_Log_MLFlow.ipynb # MLflow logging
│   └── 📄 pyspark_dataset.csv                   # Large dataset for PySpark (~10 Lakh records)
├── 📂 Deployment
│   ├── 📄 House_Price_Model_Load_&_Deploy.ipynb # Preparing model for deployment
│   ├── 📂 HousePricePrediction/                 # Streamlit Web App
│   │   ├── 📄 homeapp.py                        # Main Streamlit app
│   │   ├── 📂 model/                            # Saved trained models
│   │   └── 📂 pages/                            # App pages (tableau1.py, tableau2.py)
│   ├── 📂 Deployment/                           # Web app UI Screenshots
│   └── 📄 gradio_output.png                     # Web app output sample
├── 📄 Project_FlowChart.png                     # Complete pipeline architecture
├── 📄 Project_Report_House_Price.docx           # Detailed project report
└── 📄 README.md                                 # Project documentation
```

## 💡 Key Insights
- **Model Efficacy**: Random Forest achieved an outstanding **~99% R²** on the standard 1-2 lakh dataset, making it the most reliable model for medium-sized data.
- **Big Data Scalability**: The pipeline proved highly scalable, with Gradient Boosting via PySpark maintaining an **~89% R² score** even when the dataset size was increased 10x to 1 million records.
- **Feature Importance**: Living Area is the most significant predictor of price, with clear positive correlations highlighted in the Tableau dashboards.
- **Geospatial Trends**: Geospatial mapping reveals high concentrations of premium properties in specific coastal and metropolitan regions, with significant variances in Price per SqFt across different states.

## 🏁 Conclusion
This project successfully demonstrated a complete end-to-end Machine Learning lifecycle for real estate valuation. By automating data ingestion via web scraping, rigorously testing various regression algorithms, and successfully scaling the solution with PySpark for Big Data processing, the pipeline provides robust, real-time pricing estimates. Furthermore, the integration of Tableau dashboards and a Streamlit web app ensures that both technical and non-technical stakeholders (investors, homebuyers) can interactively explore the data and derive actionable insights.

---
*This repository contains the code and resources for the PG-Diploma in Big Data Analytics project at C-DAC.*
