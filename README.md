# Random Forest Shoreline Extraction and Change Analysis — Metaponto, Italy

## Overview

This repository contains the Python code, input datasets, trained Random Forest (RF) model, and analysis results for the study **“Random Forest Shoreline Extraction from High-Resolution HAWK Imagery: A Multi-Decadal Coastal Analysis at Metaponto, Italy.”**

The study uses high-resolution HAWK satellite imagery acquired on **27 July 2026** to extract the shoreline at Metaponto, southern Italy, and compares it with historical shoreline observations from **1950, 2000, 2006, and 2020**, provided by ISPRA.

The workflow includes Random Forest land–water classification, shoreline extraction, independent photo-interpretation validation, and shoreline-change analysis using Net Shoreline Movement (NSM), End Point Rate (EPR), Shoreline Change Envelope (SCE), and Linear Regression Rate (LRR).

## Repository Structure

```text
coastline-analysis/
│
├── data/
│   ├── HAWK image corner coordinates
│   └── ISPRA historical transect files
│
├── model/
│   └── RF_model_HAWK_20260727.joblib
│
├── notebooks/
│   └── Metaponto Coastaline Analysis.ipynb
│
├── results/
│   ├── Photo-interpreted shoreline data
│   ├── RF–manual shoreline validation results
│   ├── Common-transect shoreline-change results
│   └── Historical ISPRA shoreline-change workbooks
│
└── README.md
```

## Folder Descriptions

### `data/` — Input Data

Contains the HAWK image corner-coordinate information and three historical ISPRA shoreline-intersection datasets covering 1950–2000, 2000–2006, and 2006–2020.

### `model/` — Trained Random Forest Model

Contains **`RF_model_HAWK_20260727.joblib`**, the saved Random Forest classifier trained using HAWK multispectral imagery. The model can be reused for land–water classification with compatible spectral inputs and Python dependencies.

### `notebooks/` — Python Code

Contains **`Metaponto Coastaline Analysis.ipynb`**, the main Jupyter Notebook implementing the shoreline extraction, validation, historical comparisons, statistical calculations, and visualization workflow.

### `results/` — Processed Results

Contains the shoreline datasets and analytical outputs, including:

- **Photo-interpreted shoreline:** Independent reference shoreline digitized using 144 vertices from the 2026 HAWK image.
- **RF–manual validation:** Positional comparison between the RF-extracted and manually interpreted shorelines.
- **Common-transect results (1950–2026):** Shoreline positions and change statistics for 121 transects across approximately 12 km of coastline, including 120 valid RF–manual comparisons. Related manuscript outputs: Figures 17–19 and Table 2.
- **Historical ISPRA results:** Four Excel workbooks (`risultati_1950_2000.xlsx`, `risultati_2000_2006.xlsx`, `risultati_2006_2020.xlsx`, and `risultati_serie_completa_1950_2020.xlsx`) containing shoreline-change statistics for approximately 850 transects across the broader historical coastal region. Related manuscript outputs: Figures 10–16.

**Note:** The broader historical ISPRA analysis and the approximately 12-km HAWK study area have different spatial extents.

## Key Features

- Random Forest shoreline extraction from high-resolution HAWK imagery.
- Independent validation against a manually photo-interpreted shoreline.
- Historical shoreline comparison from 1950 to 2026.
- Calculation of NSM, EPR, SCE, and LRR.
- Statistical analysis and visualization of coastal erosion and accretion.
- Saved RF model for reuse without retraining.

## Main Results

The Random Forest classifier achieved **99.917% overall agreement** on the spatially separated land–water validation dataset.

Comparison against the manually interpreted shoreline across 120 common transects produced:

- **Mean absolute difference:** 11.02 m
- **Median absolute difference:** 6.13 m
- **RMSE:** 17.45 m

For the 2020–2026 period, the mean NSM across 121 common transects was **−11.82 m**, indicating predominantly negative shoreline displacement under the adopted transect sign convention.

## Requirements

Python 3.x and scientific Python libraries, including `numpy`, `pandas`, `matplotlib`, `scikit-learn`, `scikit-image`, `scipy`, `rasterio`, `geopandas`, `openpyxl`, and `joblib`.

## Usage

1. Download or clone the repository.
2. Install the required Python libraries.
3. Open the Jupyter Notebook in `notebooks/`.
4. Update the file paths to match the `data/`, `model/`, and `results/` folders.
5. Run the relevant notebook cells with the required input datasets.

The original HAWK imagery may need to be obtained separately from the IRIDE Earth Observation marketplace to reproduce the complete classification workflow.

## Data Sources

- **HAWK imagery:** IRIDE Earth Observation programme, 27 July 2026.
- **Historical shoreline observations:** ISPRA, 1950–2020.
- **Reference shoreline:** Independent photo interpretation of the HAWK image.
- **Training reference:** Natural Earth 1:10m land polygons.

## Research Purpose

This repository supports reproducible shoreline extraction and multi-decadal coastal-change analysis by combining machine learning, high-resolution satellite imagery, and historical shoreline observations.
