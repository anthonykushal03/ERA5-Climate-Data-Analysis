# ERA5 Climate Data Analysis

Two notebooks from my *Climate Data Analysis and Methods* coursework (M.Tech, IIT Hyderabad), using ERA5 monthly data.

## 1. Tropical Pacific SST EOF Analysis — `ERA5_1.ipynb`

- Analyses SST anomalies over 20°S–20°N, 120°E–80°W (1961–2020).
- Extracts and plots the first three EOFs and their principal components.
- Variance explained: EOF1 **48.93%**, EOF2 **11.42%**, EOF3 **7.95%**.
- The data are not detrended. PC3 has the strongest correlation with time (**r = 0.656**).

## 2. Hyderabad Rainfall Prediction — `ERA5_2.ipynb`

- Uses 2 m temperature, mean sea-level pressure and 850 hPa winds from a ±2° region around Hyderabad to predict monthly precipitation.
- Training period: **1940–2009**; testing period: **2010 onward**.
- Applies standardization, PCA (3 components; 96.39% variance explained) and linear regression.

| Model | Test R² | Test RMSE (mm/day) |
|---|---:|---:|
| PCA regression | 0.533 | 2.266 |
| Monthly climatology | 0.603 | 2.088 |

The monthly climatology baseline performs better than the PCA regression.

## Data and libraries

ERA5 NetCDF files are not included. Download them from the [Copernicus Climate Data Store]((https://cds.climate.copernicus.eu/datasets)) and place them in the `data/` folder structure specified in the notebooks. Update `DATA_DIR` if needed.

**Libraries:** Python, Xarray, NumPy, Pandas, Matplotlib, Cartopy and Scikit-learn.
