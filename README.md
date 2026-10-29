# Shoreline Change Analysis with Python

This Jupyter Notebook (Metaponto Coastaline Analysis) provides a complete workflow for analyzing and visualizing shoreline change data. It begins with a simple Python check, then processes multiple datasets of transect data, calculating key metrics like Net Shoreline Movement (NSM) and End Point Rate (EPR), and generating insightful plots to understand coastal erosion and accretion patterns over time. The photo interpretation results are in the file Results_Metaponto_CommonTransects_1950_2026_Final,the files from ISPRA are three TRANS_17_intersect files for 1950,2000,2006 and 2020 while the original 144 digitilized photointerpretation points are in the PhotoInterpreted_shoreline_20260727_EPSG32633 file. The corner coordinates file (Metaponto_HAWK_27_July_2026_Corner_Coordinates) is the detailed file based on the 27july image from the HAWK study which we used in this study as a primary source  dataset. The file (CommonTransects_1950_2026.csv) contains shoreline positions and change statistics for 121 common coastal transects within the approximately 12-km HAWK study area at Metaponto, Italy. It integrates historical ISPRA shoreline observations (1950, 2000, 2006, and 2020) with the Random Forest (RF)-derived shoreline from 2026 HAWK imagery.The file includes shoreline coordinates, Net Shoreline Movement (NSM), End Point Rate (EPR), Linear Regression Rate (LRR), and RF–manual shoreline positional differences for 120 validated transects.Related manuscript outputs: Figures 17–19 and Table 2. The dataset supports the assessment of recent and long-term shoreline change and the positional validation of the RF-extracted shoreline.

**Key Features**

*   **Python Environment Check:** A simple initial script to verify that the Python environment is set up correctly.
*   **Automated Data Processing:** The notebook automatically finds and processes multiple data files from a specified directory.
*   **Shoreline Change Metrics:** It calculates the Net Shoreline Movement (NSM) and End Point Rate (EPR) for hundreds of transects across different time periods.
*   **Multi-Panel Visualizations:** It generates detailed, six-panel figures for each dataset.
*   **Summary Statistics:** For each dataset, the notebook prints the mean NSM and EPR, summarizing the overall trend of the data.

**Visualizations Included**

For each dataset, the six-panel plots include:
*   Histograms of **NSM** and **EPR** values.
*   A scatter plot of **EPR vs. NSM**.
*   Histograms of the **uncertainty** associated with NSM and EPR.
*   A time-series plot showing the **shoreline position over time** for a single, randomly selected transect.

**Dependencies**

To run this notebook,  will need the following Python libraries:
*   **Python 3.x**
*   **pandas** (for data manipulation and reading Excel files)
*   **numpy** (for numerical operations)
*   **matplotlib** (for creating visualizations)
*   **openpyxl** (engine required by pandas to read `.xlsx` files)
*   * **scikit-image** (specifically `skimage.morphology` for cleaning binary masks, removing noise, and refining shoreline boundaries)
You can install them using pip:
`pip install pandas numpy matplotlib openpyxl jupyterlab`
