# Commodity Price Analysis and Forecasting

## Overview

This project analyzes monthly non-food commodity prices, including precious metals, industrial metals, and energy commodities. The goal is to clean and combine data from multiple sources, explore historical price and return behavior, and test forecasting models against simple naive baselines.

The project is split into three parts:

- `Data analysis for non-food commodities - Part 1 (ETL).ipynb`: data cleaning, merging, unit normalization, inflation adjustment, and return calculation
- `Data analysis for non-food commodities - Part 2 (EDA).ipynb`: price trends, returns, correlations, clustering, drawdowns, and regime-style analysis
- `Data analysis for non-food commodities - Part 3 (Forecasting).ipynb`: forecasting models, baseline comparison, and horizon-wise evaluation

## Data

The project uses public monthly commodity price data from sources such as Macrotrends and FRED.

Commodities include gold, silver, platinum, palladium, copper, iron ore, lead, nickel, zinc, uranium, crude oil, and natural gas.

## Methods

Main steps:

- Cleaned and merged commodity price datasets
- Converted dates to monthly frequency
- Adjusted selected prices for inflation and standardized units
- Created monthly return datasets
- Analyzed price trends, returns, volatility, correlations, and drawdowns
- Applied PCA, clustering, and HDBSCAN-style regime analysis
- Built forecasting models using lag features, optional Fourier features, and multi-output targets
- Compared models against naive baselines

## Key Notes

Commodity forecasting is difficult because prices and returns are noisy and affected by external shocks. Lead-lag relationships and regime clusters are exploratory and should not be interpreted as causal. Some energy unit conversions are approximate and mainly used for normalization.

## Tools

Python, pandas, NumPy, matplotlib, seaborn, scikit-learn, statsmodels, XGBoost, HDBSCAN, Jupyter Notebook.

## Folder structure

- Data
    - Processed data
    - Raw data
- Figures
- Notebooks
    - Data analysis for non-food commodities - Part 1 (ETL).ipynb
    - Data analysis for non-food commodities - Part 2 (EDA).ipynb
    - Data analysis for non-food commodities - Part 3 (Forecasting).ipynb
- requirements.txt

## How to Run

Install the required packages:

```bash
pip install -r requirements.txt
```
The notebooks can be accessed via Jupyter Notebook.
Run the notebooks in order:

```text
Data analysis for non-food commodities - Part 1 (ETL).ipynb
Data analysis for non-food commodities - Part 2 (EDA).ipynb
Data analysis for non-food commodities - Part 3 (Forecasting).ipynb
```

## Status

Part 1 and Part 2 are completed. Part 3 focuses on forecasting and model evaluation.
