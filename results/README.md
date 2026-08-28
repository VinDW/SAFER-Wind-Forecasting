# Results

This folder contains the final numerical outputs reported in the SAFER wind-power forecasting study.

## Files

- `validation_model_selection.csv` — validation RMSE for Linear Regression, Random Forest and CatBoost at 1, 3, 6, 12 and 24-hour horizons, including the selected model at each horizon.
- `point_forecast_test_metrics.csv` — untouched-test RMSE, MAE, MASE and sMAPE for the validation-selected point forecaster at each horizon.
- `probabilistic_interval_results_90pct.csv` — 90% prediction-interval results for Global split conformal, SAFER, CQR and ACI, including PICP, MPIW, coverage error and Winkler score.
- `bootstrap_safer_vs_global_90pct.csv` — dependence-aware moving-block bootstrap comparisons between SAFER and Global split conformal prediction for coverage, interval width and Winkler score.

The five regional horizon-specific modelling datasets are provided in the public GitHub release **data-v1.0**:

https://github.com/VinDW/SAFER-Wind-Forecasting/releases/tag/data-v1.0

The merged Eskom–ERA5 dataset used for exploratory analysis is stored in `data/processed/safer_wind_eskom_era5_merged.csv`.

These files correspond to the final analysis and are included so the reported numerical results can be inspected without rerunning the full notebook.
