# African CO₂ Emissions: Data Analysis and Linear Regression

**Data Engineering Principles (DAT 3103) · Strathmore University · 2025**  
**Author:** Christopher Nyaga Munyiri

## Overview

This academic project explores a Kaggle dataset of African CO₂ emissions, comparing countries and time trends and developing an introductory linear regression model based on population, GDP per capita, and energy-use measures.

The notebook contains the original analysis and saved figures/results. Its data-loading path has been adapted from Kaggle to a local `data/` directory. **The reported model scores are exploratory and not independently revalidated for this public portfolio.**

## What the notebook demonstrates

- Load and inspect a multi-country CSV dataset with pandas
- Examine missing values, data types and summary statistics
- Apply numerical median imputation, min-max scaling and IQR-based outlier filtering
- Produce country-level trend plots, a two-country comparison, a correlation heatmap and regression diagnostics
- Fit a scikit-learn `LinearRegression` model and inspect MAE, MSE and R²
- Save and reload a fitted model with Joblib

## Files

- `co2_emissions_africa_analysis.ipynb` — original authored analysis, with the input path changed for local use
- `requirements.txt` — Python dependencies
- `data/README.md` — data placement instructions (raw dataset not redistributed)

## Run locally

1. Download the source dataset **CO₂ Emission Africa** from Kaggle and review its licence/terms.
2. Place the CSV at `data/co2 Emission Africa.csv`.
3. Install dependencies: `python -m pip install -r requirements.txt`.
4. Open `co2_emissions_africa_analysis.ipynb` in Jupyter or VS Code and run cells in order from the project directory.

The notebook's final cells write a fitted `.pkl` model into the working directory; `.gitignore` excludes these generated model files.

## Methods and important limitations

The notebook performs imputation, scaling and outlier filtering before an 80/20 random train–test split. In particular, outlier filtering considers the target variable. This approach can produce optimistic test scores, so **the historical reported R² should not be presented as a reliable estimate of deployment performance**. Future improvements should place all fitting-based preprocessing within the training pipeline, evaluate chronological or country-aware splits, and report errors in the original emissions units.

The associated presentation described an SQLite relational database and SQL queries, but no executable database implementation was present among the source files reviewed. **This repository does not claim to include a working SQL pipeline.**

## Planned improvements

- Make preprocessing leakage-safe and add robust holdout evaluations
- Validate selected findings directly from the raw data
- Add a tested relational SQLite/SQL implementation as a separate, documented extension
- Regenerate figures and provide a concise findings summary

## Data and attribution

The data originated from a publicly discoverable Kaggle dataset, not from original field collection. The dataset is intentionally omitted pending verification of redistribution rights. This is a student analysis project, not an operational environmental forecasting tool.
