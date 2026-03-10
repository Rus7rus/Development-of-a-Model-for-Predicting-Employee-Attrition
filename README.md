# Predicting Employee Turnover: Development of a Risk Assessment Model and Analysis of Key Attrition Factors

## Project Overview
This Capstone Project focuses on predicting employee attrition at **Salifort Motors**. By analyzing high-dimensional HR data, I developed a machine learning solution to identify key turnover drivers and provide actionable insights for talent retention.

### Dataset
The data used in this project is the **[HR capstone dataset.csv](https://www.kaggle.com/datasets/ruskolo/hr-capstone-dataset-salifort-motors?select=HR_capstone_dataset.csv)** (HR_capstone_dataset.csv). It contains 14,999 rows and 10 attributes representing employee satisfaction, performance, workload, and tenure.

## Technical Highlights
- **Data Cleaning:** Handled missing values and removed **3,000+ duplicates** to ensure data integrity.
- **Feature Engineering:** * Performed **Discretization (Binning)** on continuous variables like `satisfaction_level` and `average_monthly_hours` to capture non-linear relationships.
    * Implemented `OneHotEncoder(drop='first')` to eliminate multicollinearity (**Dummy Variable Trap**).
- **Robust Validation:** * Executed a **Train/Validation/Test split (70/15/15)**.
    * Applied **Stratification** (`stratify=y`) to maintain the 16.6% churn rate across all datasets.
- **Modeling:** Evaluated Logistic Regression, Random Forest, and **XGBoost** to find the optimal balance between precision and recall.

## Evaluation of model results
### Confusion matrix
<img width="515" height="455" alt="dataConfusion Matrix" src="https://github.com/user-attachments/assets/153de0a7-b967-4130-9e81-a408aaefd403" />


The results showed the model's high effectiveness. Among all employees whom the model predicts will be laid off, 89% are actually laid off, meaning that 11% of predictions are false positives.

Among all employees who are actually laid off, the model correctly identifies 90% of cases.

The model demonstrates high prediction quality for a rare class: F1 = 0.90, which indicates a balance between the ability to identify dismissals and minimize false positives.

In addition, the model has high discriminatory power — it effectively distinguishes between employees who are prone to resignation and those who are highly likely to remain with the company.


## Key Insights

It was found that employees resign according to three main scenarios:

- in departments with low requirements — dismissal at the initiative of management due to non-compliance with the company's performance requirements;

- experienced specialists — due to the lack of career growth opportunities.

- experienced specialists — due to excessive workload.

<img width="689" height="624" alt="dataRelationship plot between variables average_monthly_hours and last_evaluation" src="https://github.com/user-attachments/assets/6183d0c6-6336-46b3-ba35-bd9f9d042ad0" />

## Recommendations

To mitigate turnover across different employee segments (Clusters 1, 2, and 3), the following data-driven strategies are proposed:

**For High-Skilled Specialists (Clusters 2 & 3)**
- Workload Optimization: Implement a structured project distribution strategy. Establish a standard workload of 3 to 5 projects per employee to prevent both burnout and underutilization.

- Hours Regulation: Standardize monthly working hours within the range of 180–260 hours. This ensures productivity while maintaining employee well-being.

- Defined Career Tracks: Develop transparent promotion criteria that explicitly account for both performance efficiency and tenure, providing a clear growth map for senior staff.

**For Entry-Level/Lower-Skilled Staff (Cluster 1)**
- Refined Recruitment & Incentives: Tighten hiring requirements to ensure better person-job fit, while simultaneously introducing a financial incentive system (bonuses and performance rewards) to boost initial engagement.

- Department-Specific Retention: For high-attrition departments (Sales, Technical, Support), implement strategies to encourage a stable working threshold of at least 180 hours per month.

- HR Capacity Building: Conduct a comprehensive re-evaluation of the HR department. Based on the results, provide targeted training to improve their qualification levels in talent management and organizational support.

  

## How to View the Project
Since GitHub often fails to render interactive notebooks and complex HTML (like Confusion Matrices), please use the link below for the best experience:

 **[View Full Project on NBViewer](https://nbviewer.org/github/Rus7rus/Development-of-a-Model-for-Predicting-Employee-Attrition/blob/main/Capstone_Project_Salifort_Motors.ipynb)**

---
*Developed as the final Capstone Project for the Google Advanced Data Analytics Professional Certificate.*
