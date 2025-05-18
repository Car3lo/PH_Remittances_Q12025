# Remittance Forecasting
![R](https://img.shields.io/badge/R-276DC3?style=for-the-badge&logo=r&logoColor=white)

This project showcases skills in `Time Series Forecasting`, `Econometric Analysis`, `R Proficiency`, `Tidyverse`, `ggplot2`. 

The goal is to forecast `Q1 2025` remittances using trend and seasonality models while validating results through diagnostic tests.

---

## Project: Forecasting Q1 2025 PH Remittances
- The dataset (`remittance_ph.csv`) contains monthly remittance data from 2013 to 2025.
- The goal is to analyze remittance trends, detect seasonality, and build a predictive model for 2025.
- Various time series models are tested, including **Linear Trend**, **Quadratic Trend**, and **Trend + Seasonality**.
- Codes are in `remittance.Rmd`. If you are viewing on `Github` click on `remittance.md`.

### Initial Trend and Seasonality Analysis
Before modeling, remittance data is explored through visualization.

**Nominal Cash Remittances Over Time**
![Trend Plot](https://lh3.googleusercontent.com/pw/AP1GczMyl8zdSilEGaDEL5Pu81-HJb1Q1qgNHd0_MgD1cj6MrW2mZVTe517CgWjt5yIaU83QcGvQA8OAgnNCNMwVIYCvIl0lX-U38v--NvHBeY8mLy9CyXF172hRQM0I-FF8HKU01E3WfJek9zBnD4RP5qI9=w803-h544-s-no-gm?authuser=0)

**Seasonality Effects on Remittances**
![Seasonality Plot](https://lh3.googleusercontent.com/pw/AP1GczOJa8JQVL0jB8sdjDTY_bX1JLn0bLGXP2OfKEH1TlR6QyJ8BrCS_zqItE8z11q0BgrwTtCWAGN_FY-nHYUiUAAJUNodXPvUeN_MAYLJhjR1lHbcf6OL6uWETByDmqi292Hm7mmGyNYY8PsNVlpqhvx9=w769-h539-s-no-gm?authuser=0)

A clear upward trend is observed, interrupted by a dip during the 2020 pandemic. Seasonality peaks appear in **July (school tuition payments) and December (holiday effects)**.

---

### Model Selection & Testing
Several regression models are tested to capture trend and seasonality:

#### **Model Comparisons**
- `Deterministic Linear Trend`: Captures overall upward movement.
- `Quadratic Trend`: Accounts for possible curvature in the data.
- `Seasonality Model`: Uses monthly dummy variables.
- `Trend + Seasonality`: Combines time and seasonal effects for better accuracy.

**Model Selection Table**
![Model Summary](https://lh3.googleusercontent.com/pw/AP1GczP3KjirTi68PD7JEDEU0buNgz1ETKKtiUQ11rosMVdRXcaIzkA-z19nywEJ9PWRBfcrmXlO9HbTZHIQo_a8mj-vf4q2JYmY0UxfgI4UAVFpF1CDOcUXbii4oyxkDnUWnzZfx94AMzj4cOh3q_B8bqqp=w655-h957-s-no-gm?authuser=0)

From `AIC/BIC` and model performance, **Trend + Seasonality** yields the best results.

---

### Forecasting Monthly Remittances for Q1 2025
Using the best-performing model, monthly remittance forecasts for `Jan - Mar 2025` are generated.

**Forecast Plot**
![Forecast Plot](placeholder_image_url)

Key findings:
- **January 2025 remittance estimate:** `$2,860M`
- **February 2025 remittance estimate:** `$2,767M`
- **March 2025 remittance estimate:** `$2,979M`
- **Q1 2025 growth rate compared to Q1 2024:** `+4.71%`

---

### Residual Diagnostics
The model is validated through diagnostic checks, including **Ljung-Box tests** for white noise.

**Residual Analysis**
![Residual Plot](https://lh3.googleusercontent.com/pw/AP1GczMNCZ3IeMuo1_iYHZgbPpzYmHv3MaHAPdu3s0F3kdvAD66VJ4M3Xxo_BCHK4d2Xn2I8aL49RptxD83zA7k-Awgn9lmFCRo-WY7uaO4KdfoigO8ky5CH28Hl5iE5SVCnvCLGsy_NWT9GCl1MYiIkgWfc=w792-h551-s-no-gm?authuser=0)

Results indicate some autocorrelation in residuals, possibly due to the pandemic altering typical remittance behaviors.

---

### Important Considerations
- Due to Duterte’s arrest, OFWs have scheduled a week in March where they will not send remittances as protest aka a shock.
- The model will not account for this “shock” and has probably overstated the remittances for that month of March. This event may distort accuracy.
- Despite this, **the model still provides a reliable baseline for expected remittance flows**.

---

