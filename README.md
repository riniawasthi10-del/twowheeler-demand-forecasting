# 🏍️ Macroeconomic Forecasting of Two-Wheeler Demand in India

## Overview
This project forecasts monthly two-wheeler demand in India using macroeconomic variables. I built SARIMA and VAR models to capture both the seasonal patterns in vehicle sales and the transmission effects of monetary policy and fuel price shocks on consumer demand.

---

## Motivation
Two-wheeler demand in India is highly sensitive to fuel prices and credit conditions. Understanding how repo rate changes and fuel price movements affect demand has direct implications for consumer finance, credit risk, and sectoral lending decisions — which is what drew me to this problem.

---

## Data
- **Period:** Monthly data, 2010–2024
- **Sources:** RBI, MOSPI, SIAM (Society of Indian Automobile Manufacturers)
- **Variables used:**
  - Two-wheeler sales volume (units)
  - Repo rate (RBI)
  - Fuel prices (petrol, monthly average)
  - CPI Inflation

---

## Methodology

### 1. Stationarity Diagnostics
- Applied Augmented Dickey-Fuller (ADF) tests to all series
- First-differenced non-stationary variables before modelling

### 2. SARIMA Model
- Used ACF/PACF plots to identify seasonal and non-seasonal orders
- Model selection via AIC and BIC criteria
- Captured seasonal demand cycles (festival season peaks, Q1 dips)

### 3. VAR Model
- Built a Vector Autoregression model to capture dynamic interactions between sales, repo rate, and fuel prices
- Estimated optimal lag length using AIC/BIC
- Conducted impulse response analysis to trace shock transmission

### 4. Forecast Validation
- Split data into in-sample and out-of-sample periods
- Compared SARIMA vs VAR forecasts using RMSE
- VAR model outperformed SARIMA on out-of-sample accuracy for shock periods

---

## Key Findings
- Repo rate hikes of 25 bps transmitted a measurable dampening effect on two-wheeler demand within **2–3 quarters**
- Fuel price shocks showed a faster, more immediate effect on demand compared to monetary policy
- SARIMA captured seasonal patterns well; VAR performed better when macroeconomic shocks were present

---

## Tools & Libraries
| Tool | Purpose |
|------|---------|
| Python | Core analysis |
| Pandas, NumPy | Data cleaning and manipulation |
| Statsmodels | SARIMA, VAR, ADF tests |
| Matplotlib | Visualisation |
| Excel | Initial data compilation |

---

## Files
```
├── data/                  # Raw and cleaned datasets
├── notebooks/
│   ├── 01_eda.ipynb       # Exploratory data analysis
│   ├── 02_sarima.ipynb    # SARIMA modelling
│   ├── 03_var.ipynb       # VAR modelling and IRF
├── outputs/               # Forecast plots, IRF charts
└── README.md
```

---

## Author
**Rini Awasthi**  
MA General Economics, Madras School of Economics  
ge25rini@mse.ac.in
