# SAFER Wind-Power Forecasting

Reproducibility materials for the study:

**State-Adaptive Forecast Error Recalibration for Probabilistic Wind Power Forecasting**

## Overview

This repository contains the code, processed data and final numerical outputs used to evaluate **State-Adaptive Forecast Error Recalibration (SAFER)** for probabilistic wind-power forecasting in South Africa.

The analysis combines hourly Eskom wind-generation data with regional ERA5 meteorological predictors and evaluates forecast horizons of **1, 3, 6, 12 and 24 hours**. The final experimental design uses a chronological **55% training / 10% validation / 20% calibration / 15% untouched test** split.

The main Jupyter notebook covers exploratory data analysis, validation-based point-model selection, conformal calibration, SAFER state construction, comparator methods, forecast evaluation and statistical validation.

## Repository structure

```text
SAFER-Wind-Forecasting/
├── README.md
├── SAFER_Wind_Research_.ipynb
├── requirements.txt
├── .gitignore
├── data/
│   └── processed/
│       ├── README.md
│       └── safer_wind_eskom_era5_merged.csv
└── results/
    ├── README.md
    ├── validation_model_selection.csv
    ├── point_forecast_test_metrics.csv
    ├── probabilistic_interval_results_90pct.csv
    └── bootstrap_safer_vs_global_90pct.csv
```

## Main notebook

`SAFER_Wind_Research_.ipynb` is the primary reproducibility notebook. It is organised as a research workflow covering data loading and checks, exploratory analysis, chronological splitting, state construction, point forecasting, probabilistic calibration, statistical testing and final result summaries.

## Data

The merged Eskom–ERA5 dataset used for exploratory analysis is stored at:

`data/processed/safer_wind_eskom_era5_merged.csv`

The five larger regional horizon-specific modelling datasets are provided as assets in the public GitHub release **data-v1.0**:

https://github.com/VinDW/SAFER-Wind-Forecasting/releases/tag/data-v1.0

Release assets:

- `safer_wind_eskom_era5_regional_model_dataset_h1.csv`
- `safer_wind_eskom_era5_regional_model_dataset_h3.csv`
- `safer_wind_eskom_era5_regional_model_dataset_h6.csv`
- `safer_wind_eskom_era5_regional_model_dataset_h12.csv`
- `safer_wind_eskom_era5_regional_model_dataset_h24.csv`

## Results

The `results/` directory contains the final numerical outputs reported in the study, including validation model selection, untouched-test point-forecast metrics, 90% prediction-interval results and moving-block bootstrap comparisons.

## Software

The analysis uses Python with NumPy, pandas, SciPy, scikit-learn, CatBoost and Matplotlib. Install the main dependencies with:

```bash
pip install -r requirements.txt
```

## Reproducibility

For a clean reproducibility run:

1. Download the five regional modelling datasets from the `data-v1.0` release.
2. Place them in the processed-data directory expected by the notebook.
3. Keep `safer_wind_eskom_era5_merged.csv` in `data/processed/` for the exploratory-analysis sections.
4. Open `SAFER_Wind_Research_.ipynb`.
5. Restart the kernel and run all cells sequentially from top to bottom.

The notebook records the random seed and package-version information used during execution.

## Methodological note

ERA5 is a retrospective reanalysis product rather than archived operational numerical weather prediction. The study should therefore be interpreted as a retrospective methodological evaluation of the SAFER recalibration framework rather than a live operational forecasting simulation.
