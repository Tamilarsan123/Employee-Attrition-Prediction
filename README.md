# Employee Attrition Prediction

![Python](https://img.shields.io/badge/Python-3.10+-blue)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-ML-orange)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

A machine learning project that predicts whether an employee is likely to leave an organization, and identifies the key factors behind attrition so HR teams can take early retention action.

---

## Table of Contents
1. [Overview](#overview)
2. [Business Problem](#business-problem)
3. [Dataset](#dataset)
4. [Project Workflow](#project-workflow)
5. [Exploratory Data Analysis](#exploratory-data-analysis)
6. [Data Preprocessing](#data-preprocessing)
7. [Model Building](#model-building)
8. [Results](#results)
9. [Key Insights](#key-insights)
10. [Tech Stack](#tech-stack)
11. [Project Structure](#project-structure)
12. [Installation and Usage](#installation-and-usage)
13. [Future Improvements](#future-improvements)
14. [Author](#author)

---

## Overview

Employee attrition increases hiring and training costs, disrupts teams, and leads to loss of skilled talent. This project builds a classification model on HR data to predict whether an employee will leave (`Attrition = Yes`) or stay (`Attrition = No`).

**Objectives**
- Explore HR data to understand why employees leave
- Build and compare multiple classification models
- Select the best model using metrics suited to imbalanced data
- Provide actionable insights for HR decision-making

---

## Business Problem

Replacing an employee is expensive and time-consuming. If HR can predict who is at risk of leaving, it can intervene early through salary review, workload changes, career growth plans, or engagement programs. This project turns that need into a data-driven prediction model.

---

## Dataset

| Item | Details |
|------|---------|
| Source | [Dataset name, e.g. IBM HR Analytics Employee Attrition (Kaggle)] |
| Records | [e.g. 1,470] |
| Features | [e.g. 35] |
| Target | `Attrition` (Yes / No) |
| Class balance | [e.g. ~16% Yes, ~84% No] |

**Feature groups**
- **Demographics:** Age, Gender, Marital Status, Education
- **Job details:** Department, Job Role, Job Level, Business Travel
- **Compensation:** Monthly Income, Percent Salary Hike, Stock Option Level
- **Satisfaction:** Job Satisfaction, Environment Satisfaction, Work-Life Balance, Relationship Satisfaction
- **Experience:** Total Working Years, Years at Company, Years Since Last Promotion, Years with Current Manager
- **Work pattern:** OverTime, Distance From Home, Training Times Last Year

---

## Project Workflow

```
Data Collection → Data Cleaning → EDA → Preprocessing → Model Training → Evaluation → Insights
```

---

## Exploratory Data Analysis

EDA was performed to understand patterns between employee attributes and attrition.

- Attrition distribution (class imbalance check)
- Attrition by department, job role, and gender
- Impact of overtime on attrition
- Relationship between monthly income and attrition
- Effect of age, tenure, and years since last promotion
- Correlation heatmap of numeric features
- Outlier detection using box plots

> Add screenshots of your key charts here, for example:
> `![Attrition Distribution](images/attrition_distribution.png)`

---

## Data Preprocessing

- Removed non-informative columns (e.g. `EmployeeCount`, `StandardHours`, `Over18`, `EmployeeNumber`)
- Checked for and handled missing values and duplicates
- Encoded the target variable (Yes = 1, No = 0)
- Encoded categorical features using [Label Encoding / One-Hot Encoding]
- Scaled numeric features using [StandardScaler / MinMaxScaler]
- Handled class imbalance using [SMOTE / class weights / stratified sampling]
- Split data into training and testing sets ([80:20], stratified)

---

## Model Building

The following models were trained and compared:

| Model | Purpose |
|-------|---------|
| Logistic Regression | Baseline, interpretable |
| Decision Tree | Rule-based, easy to explain |
| Random Forest | Ensemble, handles non-linear patterns |
| [XGBoost / Gradient Boosting] | High-performance boosting model |

Hyperparameter tuning was done using [GridSearchCV / RandomizedSearchCV] with cross-validation.

---

## Results

Because attrition data is imbalanced, accuracy alone is misleading. Recall, F1-score, and ROC-AUC were used to judge models.

| Model | Accuracy | Precision | Recall | F1-Score | ROC-AUC |
|-------|----------|-----------|--------|----------|---------|
| Logistic Regression | [ ]% | [ ]% | [ ]% | [ ]% | [ ] |
| Decision Tree | [ ]% | [ ]% | [ ]% | [ ]% | [ ] |
| Random Forest | [ ]% | [ ]% | [ ]% | [ ]% | [ ] |
| [XGBoost] | [ ]% | [ ]% | [ ]% | [ ]% | [ ] |

**Best model:** [model name], selected for its [recall / F1 / ROC-AUC] performance.

---

## Key Insights

- Employees working **overtime** show a noticeably higher attrition rate
- **Lower monthly income** and **fewer years at the company** are linked to higher attrition
- Low **job satisfaction** and poor **work-life balance** increase leaving risk
- Long periods **without promotion** contribute to attrition
- [Add your own findings from feature importance]

**Recommendations for HR**
- Review workload and overtime policies
- Revisit pay for high-risk roles
- Create clear promotion and growth paths
- Run regular satisfaction surveys and act on feedback

---

## Tech Stack

| Category | Tools |
|----------|-------|
| Language | Python |
| Data handling | Pandas, NumPy |
| Visualization | Matplotlib, Seaborn |
| Machine learning | Scikit-Learn, [XGBoost, imbalanced-learn] |
| Environment | Jupyter Notebook |
| Version control | Git, GitHub |

---

## Project Structure

```
Employee-Attrition-Prediction/
│
├── data/
│   └── employee_attrition.csv
├── notebooks/
│   └── attrition_prediction.ipynb
├── models/
│   └── best_model.pkl
├── images/
│   └── (charts and plots)
├── requirements.txt
└── README.md
```

> Update this tree to match your actual files.

---

## Installation and Usage

**1. Clone the repository**
```bash
git clone https://github.com/Tamilarsan123/Employee-Attrition-Prediction.git
cd Employee-Attrition-Prediction
```

**2. Create a virtual environment (optional)**
```bash
python -m venv venv
source venv/bin/activate      # Windows: venv\Scripts\activate
```

**3. Install dependencies**
```bash
pip install -r requirements.txt
```

**4. Run the notebook**
```bash
jupyter notebook
```
Open `attrition_prediction.ipynb` and run all cells.

**5. Make a prediction (example)**
```python
import joblib
import pandas as pd

model = joblib.load("models/best_model.pkl")
sample = pd.DataFrame([{...}])   # employee features
print(model.predict(sample))     # 1 = likely to leave, 0 = likely to stay
```

---

## Future Improvements

- Deploy as a web app using Flask or Streamlit
- Add model explainability with SHAP or LIME
- Try advanced models and ensemble stacking
- Build a Power BI dashboard for HR attrition tracking
- Containerize with Docker and track experiments with MLflow

---

## Author

**Tamilarasan K**
B.Tech Artificial Intelligence & Data Science

- GitHub: [Tamilarsan123](https://github.com/Tamilarsan123)
- LinkedIn: [tamilarasan-k](https://linkedin.com/in/tamilarasan-k-03a27834b)

If you found this project useful, please give it a ⭐
