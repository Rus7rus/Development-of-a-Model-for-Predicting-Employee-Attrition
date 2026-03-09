# Predicting Employee Turnover: Development of a Risk Assessment Model and Analysis of Key Attrition Factors
[![NBViewer](https://img.shields.io/badge/render-nbviewer-orange.svg)](https://nbviewer.org/github/Rus7rus/Development-of-a-Model-for-Predicting-Employee-Attrition/blob/main/Capstone_Project_Salifort_Motors.ipynb)

## Project Overview
This Capstone Project focuses on predicting employee attrition at **Salifort Motors**. By analyzing high-dimensional HR data, I developed a machine learning solution to identify key turnover drivers and provide actionable insights for talent retention.

### Dataset
The data used in this project is the **[HR Analytics Case Study](https://www.kaggle.com/datasets/mfaisalqureshi/hr-analytics-and-job-prediction?select=HR_comma_sep.csv)** (HR_comma_sep.csv). It contains 14,999 rows and 10 attributes representing employee satisfaction, performance, workload, and tenure.



## Technical Highlights
* **Data Cleaning:** Handled missing values and removed **3,000+ duplicates** to ensure data integrity.
* **Feature Engineering:** * Performed **Discretization (Binning)** on continuous variables like `satisfaction_level` and `average_monthly_hours` to capture non-linear relationships.
    * Implemented `OneHotEncoder(drop='first')` to eliminate multicollinearity (**Dummy Variable Trap**).
* **Robust Validation:** * Executed a **Train/Validation/Test split (70/15/15)**.
    * Applied **Stratification** (`stratify=y`) to maintain the 16.6% churn rate across all datasets.
* **Modeling:** Evaluated Logistic Regression, Random Forest, and **XGBoost** to find the optimal balance between precision and recall.

## Key Insights

It was found that employees resign according to three main scenarios:

- in departments with low requirements — dismissal at the initiative of management due to non-compliance with the company's performance requirements;

- experienced specialists — due to the lack of career growth opportunities.

- experienced specialists — due to excessive workload.



## How to View the Project
Since GitHub often fails to render interactive notebooks and complex HTML (like Confusion Matrices), please use the link below for the best experience:

 **[View Full Project on NBViewer](https://nbviewer.org/github/Rus7rus/Development-of-a-Model-for-Predicting-Employee-Attrition/blob/main/Capstone_Project_Salifort_Motors.ipynb)**

---
*Developed as the final Capstone Project for the Google Advanced Data Analytics Professional Certificate.*
