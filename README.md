# Real Estate Dataset — Preparation & Cleaning

## Overview
This notebook covers the full data preparation pipeline for a real estate dataset, from initial inspection through cleaning, preprocessing, and dimensionality reduction via PCA.


## How to Run

### 1. Open Google Colab
Go to [colab.research.google.com](https://colab.research.google.com) and open the notebook by either:

### 2. Upload the Dataset
Once the notebook is open, upload `data.csv` into files

### 3. Run the Notebook
Click **Runtime → Run all** to execute all cells in order.


## Steps

### 1. Data Loading & Inspection
The dataset is loaded from `data.csv` using pandas. Initial exploration includes viewing the first rows, checking column types with `.info()`, and checking the overall shape of the data.

### 2. Data Quality Checks
Three quality checks are performed:
- **Null values** — counts missing values across all columns.
- **Invalid values** — detects `-1` entries, which are treated as sentinel values for missing data.
- **Duplicates** — counts duplicate rows.

### 3. Data Cleaning
- All `-1` values are replaced with `NaN`.
- Rows containing any null values are dropped.
- Duplicate rows are removed, keeping the first occurrence.

### 4. Preprocessing
- Non-numeric columns (categorical/type columns) are dropped, keeping only numerical features.
- The `price` column is removed from the feature set (used as target).
- Features are standardized using `StandardScaler` (zero mean, unit variance).

### 5. Dimensionality Reduction (PCA)
Principal Component Analysis is applied to the scaled data:
- Explained variance per component is computed and summarized in a table.
- A **Scree Plot** is generated to visualize eigenvalues and apply Kaiser's criterion (keep components with eigenvalue > 1).
- **Variable contribution bar charts** show how each feature loads onto the first two principal components.
- **Individual projection scatter plots** display data points in the PC1–PC2 space, colored by city.
- A **correlation circle** visualizes variable correlations with the principal components.

---


