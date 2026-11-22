# Walmart Weekly Sales Forecasting

A machine learning and time-series forecasting project developed to predict weekly retail sales across Walmart stores and departments using historical sales, store metadata, holiday indicators, and macroeconomic features.

---

## Project Overview

Accurate retail demand forecasting is essential for inventory optimization, staffing, and supply chain management. This project merges multiple historical datasets from Walmart stores to analyze seasonal trends, store-type performance, and holiday spikes, then trains and compares regression models using engineered time-based and lag features.

---

## Dataset Description

The pipeline integrates three primary CSV datasets:

| File | Description | Key Columns |
| :--- | :--- | :--- |
| **`train.csv`** | Historical weekly sales records (Feb 2010 – Oct 2012) | `Store`, `Dept`, `Date`, `Weekly_Sales`, `IsHoliday` |
| **`features.csv`** | Regional and promotional data per store and week | `Temperature`, `Fuel_Price`, `MarkDown1–5`, `CPI`, `Unemployment` |
| **`stores.csv`** | Store-level metadata | `Store`, `Type` (`A`, `B`, `C`), `Size` |

---

## Project Workflow

1. **Data Integration & Exploration:** Merged sales, store attributes, and external economic features into a unified dataset (`421,570` records across `45` stores).
2. **Data Cleaning & Preprocessing:**
   - Converted `Date` to datetime format and extracted calendar features (`Year`, `Month`, `Week`, `Day_of_week`, `Day_of_year`).
   - Imputed missing numerical values (`Temperature`, `Fuel_Price`, `CPI`, `Unemployment`, `Size`) using column means.
   - Encoded categorical attributes (`IsHoliday` as binary flag, store `Type` as ordinal numeric values).
3. **Exploratory Data Analysis (EDA):** Visualized weekly sales trends over time, average sales by store type (`A`, `B`, `C`), monthly seasonality, holiday impact, and correlations with temperature and store size.
4. **Feature Engineering (Lag Features):** Generated historical lag features (`Sales_lag_1`, `Sales_lag_2`, `Sales_lag_3`, `Sales_lag_4`, `Sales_lag_5`, and `Sales_lag_52`) grouped by `Store` and `Dept` to capture short-term momentum and annual seasonality.
5. **Time-Based Split & Scaling:** Performed an 80/20 chronological train-test split and standardized input features with `StandardScaler`.
6. **Model Training & Comparison:** Trained and evaluated three regression models:
   - **Linear Regression**
   - **Random Forest Regressor**
   - **Gradient Boosting Regressor**
7. **Evaluation & Serialization:** Compared models using **MAE**, **RMSE**, and **R² Score**, visualized actual vs. predicted sales, analyzed feature importances, and exported the best model (`walmart_sales_forecast_model.pkl`) and scaler (`walmart_scaler.pkl`).

---

## Tech Stack

- **Language:** Python 3
- **Data Manipulation:** `pandas`, `numpy`
- **Visualization:** `matplotlib`, `seaborn`
- **Machine Learning & Stats:** `scikit-learn`, `statsmodels`, `joblib`

---

## Repository Structure

```text
├── Task 7 Sales Forecasting Description.ipynb   # Main Jupyter Notebook
├── train.csv                                    # Training dataset
├── test.csv                                     # Test dataset
├── features.csv                                 # Macroeconomic & holiday features
├── stores.csv                                   # Store metadata
├── walmart_sales_forecast_model.pkl             # Saved best-performing model
├── walmart_scaler.pkl                           # Saved StandardScaler object
└── README.md                                    # Project documentation
```

---

## How to Run

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/MernaMero/](https://github.com/MernaMero/)<your-repo-name>.git
   cd <your-repo-name>
   ```

2. **Install dependencies:**
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn statsmodels joblib
   ```

3. **Run the notebook:**
   Open `Task 7 Sales Forecasting Description.ipynb` in Jupyter Notebook, JupyterLab, or VS Code and run all cells sequentially.

---

## Results Summary

*(Update with your final run metrics)*

| Model | MAE ($) | RMSE ($) | R² Score |
| :--- | :---: | :---: | :---: |
| **Gradient Boosting Regressor** | `TBD` | `TBD` | `TBD` |
| **Random Forest Regressor** | `TBD` | `TBD` | `TBD` |
| **Linear Regression** | `TBD` | `TBD` | `TBD` |
