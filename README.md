# ESG Carbon Emissions Forecasting Pipeline
**Treeni | Capstone Project | Jan 2026 – Present**

> ⚠️ **Note:** This project was built using real corporate ESG data from a multinational technology company. The actual data is confidential and has been removed from this repository. Code is shared for portfolio purposes only. Full project including data and results is available upon request.

---

## Project Overview

Built a multi-series time-series forecasting system to predict future carbon emissions for a multinational technology company across **30+ facilities**, **15 cities**, and **10 regions** — independently per location and scope.

The system forecasts **Scope 1** (direct fuel emissions) and **Scope 2** (electricity/energy emissions) separately, generating 6, 12, and 24-month forecasts with confidence intervals for each combination of scope, region, city, and site.

---

## Problem Statement

Organizations maintain historical ESG records but often lack reliable methods to project future values for planning, target-setting, and sustainability decision-making. This project builds a pure time-series forecasting system using only historical observations — no external variables required.

---

## Technical Approach

### Data Preparation
- Imported and cleaned raw ESG datasets using **Pandas and NumPy**
- Standardized timestamps to consistent monthly frequency
- Handled missing values using **KNN Imputation** with forward fill and interpolation
- Detected and flagged anomalies using rolling mean and IQR methods
- Split data into independent time series per metric, scope, region, city, and site

### Forecasting Models
Tested and compared 7 model families per time series:
| Model | Use Case |
|---|---|
| Naive | Baseline benchmark |
| ARIMA (1,1,1) | Stationary/trending series |
| SARIMAX | Seasonal series |
| Holt's Linear Trend | Strong trend, no seasonality |
| Holt-Winters | Trend + seasonality |
| Simple Exponential Smoothing (SES) | Stable/flat series |
| Facebook Prophet | Complex seasonality |

### Model Selection
- Chronological train/validation split (last 12 months held out)
- Selected best model per series using **MAE, RMSE, and MAPE**
- Preferred simpler models when performance was similar

### Forecast Generation
- Generated 6, 12, and 24-month forecasts with **95% confidence intervals**
- Ensured non-negative forecast values for all ESG metrics
- Exported 12 Power BI-ready CSV files across 3 granularity levels

### Visualization
- Built interactive **Power BI dashboard** with:
  - Historical vs forecast line charts
  - Confidence bands
  - Filters by metric, scope, region, city, and site

---

## Tools & Technologies
- **Python** — Pandas, NumPy, Scikit-learn, Statsmodels, Prophet
- **Jupyter Notebooks** — development and documentation
- **Power BI** — interactive dashboard and stakeholder reporting
- **Excel** — raw data source

---

## Repository Structure
```
├── Scope1_Forecasting_Pipeline.ipynb   # Scope 1 (direct emissions) pipeline
├── Scope2_Forecasting_Pipeline.ipynb   # Scope 2 (energy emissions) pipeline
└── README.md
```

---

## Key Results
> Actual numbers are confidential. Available upon request during interviews.

- Forecasted emissions across 30+ independent time series at state, city, and site level
- Identified high-risk facilities with rising emission trends for operational review
- Generated 3-year forward forecasts enabling proactive sustainability target-setting
- Delivered findings via interactive Power BI dashboard to non-technical stakeholders

---

## Contact
**Drashti Ashish Kadakia**
📧 drashtiashishkadakia@gmail.com
🔗 [linkedin.com/in/drashti-kadakia](https://linkedin.com/in/drashti-kadakia)
