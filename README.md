# SAFER Wind-Power Forecasting

Reproducibility materials for the study:

**State-Adaptive Forecast Error Recalibration for Reliable Probabilistic Wind Power Forecasting in Renewable Energy Applications**

## Overview

This repository contains the research code, processed modelling inputs and numerical outputs used to evaluate **State-Adaptive Forecast Error Recalibration (SAFER)** for probabilistic wind-power forecasting in South Africa.

The analysis combines hourly Eskom wind-generation data with regional ERA5 meteorological predictors and evaluates forecast horizons of **1, 3, 6, 12 and 24 hours**. The final experimental design uses a chronological **55% training / 10% validation / 20% calibration / 15% untouched test** split.

The main analysis is provided as a Jupyter Notebook and includes exploratory data analysis, validation-based point-model selection, conformal calibration, SAFER state construction, comparator methods, forecast evaluation and statistical validation.

## Repository structure

```text
SAFER-Wind-Forecasting/
├── README.md
├── SAFER_Wind_Research_Analysis.ipynb
├── requirements.txt
├── .gitignore
├── data/
│   └── processed/
│       └── README.md
├── development/
│   └── README.md
└── results/
    ├── README.md
    ├── tables/
    └── predictions/
```

### Main notebook

`SAFER_Wind_Research_Analysis.ipynb` is the primary reproducibility notebook. It is structured as a research workflow: data loading and checks, exploratory data analysis, chronological splitting, state construction, point forecasting, probabilistic calibration, statistical testing and final result summaries.

### Development notebooks

The `development/` directory is reserved for the original notebooks used during data preparation, exploratory analysis and methodological development. These files document the development history but are not required to reproduce the final reported experiment.

### Data

Processed modelling inputs are documented in `data/processed/README.md`. The five regional horizon-specific modelling files are large and exceed GitHub's ordinary per-file limit, so they should be managed using Git LFS or a dedicated research-data archive rather than ordinary Git blobs.

### Results

Generated tables and prediction files can be written to the `results/` directory. The main numerical results are also displayed directly in the Jupyter Notebook.

## Software

The analysis uses Python with NumPy, pandas, SciPy, scikit-learn, CatBoost and Matplotlib. Install the main dependencies with:

```bash
pip install -r requirements.txt
```

## Reproducibility

For a clean reproducibility run:

1. Place the required processed datasets in the expected processed-data directory.
2. Open `SAFER_Wind_Research_Analysis.ipynb`.
3. Restart the kernel.
4. Run all cells sequentially from top to bottom.

The notebook records the random seed and package-version information used during execution.

## Methodological note

ERA5 is a retrospective reanalysis product rather than archived operational numerical weather prediction. The study should therefore be interpreted as a retrospective methodological evaluation of the SAFER recalibration framework rather than a live operational forecasting simulation.
