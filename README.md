# Customer Churn Prediction + Survival Analysis (Telco Dataset)

This repo contains an end-to-end customer analytics workflow on the classic Telco Customer Churn dataset:
1) **Exploratory Data Analysis (EDA)**  
2) **Churn Prediction (Classification)** using **Random Forest + SMOTE + GridSearchCV**  
3) **Customer Survival Analysis** using **Kaplan–Meier** and **Cox Proportional Hazards (lifelines)**  
4) Model explainability artifacts (SHAP / permutation importance / PDP)

---

## Project Files

- `data.csv`  
  Telco dataset (7,043 rows × 21 columns) with target column: **`Churn`**

- `Exploratory Data Analysis.ipynb`  
  Visual + statistical EDA and feature insights (tenure effects, services, contract types, etc.)

- `Churn Prediction Model.ipynb`  
  Data prep + model training + tuning + evaluation + explainability
  - **RandomForestClassifier**
  - **SMOTE** for imbalance handling
  - **GridSearchCV** for hyperparameter tuning
  - Metrics: accuracy, precision, recall, F1, ROC-AUC, confusion matrix
  - Explainability: **SHAP**, permutation importance (eli5), PDPs (pdpbox)

- `Customers Survival Analysis.ipynb`  
  Survival modeling to understand *time-to-churn*
  - Kaplan–Meier curves
  - Log-rank tests
  - CoxPH model (hazard ratios & significance)

- `model.pkl`  
  Saved churn prediction model (pickle)

- `survivemodel.pkl`  
  Saved survival model (pickle)

- `explainer.bz2`  
  Compressed explainability artifact (typically a SHAP explainer object)

---

## Dataset (Columns)

Common key columns include:
- Customer profile: `gender`, `SeniorCitizen`, `Partner`, `Dependents`
- Tenure/plan: `tenure`, `Contract`
- Services: `PhoneService`, `InternetService`, `OnlineSecurity`, `TechSupport`, etc.
- Billing: `PaperlessBilling`, `PaymentMethod`
- Charges: `MonthlyCharges`, `TotalCharges`
- Target: `Churn`

---

## How to Run (Recommended Order)

### Option A: Run the notebooks (easiest)
1. Open Jupyter/VS Code notebooks
2. Run in this order:
   1) `Exploratory Data Analysis.ipynb`  
   2) `Churn Prediction Model.ipynb`  
   3) `Customers Survival Analysis.ipynb`