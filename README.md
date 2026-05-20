# Turkey Macroeconomic & Econometric Correlation Dashboard

An empirical research project analyzing the structural macroeconomic shifts in Turkey across three key eras: **Pre-COVID**, **COVID Pandemic**, and **Post-COVID (Post-Pandemic Recovery)**. The project aggregates data directly from the **Central Bank of the Republic of Turkey (TCMB) EVDS system** using Python to model key macroeconomic relationships.

---

## 📈 Empirical Research & Key Hypotheses

This project evaluates three core macroeconomic theories within the Turkish structural economic context:

1. **Okun's Law in Turkey:** 
   - *Hypothesis:* A negative correlation between GDP per Capita growth and the Unemployment Rate.
   - *Finding:* Validated. The negative correlation significantly strengthened in the post-pandemic era, demonstrating that output changes command high employment costs in Turkey.

2. **Phillips Curve Breakdown:**
   - *Hypothesis:* An inverse relationship between Inflation (CPI) and Unemployment.
   - *Finding:* Anomaly detected. In the post-COVID era, Turkey experienced a negative correlation between unemployment and inflation, reflecting a cost-push inflationary regime and labor market structural mismatches rather than traditional demand-pull dynamics.

3. **Exchange Rate Pass-Through (ERPT):**
   - *Hypothesis:* Transmission of USD/TRY volatility directly into domestic price levels.
   - *Finding:* Extremely strong positive correlation (~0.98+), demonstrating an almost immediate and severe Exchange Rate Pass-Through into domestic inflation, driven by Turkey's heavy reliance on imported intermediate goods.

---

## 🛠️ Tech Stack & Methods

- **Data Sourcing:** `evds` Python API Wrapper (Central Bank of Turkey Electronic Data Delivery System)
- **Data Wrangling:** `pandas` (cleaning monthly data, handling datetime formats, computing percentage changes)
- **Visualization & Stat Modeling:** `matplotlib`, `seaborn` (time series plots, dual-axis plotting, correlation matrices, heatmaps)

---

## 📁 Project Structure

```text
├── CVS/                           # Downloaded CSV datasets from TCMB EVDS
│   ├── cpi_data_with_monthly_change.csv
│   ├── turkey_gdp_growth_all_years.csv
│   ├── unemployment_rate_data.csv
│   └── usd_try_data.csv
├── Python_project.ipynb           # Main Jupyter Notebook with data fetching, plots & analysis
├── requirements.txt               # Project dependency list
└── README.md                      # Professional project documentation
```

---

## 🚀 Setup & Execution

### 1. Prerequisites
Get an API key from the [TCMB EVDS Portal](https://evds2.tcmb.gov.tr/).

### 2. Installation
Clone this repository and install the dependencies:
```bash
pip install -r requirements.txt
```

### 3. Run Notebook
Open Jupyter Lab or VS Code and run `Python_project.ipynb`. Remember to set your EVDS API key:
```python
from evds import evdsAPI
evds = evdsAPI("YOUR_EVDS_API_KEY")
```

---

## 📊 Summary of Findings

| Period | USD/TRY vs CPI (Pass-through) | GDP per Capita vs Unemployment (Okun's Law) | Unemployment vs CPI (Phillips Curve) |
| :--- | :---: | :---: | :---: |
| **Pre-Pandemic** | Moderate / Systematic | Weak Negative | Unsystematic |
| **Pandemic** | Strong Positive | Moderate Negative | High Structural Correlation |
| **Post-Pandemic** | **Near Perfect Positive (~0.99)** | **Strong Negative** | **Negative Correlation (Curve Shift)** |

*Conclusions suggest that Turkey's macroeconomic indicators are deeply integrated and highly vulnerable to currency shocks, requiring active monetary stabilization to combat structural imbalances.*
