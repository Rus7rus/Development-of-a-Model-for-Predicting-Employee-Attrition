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
<img width="257" height="225" alt="dataConfusion Matrix" src="https://github.com/user-attachments/assets/f0d87213-0d70-4035-b318-8c9862b7cccc" />




The results showed the model's high effectiveness. Among all employees whom the model predicts will be laid off, 89% are actually laid off, meaning that 11% of predictions are false positives.

Among all employees who are actually laid off, the model correctly identifies 90% of cases.

The model demonstrates high prediction quality for a rare class: F1 = 0.90, which indicates a balance between the ability to identify dismissals and minimize false positives.

In addition, the model has high discriminatory power — it effectively distinguishes between employees who are prone to resignation and those who are highly likely to remain with the company.


## Key Insights

It was found that employees resign according to three main scenarios:

- in departments with low requirements — dismissal at the initiative of management due to non-compliance with the company's performance requirements;

- experienced specialists — due to the lack of career growth opportunities.

- experienced specialists — due to excessive workload.

<img width="533" height="425" alt="dataRelationship plot between variables average_monthly_hours and last_evaluation" src="https://github.com/user-attachments/assets/202d4224-9455-4b2f-9563-05f9e0aab82e" />


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

<img width="533" height="425" alt="dataRelationship between last_evaluation and satisfaction_level" src="https://github.com/user-attachments/assets/2c5d8a4e-ba6a-4825-a87c-817574f5b172" />
  
## Remarks

**Methodological Conclusions and Recommendations**

Since this is an educational project, some steps that are important in real-world practice were omitted. To transition to real-world business tasks, two key aspects must be taken into account.

**The Need for Scaling in Logistic Regression**

Data scaling (*standardization or normalization*) was not performed as part of this work. For logistic regression, this is a crucial step in data preparation. Without bringing the features to a common scale, the model may assign greater weight to variables with large numerical values (*e.g., number of hours worked*) compared to variables with small values (*e.g., satisfaction level*). This can distort the assessment of feature importance and negatively impact the quality of model training.

**Using Two Separate Models**

A practical approach is to build two different models depending on the objective.

**Prediction Model**
The main goal of such a model is to achieve the highest possible predictive accuracy. In this case, it is undesirable to use variable binning, as it makes the data discrete and leads to a loss of information. To achieve high accuracy, the model must use the most detailed information possible.

**Model for interpretation**
The goal of this model is to explain the causes and interpret the influencing factors. In this case, binning can be useful because it allows for the formation of simple and understandable rules (e.g., if work experience exceeds 5 years, the risk of dismissal increases). This facilitates the interpretation of results for practical use, although the overall accuracy of such a model will typically be lower.

Translated with DeepL.com (free version)

**Interpretation Issues**

Due to the fact that the analysis was conducted under conditions where it was impossible to make clarifications or obtain answers to questions that arose during the study from stakeholders, the conclusions are presumptive and do not reflect the actual situation within the company. 

After establishing correlations between influence factors and the characteristics of the terminated employee groups, it is almost impossible to determine which is the cause and which is the effect.

For instance, in the Cluster 1 turnover group, a hypothesis was adopted that terminations were initiated by company management due to a failure to meet requirements, such as low performance ratings and underutilization. However, another scenario is possible — for example, staff reductions due to the phasing out of short-term programs or the emergence of force majeure circumstances. In such a case, the characteristic features of those dismissed would have indirect rather than direct causes.



## How to View the Project
Since GitHub often fails to render interactive notebooks and complex HTML (like Confusion Matrices), please use the link below for the best experience:

 **[View Full Project on NBViewer](https://nbviewer.org/github/Rus7rus/Development-of-a-Model-for-Predicting-Employee-Attrition/blob/main/Capstone_Project_Salifort_Motors.ipynb)**

---
*Developed as the final Capstone Project for the Google Advanced Data Analytics Professional Certificate.*
