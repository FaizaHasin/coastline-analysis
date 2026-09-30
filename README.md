# Shoreline Change Analysis with Python

This Jupyter Notebook provides a complete workflow for analyzing and visualizing shoreline change data. It begins with a simple Python check, then processes multiple datasets of transect data, calculating key metrics like Net Shoreline Movement (NSM) and End Point Rate (EPR), and generating insightful plots to understand coastal erosion and accretion patterns over time.

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
