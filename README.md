# Customer Churn Prediction & Dashboard Project

![Python](https://img.shields.io/badge/Python-3.10-blue?logo=python)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter)
![Looker Studio](https://img.shields.io/badge/Looker-Studio-4285F4?logo=google)
![RandomForest](https://img.shields.io/badge/Model-RandomForest-success)
![License](https://img.shields.io/badge/License-MIT-green)

This project builds a machine learning model to predict customer churn and visualizes the results in an interactive Looker Studio dashboard. It includes data preparation, feature engineering, model evaluation, and business-friendly segmentation filters to support retention targeting.

---

## Table of Contents

- [Dashboard Preview](#-dashboard-preview)
- [Dataset Overview](#-dataset-overview)
- [Data Preprocessing](#-data-preprocessing)
- [Exploratory Data Analysis](#-exploratory-data-analysis)
- [Predictive Modeling](#-predictive-modeling)
- [Looker Studio Dashboard](#-looker-studio-dashboard)
- [Key Insights](#-key-insights)
- [Technologies Used](#-technologies-used)
- [Project Structure](#-project-structure)
- [Author & License](#-author--license)

---

## Dashboard Preview

![Churn Dashboard](dashboard_screenshot.png)

---

## Dataset Overview

- **Source**: Internal or simulated e-commerce CRM data  
- **Rows**: 5,000+ customer records  
- **Fields**:  
  - Customer ID, tenure, app usage, order activity  
  - Complaint history, product category preferences  
  - Marital status, satisfaction score, and churn status

---

## Data Preprocessing

- Imputed missing values using median strategy  
- One-hot encoded categorical features  
- Engineered custom fields:
  - `RecencySegment`: Very Recent, Recent, Stale, Dormant  
  - `HighValueCustomer`: Based on order frequency and engagement  
  - `Churn_Prediction`: Binary churn output  
  - `Churn_Probability`: Model score for churn risk

---

## Exploratory Data Analysis

Visualized churn patterns using Python:

- Churn rate by recency segment  
- App usage vs. churn  
- Churn by product category  
- Distribution of churn probabilities  

---

## Predictive Modeling

### Final Model: Random Forest Classifier (Tuned with GridSearchCV)

- **ROC AUC**: 0.987  
- **Accuracy**: 0.96  
- **Recall (Churn class)**: 0.79  
- **Precision (Churn class)**: 0.96  
- **F1 Score**: 0.87

### Best Parameters:
```python
{
  'class_weight': 'balanced',
  'max_depth': 20,
  'min_samples_split': 2,
  'n_estimators': 100
}
```

### Confusion Matrix:
```
[[1395   10]
 [  59  225]]
```

---

## Looker Studio Dashboard

> [View Dashboard](https://lookerstudio.google.com/reporting/614f9d9c-b959-4b0b-bd59-bd77cfa33bb1)

### KPIs
- Total Customers  
- Total Predicted Churners  
- High-Value Churners  

### Charts
- Churn Breakdown by Recency Segment  
- Risk Distribution Histogram  

### Interactive Filters
- Recency Segment (Dropdown)  
- High-Value Customer (Dropdown)  
- Churn Status (Dropdown)  
- Churn Probability (Slider)

---

## Key Insights

- Majority of churn risk comes from **Stale** and **Dormant** segments  
- **High-Value churners** are critical to prevent loss of revenue  
- Customers with **Churn Probability > 0.7** are top targets for promos  
- Engagement metrics (app usage, order recency) are strong churn predictors

---

## Technologies Used

- Python (pandas, scikit-learn, matplotlib)
- Jupyter Notebook
- Google Looker Studio
- Git & GitHub

---

## Project Structure

```
customer_churn_project/
├── data/
│   └── E Commerce Dataset.xlsx
├── notebooks/
│   └── churn_modeling.ipynb
├── outputs/
│   └── churn_predictions_scored.csv
├── dashboard/
│   └── looker_studio_link.txt
└── README.md
```

---

## Author & License

**Author**: Matt Baglietto  
matt.baglietto11@gmail.com
[LinkedIn](https://www.linkedin.com/in/matthewbaglietto)
