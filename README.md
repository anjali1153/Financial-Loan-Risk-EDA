Bank Loan Data — Exploratory Data Analysis (EDA)

Project: Bank Loan Data EDA

- This repository contains an exploratory data analysis (EDA) of a bank loan dataset using a Jupyter Notebook (Bank_loan_data_EDA.ipynb). The goal is to understand factors that influence loan approvals, clean and preprocess the data, visualize distributions and relationships, and highlight insights useful for downstream modeling.

# Table of contents

1. Project Overview

2. Files in this repo

3. How to run

4. Notebook structure & steps performed

5. Key analyses and visualizations

6. Dependencies

7. Data dictionary (example)

8. Recommendations & next steps

9. Author / Contact


1.  Project overview

This EDA aims to:

Inspect the raw loan dataset for missing values, inconsistent formatting, and outliers.

Clean and preprocess fields (e.g., convert categorical variables, impute missing values).

Plot distributions (age, income, loan amount), correlation heatmap, and categorical counts (loan status by gender, education, property area).

Derive features that might be predictive for loan default/approval models.

This notebook is intended for data analysts, students preparing assignments, or engineers starting a modeling pipeline.

2. Files in this repo

Bank_loan_data_EDA.ipynb — main Jupyter notebook with step-by-step EDA and plots.

README.md — this file (rendered from GitHub or local viewer).

data/ (optional) — place your dataset CSV files here (e.g., loan_data.csv).

If you add more files (scripts, models), update this README accordingly.

3. How to run

Clone the repository:

git clone <your-repo-url>
cd <repo-folder>

Create a python environment (recommended) and install dependencies:

python -m venv venv
source venv/bin/activate   # macOS / Linux
venv\Scripts\activate     # Windows PowerShell
pip install -r requirements.txt

Open the notebook:

jupyter notebook Bank_loan_data_EDA.ipynb
# or
jupyter lab

Execute cells top-to-bottom. If any datasets are missing, place them in the data/ folder or update the notebook cell that loads the file.

4. Notebook structure & steps performed

The notebook follows a clear, reproducible workflow:

Load libraries & dataset — pandas, numpy, matplotlib, seaborn, sklearn (if used).

Initial inspection — df.head(), df.info(), df.describe().

Missing value analysis — identify columns with missing data and decide imputation strategies.

Data cleaning — trimming whitespace, fixing datatypes, encoding categorical fields (Label/One-hot), handling outliers.

Feature engineering — create meaningful derived features (e.g., Income_per_family_member, TotalIncome, EMI_ratio).

Univariate analysis — histograms, boxplots for numeric features; barplots for categorical.

Bivariate analysis — correlation matrices, scatter plots, cross-tabs (e.g., Loan_Status by Education).

Summary of insights — bullet points with actionable findings.

5. Key analyses and visualizations

Distribution plots for ApplicantIncome, CoapplicantIncome, and LoanAmount (show skewness and potential log-transform needs).

Bar charts showing loan approval rates by Gender, Married, Education, Self_Employed, Property_Area.

Correlation heatmap for numeric variables to review multicollinearity.

Missing-value heatmap to visualize sparsity.

Tip: Save important figures from the notebook to figures/ for use in presentations or reports.

6. Dependencies

You can place exact package versions in requirements.txt. Example packages commonly used in this notebook:

pandas
numpy
matplotlib
seaborn
scikit-learn
jupyter
openpyxl  # if reading/writing Excel files
7. Data dictionary (example)

Update this section to match the columns in your dataset. Below is a typical example for bank loan datasets.

Loan_ID — Unique Loan ID

Gender — Male / Female

Married — Yes / No

Dependents — Number of dependents (0, 1, 2, 3+)

Education — Graduate / Not Graduate

Self_Employed — Yes / No

ApplicantIncome — Applicant's monthly income

CoapplicantIncome — Coapplicant's monthly income

LoanAmount — Loan amount (in thousands)

Loan_Amount_Term — Term of loan in months

Credit_History — 1.0 or 0.0 (shows if credit history meets criteria)

Property_Area — Urban / Semiurban / Rural

Loan_Status — Approved (Y) / Not Approved (N)

8. Recommendations & next steps

Feature importance / modelling: Use the cleaned dataset to train tree-based models (RandomForest, XGBoost) and inspect feature importances.

Model explainability: Apply SHAP or LIME to explain per-instance predictions.

Advanced preprocessing: Try target encoding for high-cardinality categoricals, or impute using model-based techniques.

Cross-validation: Use stratified K-folds when the target is imbalanced.

Deployment: Wrap preprocessing + model into a single sklearn.pipeline and save with joblib.

9. Author / Contact

Prepared by: Anjali Wable

Email: wableab1153@gmail.com

GitHub: https://github.com/anjali1153/Financial-Loan-Risk-EDA
