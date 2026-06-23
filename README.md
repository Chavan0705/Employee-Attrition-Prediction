# Employee Attrition Prediction Project

This project delivers a Machine Learning system to predict employee attrition and provide data-backed strategic recommendations for HR leadership. The system cleans and prepares HR data, handles class imbalance, evaluates multiple classification models, and extracts the primary drivers of voluntary employee exits.

---

# 📋 EXECUTIVE MEMORANDUM
### TO: HR Director  
### FROM: Lead Data Scientist  
### DATE: June 23, 2026  
### SUBJECT: Data-Driven Retention Insights & Business Recommendations  

---

## 1. Executive Summary
Every company loses employees, but losing high-performing talent at critical times damages organizational stability and incurs substantial replacement costs. This analysis examines historical employee data from **1,470 individuals** to predict attrition risk and identify key exit drivers. By deploying a calibrated Machine Learning system (**Logistic Regression, 80.32% AUC, 63.83% Recall**), we isolated the organizational levers that drive employee turnover. Our findings indicate that attrition is highly concentrated in specific job roles, new hire tenure cohorts, and burnout-inducing work structures.

---

## 2. Key Insights & Risk Areas
Based on our exploratory data analysis (EDA) and model coefficients, we have identified the following primary risk areas:
*   **Overall Baseline**: The organization has a baseline attrition rate of **16.12%** (237 employees left, 1,233 stayed).
*   **High-Risk Job Roles**: **Sales Representatives** face a massive voluntary exit rate of **39.76%**, followed by **Laboratory Technicians** at **23.94%** and **Human Resources Staff** at **23.08%**. Conversely, Research Directors (2.50%) and Managers (4.90%) are highly stable.
*   **The Onboarding Gap**: New hires are highly vulnerable. Attrition stands at **29.82%** for employees with 0-2 years of tenure, and spikes to **34.88%** for those with 1 year or less of service.
*   **Overtime and Burnout**: Working **Overtime** is the strongest positive predictor of voluntary resignation (model coefficient: +0.76). Employees who work overtime are statistically twice as likely to exit compared to those who do not.
*   **Financial Disparity**: Compensation plays a major role. Employees who left earned a median monthly salary of **$3,202**, compared to **$5,204** for those who stayed—representing a **38.5% compensation gap**.

---

## 3. Strategic Interventions (Recommendations)
To improve employee retention and mitigate replacement costs, HR should implement the following policy changes:
1.  **Overtime Cap & Burnout Management**: Cap weekly overtime hours for high-risk roles (Laboratory Technicians, Sales Representatives) at a maximum of 5 hours and institute a mandatory recovery policy. Since overtime is a primary exit driver, managing workload and burnout will directly improve retention.
2.  **First-Year Mentorship & Retention Reviews**: Launch a "First-Year Anchor" mentorship program pairing new hires with senior colleagues. Conduct structured "stay-interviews" at the 6-month and 12-month marks. Targeting the onboarding gap is crucial, as employees with under 1 year of tenure exhibit a **34.88% exit rate**.
3.  **Targeted Compensation Audits**: Review salaries for positions earning under the $3,500 monthly threshold, particularly for Sales Representatives and Laboratory Technicians. Adjusting base pay to align with local market medians will neutralize the financial pull of competing external offers.

---

## 4. Analytical Framework & Model Limitations
*   **Model Performance**: The Logistic Regression model achieved the best performance for retention efforts, maximizing **Recall at 63.83%** and **ROC-AUC at 80.32%** on the test set. This allows HR to proactively identify nearly 2/3 of at-risk employees prior to their departure, while minimizing false alarms (Precision: 34.88%).
*   **Limitations for HR Leadership**:
    1.  **Historical Snapshot Bias**: The model is trained on static data and cannot automatically adjust to macroeconomic shifts (e.g., sudden job market changes in 2026).
    2.  **Lack of Qualitative Context**: Important variables like team dynamics, manager relationships, personal circumstances, or cultural fit are not fully captured in the structured numeric features.
    3.  **Actionable Window**: The model indicates probability but not timing; proactive reviews should occur at regular intervals rather than waiting for alerts.

---

## 📊 Machine Learning Model Comparison

The three classification models trained and evaluated on an 80/20 train/test split yielded the following metrics:

| Model | Precision | Recall | F1-Score | ROC-AUC |
| :--- | :---: | :---: | :---: | :---: |
| **Logistic Regression (Best)** | **0.3488** | **0.6383** | **0.4511** | **0.8032** |
| Gradient Boosting | 0.3793 | 0.4681 | 0.4190 | 0.7771 |
| Random Forest | 0.5556 | 0.1064 | 0.1786 | 0.7878 |

*Recall is prioritized to ensure we flag as many at-risk employees as possible, making Logistic Regression the clear choice.*

---

## 📁 Directory Structure & Deliverables

All project deliverables are located in the root directory:

*   **[Employee_Attrition_Prediction.ipynb](file:///c:/Users/adity/OneDrive/Desktop/Employee%20Attrition%20Prediction/Employee_Attrition_Prediction.ipynb)**: Fully executed and annotated Jupyter Notebook containing all 7 tasks.
*   **[HR_Attrition.csv](file:///c:/Users/adity/OneDrive/Desktop/Employee%20Attrition%20Prediction/HR_Attrition.csv)**: Copy of the dataset.
*   **[README.md](file:///c:/Users/adity/OneDrive/Desktop/Employee%20Attrition%20Prediction/README.md)**: Executive Summary and model documentation (this file).
*   **[charts/](file:///c:/Users/adity/OneDrive/Desktop/Employee%20Attrition%20Prediction/charts/)**: High-resolution visualization plots:
    *   `attrition_by_dept_role.png` (Attrition rate by role & department)
    *   `income_boxplot.png` (Salary distribution for stayed vs left)
    *   `confusion_matrix.png` (Best model's confusion matrix heatmap)
    *   `feature_importances.png` (Logistic Regression coefficients)
    *   `roc_curve.png` (ROC curves for model comparison)
