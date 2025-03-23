# shallowML_regression
Assessing different models and approaches for predicting SST

These notebooks walk through several (non-exhaustive) options for predicting Sea Surface Temperature (SST) using co-variables including Sea Surface Height (SSH), Salinity (SSS), Currents (Vuo and Vvo), and Ocean Mixed Layer Depth (MLD). Time-related variables, such as 'day of year', and categorical variables like **season** and ENSO state (**MEI**) are also tested.

From the Copernicus Marine Service (CMEMS), training data were taken from the freely available Level-4 Global Ocean Physics Reanalysis Product (ID: GLOBAL_MULTIYEAR_PHY_001_030; daily). Testing data were sourced from the Level-4 Global Ocean Physics Analysis and Forecast Product (ID: GLOBAL_ANALYSISFORECAST_PHY_001_024; daily).  
In this example, data were extracted for the Gulf Stream at the location: POINT (-80.00, 30.00).

The ENSO state data — Multivariate ENSO Index Version 2 (MEI.v2) — were provided at no cost by NOAA:  
https://psl.noaa.gov/enso/mei/

---

## Shallow ML Regressors for Environmental Time Series

This repository provides worked examples of shallow machine learning regressors applied to environmental time series data. These notebooks demonstrate core principles of supervised learning, model evaluation, and interpretability.

The focus is on introducing **interpretable**, **non-deep** methods suitable for students and practitioners in remote sensing, oceanography, and environmental data science. The material is designed for learners with limited coding or ML experience.

---

## Models Covered

- Multiple Linear Regression (OLS)
- Elastic Net Regularised Regression
- Support Vector Regression (SVR)
- Random Forest Regression
- XGBoost Regression
- CatBoost Regression

All models are trained to predict **SST** using **SSH, SSS, Vuo, Vvo, and MLD** as predictors (features/ co-variables). 

Optional categorical features include **season** and **ENSO state** (MEI.v2).

---

## Notebook Overview

| Notebook | Model Type | Highlights |
|----------|------------|------------|
| `ML1_LinearRegression_cmems_csv.ipynb` | OLS Regression | Baseline model with interpretable coefficients |
| `ML2_MVar_ElasticNet_cmems_csv.ipynb` | Elastic Net | Combines L1 & L2 penalties, cross-validation |
| `ML2b_SupportVector_R_cmems_csv.ipynb` | SVR | Linear + polynomial kernels; SHAP for feature effect |
| `ML3_RandomForest_R_cmems_csv.ipynb` | Random Forest | Tree-based ensemble; robust to noise; SHAP |
| `ML4_XGBoost_Regres_cmems_csv.ipynb` | XGBoost | Gradient boosting, tuned with RandomizedSearchCV |
| `ML5a–ML5d` | XGBoost & CatBoost | Compare boosting methods; SHAP + categorical handling (CatBoost) |

---

## Explainable ML

Most models include SHAP (SHapley Additive exPlanations) to support interpretability, particularly for tree-based and kernel models.

⚠️ **Note on SVR**  
SHAP + SVR is **computationally expensive**. Running SHAP on the full dataset can take literally hours, and even modest background sample sizes need long runtimes. For demonstration purposes, the SVR notebook here uses a very small subset (10 samples) to allow the notebook to run in a reasonable time. This limits SHAP accuracy, but still illustrates the method’s logic and application.

---

## How to Use

1. Clone the repository:
   ```bash
   git clone https://github.com/Indungulo/shallowML_regressors.git
   ```
2. Install the required packages (I prefer pip because it works on the uni computers ^^)
   ```bash
   pip install numpy pandas scikit-learn xgboost catboost shap matplotlib seaborn
   ```
3. Open the .ipynb notebooks in your preferred environment. In my classes, we use Jupyter Notebook.

4. Run each notebook top to bottom. Notebooks are independent but use the same CMEMS CSV data.



## License & Credits

All code here is released for teaching and academic use.

Ocean data: © Copernicus Marine Service

MEI.v2 data: NOAA PSL https://psl.noaa.gov/enso/mei/
