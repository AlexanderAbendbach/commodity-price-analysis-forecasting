# Commodity Price Analysis and Forecasting

## Project Overview

This project analyzes historical non-food commodity prices, including precious metals, industrial metals, and energy commodities. The goal is to clean and combine multiple commodity price datasets, explore long-term price and return behavior, identify relationships between commodities, and test whether forecasting models can outperform naive baselines.

The project is organized into three main parts:

1. ETL and data preparation
2. Exploratory data analysis
3. Forecasting and model evaluation

This is a research-style data science project. The focus is on building an end-to-end analytical workflow, understanding the data, comparing modeling approaches, and interpreting results honestly.

---

## Project Motivation

Commodity prices are affected by inflation, economic cycles, industrial demand, energy shocks, market uncertainty, and monetary conditions. Because of this, commodity markets are difficult to analyze and even harder to forecast.

This project explores several questions:

- How have different commodity prices evolved over time?
- Which commodities show similar return behavior?
- Are there meaningful commodity groups or regimes?
- Can machine learning models forecast future prices or returns better than simple naive baselines?
- What are the main limitations of commodity price forecasting?

The goal is not to claim perfect prediction, but to build a realistic data science workflow and evaluate models carefully.

---

## Data Sources

The project uses monthly historical commodity price data from public sources, including:

- Macrotrends
- World Bank commodity price data
- FRED CPI data

The dataset includes commodities such as:

- Gold
- Silver
- Platinum
- Palladium
- Copper
- Iron ore
- Lead
- Nickel
- Zinc
- Uranium
- Crude oil
- Natural gas

The final cleaned datasets contain monthly price levels and monthly returns.

---

## Project Structure

```text
commodity-price-analysis-forecasting/
│
├── README.md
├── requirements.txt
├── .gitignore
│
├── notebooks/
│   ├── 01_ETL.ipynb
│   ├── 02_EDA.ipynb
│   └── 03_Modeling_Forecasting.ipynb
│
├── data/
│   ├── raw/
│   └── processed/
│
└── images/
    ├── price_level_trends.png
    ├── return_analysis.png
    ├── correlation_heatmap.png
    ├── clustering_results.png
    └── model_results_summary.png
```

---

## Part 1: ETL and Data Preparation

The first notebook focuses on extracting, cleaning, transforming, and combining the raw commodity datasets.

Main steps:

- Load raw commodity price files
- Clean source-specific formatting issues
- Convert dates to monthly format
- Merge all commodities into one common time range
- Normalize units where possible
- Adjust prices for inflation where needed
- Create monthly return datasets
- Export cleaned price and return data

The ETL process produces two main datasets:

- Cleaned monthly commodity prices
- Monthly commodity returns

Some unit conversions, especially for energy commodities, are approximate and mainly used for normalization. Return calculations are less affected by constant unit conversions because percentage returns remain unchanged.

---

## Part 2: Exploratory Data Analysis

The second notebook analyzes historical commodity behavior using price levels, returns, risk metrics, correlations, and clustering methods.

Main analyses include:

- Long-term price trend analysis
- Annual return comparison
- Mean vs. median return comparison
- Volatility and risk-return analysis
- Monthly and annual correlation analysis
- PCA visualization
- Commodity clustering
- Lead-lag exploration
- Cluster-level behavior
- 12-month rolling drawdown analysis
- HDBSCAN regime-style clustering

The EDA shows that commodity groups behave differently over time. Precious metals, industrial metals, and energy commodities often show different risk-return profiles and correlation structures.

The lead-lag analysis is exploratory. It identifies possible lagged relationships between commodities, but these should not be interpreted as causal without further statistical testing.

The HDBSCAN analysis is used as a regime-style exploration of unusual monthly return states. Small clusters are interpreted carefully because they may represent unusual market conditions rather than stable long-term patterns.

---

## Part 3: Forecasting and Model Evaluation

The third notebook focuses on forecasting commodity prices and/or returns using machine learning models.

The modeling workflow includes:

- Creating lag features
- Creating multi-step forecast targets
- Adding optional Fourier features
- Splitting data into training and testing periods
- Using time-series-aware cross-validation
- Comparing models against naive baselines
- Evaluating total and horizon-wise performance

Models tested include:

- Linear Regression
- Ridge Regression
- Lasso Regression
- Decision Tree Regressor
- XGBoost Regressor
- MultiOutputRegressor
- RegressorChain
- Hybrid residual-correction models

Evaluation metrics include:

- MAE
- RMSE
- R²
- Horizon-wise RMSE
- Improvement over naive baseline

The naive baseline is important because simple persistence forecasts are often difficult to beat in price-level forecasting.

---

## Key Findings

Main findings from the project include:

- Commodity returns are noisy and difficult to forecast.
- Precious metals tend to show stronger relationships with each other than with industrial or energy commodities.
- Correlation patterns differ depending on whether monthly or annual returns are used.
- Clustering methods can reveal meaningful commodity groups, but results depend on feature choices and should be interpreted carefully.
- Some unusual market regimes can be identified through density-based clustering, although small clusters should not be overinterpreted.
- Forecasting models should always be compared against naive baselines, because a model that looks complex is not necessarily better.

Final modeling results will be added after the forecasting notebook is completed.

---

## Limitations

This project has several limitations:

- Commodity forecasting is difficult because prices and returns are affected by external shocks, macroeconomic events, geopolitical risk, and market sentiment.
- Some unit conversions, especially for crude oil and natural gas, are approximate.
- Lead-lag relationships are exploratory and do not prove causality.
- HDBSCAN clusters with few observations should be treated as unusual regimes rather than stable long-term market states.
- The project is notebook-based and research-style, not a production forecasting system.
- Model performance depends on the selected time period, features, forecast horizon, and validation method.

---

## How to Run the Project

1. Clone this repository:

```bash
git clone https://github.com/your-username/commodity-price-analysis-forecasting.git
```

2. Move into the project folder:

```bash
cd commodity-price-analysis-forecasting
```

3. Install the required packages:

```bash
pip install -r requirements.txt
```

4. Open the notebooks in Jupyter Notebook or JupyterLab.

5. Run the notebooks in this order:

```text
01_ETL.ipynb
02_EDA.ipynb
03_Modeling_Forecasting.ipynb
```

The cleaned datasets are saved in the `data/processed/` folder.

---

## Tools Used

- Python
- pandas
- NumPy
- matplotlib
- seaborn
- scikit-learn
- statsmodels
- XGBoost
- HDBSCAN
- Jupyter Notebook
- GitHub

---

## Future Improvements

Possible future improvements include:

- Add automated data downloading
- Refactor repeated notebook code into reusable Python scripts
- Build a formal walk-forward backtesting pipeline
- Add statistical tests for lead-lag relationships
- Add forecast uncertainty intervals
- Create a Streamlit or Dash dashboard
- Add experiment tracking for model comparison
- Turn the notebook workflow into a more production-style pipeline

---

## Project Status

Part 1 and Part 2 are completed. Part 3 focuses on forecasting and model evaluation and will be updated with final model results.
