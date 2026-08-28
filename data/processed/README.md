# Processed data

This folder documents the processed inputs used by the final SAFER analysis.

## Exploratory dataset

The merged Eskom–ERA5 dataset used for exploratory analysis is stored directly in this repository:

- `safer_wind_eskom_era5_merged.csv`

## Horizon-specific modelling datasets

The five larger regional modelling datasets are distributed through the public GitHub release **data-v1.0** because they exceed GitHub's ordinary per-file repository limit:

https://github.com/VinDW/SAFER-Wind-Forecasting/releases/tag/data-v1.0

Release assets:

- `safer_wind_eskom_era5_regional_model_dataset_h1.csv`
- `safer_wind_eskom_era5_regional_model_dataset_h3.csv`
- `safer_wind_eskom_era5_regional_model_dataset_h6.csv`
- `safer_wind_eskom_era5_regional_model_dataset_h12.csv`
- `safer_wind_eskom_era5_regional_model_dataset_h24.csv`

Download those five files and place them in the processed-data directory expected by the notebook before running the full forecasting workflow.
