# 🌍 Global Agricultural Production & Unsupervised Machine Learning Analysis (FAOSTAT)

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![GeoPandas](https://img.shields.io/badge/GeoPandas-Spatial Analysis-green.svg)](https://geopandas.org/)
[![Scikit-Learn](https://img.shields.io/badge/scikit--learn-Machine%20Learning-orange.svg)](https://scikit-learn.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## 📌 Project Overview
This project delivers an end-to-end Data Science and Unsupervised Machine Learning workflow analyzing country-level agricultural statistics from the **UN Food and Agriculture Organization (FAOSTAT)**. 

The study transitions from spatial commodity diagnostics (**Olive & Maize production**) to multidimensional country segmentation using **K-Means Clustering** and **Principal Component Analysis (PCA)**. A core highlight of this project is demonstrating how **Feature Engineering (`np.log1p`)** resolves extreme scale skewness in spatial clustering.

---

## 📊 Key Highlights & Analytical Journey

### 1. Spatial Choropleth Mapping
* **Olive Production (2021):** Visualized extreme spatial clustering around the Mediterranean basin, highlighting Spain as a major global outlier (>8,000 kT).
* **Maize Yield (2023):** Mapped global land productivity ($kg/ha$), identifying yield hotspots in the US Corn Belt, Southern Europe, and irrigated valleys in Central Asia (Tajikistan).

### 2. Machine Learning: The "Scale Dominance" Paradox
* **Raw Feature Clustering:** Running K-Means on raw harvested area (`Total_Area_ha`) caused Euclidean distance metrics to be dominated by multi-million hectare land outliers (USA, China, India, Brazil), isolating them into an exclusive 4-country cluster.
* **Log-Transformation Optimization (`np.log1p`):** Compressing arable land variance allowed **crop portfolio diversity** and **yield efficiency** to participate equally in clustering distance calculations.

### 3. Final Global Rural Clusters (Log-Transformed)
* **🟢 Cluster 2 (Diversified Core & Superpowers - 123 Countries):** Agrarian superpowers and diversified mid-scale producers (e.g., France, Spain, Greece) sharing broad crop portfolios ($\sim67\text{ unique crops}$).
* **🔴 Cluster 0 (Intensive High-Yield Outliers - 15 Countries):** Specialized economies (e.g., UAE, Norway) overcoming geographic/climatic constraints via extreme yield maximization ($\sim42,357\text{ kg/ha}$).
* **🔵 Cluster 1 (Small-Scale / Constrained Economies - 61 Countries):** Economies constrained by arable land or development (e.g., Afghanistan), exhibiting lower diversity ($\sim29\text{ crops}$) and higher supply chain exposure.

---

## 🛠️ Tech Stack & Libraries
* **Data Processing:** `pandas`, `numpy`
* **Machine Learning:** `scikit-learn` (`StandardScaler`, `KMeans`, `PCA`)
* **Spatial & GIS:** `geopandas`, `shapely`
* **Data Visualization:** `matplotlib`, `seaborn`

---

## 📁 Repository Structure
```text
├── data/                       # Dataset directory (FAOSTAT CSVs & Shapefiles)
├── notebooks/
│   └── faostat_agricultural_analysis.ipynb   # Main Jupyter/Kaggle Notebook
├── outputs/                    # Generated maps & exported plots (.png)
├── README.md                   # Project documentation
└── requirements.txt            # Python dependencies
