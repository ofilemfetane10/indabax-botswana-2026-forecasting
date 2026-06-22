# IndabaX Botswana 2026 Forecasting Challenge

## Overview

This repository contains our Phase 1 submission for the IndabaX Botswana 2026 AI Hackathon.

The project develops a multi-source forecasting framework to predict Botswana food inflation and explore how global economic shocks may propagate into human capital outcomes. The solution integrates shipping, energy, monetary policy, domestic food prices, and regional inflation indicators into a unified forecasting pipeline.

## Problem Statement

Botswana is a small open economy that is highly exposed to global shocks.

Changes in shipping costs, oil prices, regional food inflation, and monetary policy can influence domestic food prices and eventually affect household welfare, education outcomes, and health outcomes.

The objective of this project is to:

1. Forecast Botswana food inflation.
2. Identify important economic drivers of inflation.
3. Compare classical machine learning and deep learning forecasting approaches.
4. Explore regional inflation spillovers using cross-country HCP indicators.
5. Produce evidence that can support downstream human-capital forecasting.

## Datasets Used

This benchmark combines all five challenge datasets:

- Baltic Dry Index (shipping costs)
- Brent Crude Oil Prices
- Botswana Policy Rate
- FAO Botswana Food Price Indicators
- HCP Cross-Country Food Inflation Indicators

## Methodology

### Feature Engineering

The Baltic Dry Index was transformed into monthly indicators capturing:

- Monthly mean
- Monthly standard deviation
- Monthly maximum
- Monthly minimum
- Monthly range
- Last observed monthly value
- Intramonth return
- Momentum indicators
- Volatility indicators

Lag structures of:

- 1 month
- 2 months
- 3 months
- 6 months
- 9 months
- 12 months

were used to capture delayed transmission effects.

### Forecasting Models

Two forecasting approaches were evaluated:

#### Classical Machine Learning

- Gradient Boosting Regressor
- XGBoost-style forecasting pipeline
- Recursive 12-month forecasting

#### Deep Learning

- Two-layer LSTM
- 32 hidden units
- Dropout regularisation
- AdamW optimisation
- Early stopping

## Validation Results

| Model | RMSE | MAE | MAPE |
|---------|---------|---------|---------|
| Classical XGBoost / GBR | 4.392 | 3.634 | 73.33 |
| LSTM | 5.136 | 4.613 | 78.49 |

### Winner

The classical forecasting model achieved the best validation performance.

## HCP Linkage Analysis

The project additionally investigates relationships between Botswana food inflation and regional food inflation indicators from:

- South Africa
- Namibia
- Kenya
- Zimbabwe

Ordinary Least Squares regression and lag-based analysis were used to quantify regional spillover effects.

## Repository Structure

```text
.
├── notebook/
├── tables/
├── figures/
├── report_text/
├── outputs/
└── README.md
```
## Key Deliverables

The repository contains:

- Feature engineering summary
- Model comparison report
- Validation predictions
- Forecast outputs
- HCP linkage analysis
- Regression results
- Supporting tables and figures

## Technologies

- Python
- Pandas
- NumPy
- Scikit-Learn
- TensorFlow / Keras
- Statsmodels
- Matplotlib

## License

This repository is provided for academic and competition purposes.
