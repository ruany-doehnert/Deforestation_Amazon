# Amazon Deforestation Prediction with Machine Learning

This project demonstrates a complete workflow for predicting and analyzing Amazon deforestation using remote sensing data, Google Earth Engine, and machine learning in Python.

---

Author: Ruany Doehnert
Date: July 2025

This notebook extracts and processes satellite imagery features for 
Amazon deforestation prediction using Google Earth Engine.

## 🚀 Project Overview

The goal of this project is to build a machine learning model that can classify forest and non-forest areas in the Amazon, and use it to analyze and predict future deforestation scenarios. The workflow includes:

- **Data sourcing and feature engineering** using Google Earth Engine (GEE)
- **Label creation** based on tree cover thresholds
- **Model training** with scikit-learn
- **Time-series scenario analysis** for future predictions
- **Visualization** of results and trends

---

## 🌱 Motivation
Deforestation in the Amazon has a critical impact on biodiversity, climate change, and local communities. By using Machine Learning, we can create tools to support early detection and prevention strategies, contributing to sustainable development and environmental protection.

## 📦 Data Sources

- **Hansen Global Forest Change v1.10**  
  [`UMD/hansen/global_forest_change_2022_v1_10`](https://developers.google.com/earth-engine/datasets/catalog/UMD_hansen_global_forest_change_2022_v1_10)
- **Landsat 8 Surface Reflectance**  
  [`LANDSAT/LC08/C02/T1_L2`](https://developers.google.com/earth-engine/datasets/catalog/LANDSAT_LC08_C02_T1_L2)
- **SRTM Elevation**  
  [`USGS/SRTMGL1_003`](https://developers.google.com/earth-engine/datasets/catalog/USGS_SRTMGL1_003)

---

## 📝 Data Preparation (Notebook 1)

- Authenticate and initialize GEE.
- Define a region of interest in the Amazon.
- Extract features:  
  - **Tree cover (2000)**
  - **NDVI** (Normalized Difference Vegetation Index)
  - **NBR** (Normalized Burn Ratio)
  - **Elevation**
- Sample 2,000 points in the region at 30m resolution.
- Create binary labels:  
  - `1` = forest (`treecover > 30`)
  - `0` = non-forest
- Export the dataset as CSV to Google Drive.
  
---

## 🤖 Model Training & Evaluation (Notebook 2)

- Load the exported dataset.
- Handle class imbalance (downsampling/upsampling).
- Train a Random Forest classifier using `treecover`, `NDVI`, `NBR`, and `elevation`.
- Evaluate with accuracy, confusion matrix, and classification report.
- Save the trained model and predictions to Google Drive.

---

## 📈 Time-Series & Scenario Analysis (Notebook 3)

- Project features into the future using linear regression or scenario modeling.
- Predict forest/non-forest for each year up to 2028.
- Visualize predicted forest area trends over time.
- Save future predictions for further analysis.

---

## 🖼️ Example Results

- **Confusion matrix** and classification report for model evaluation.
- **Bar and line charts** showing predicted forest area percentage over time.

---

## 💡 Next Steps & Improvements

- Incorporate more features (e.g., texture, proximity to roads).
- Use real or scenario-based land use change rates for future projections.
- Expand region of interest and increase sample size.
- Experiment with other ML algorithms and hyperparameter tuning.

---

## 📚 License & Acknowledgments

- Data sources are publicly available via Google Earth Engine.
- Project for educational and research purposes.

---

**Feel free to fork, use, and improve this project!  
Questions or suggestions? Open an issue or connect with me on [LinkedIn](https://www.linkedin.com/).**

🌍 Impact
This project demonstrates how data science and machine learning can be applied to environmental protection. 
The methodology can be extended to other biomes or conservation problems and can assist NGOs, researchers, or public agencies in identifying areas of concern more efficiently.

Google Earth Engine:
https://developers.google.com/earth-engine/guides/getstarted

#### Alternative and Additional Datasets
Global Forest Change (Hansen et al.)
UMD/hansen/global_forest_change_2022_v1_10
Contains annual forest loss/gain, tree cover, and more. Useful for labeling and validation.

PRODES (INPE Amazon Deforestation Monitoring)
projects/mapbiomas-workspace/AUX_MATRIZ/PRODES_2022
Official Brazilian deforestation data, great for ground truth.

MapBiomas Land Cover & Use
projects/mapbiomas-workspace/public/collection7/mapbiomas_collection70_integration_v1
Annual land cover/use maps for Brazil, can help with multi-class classification (e.g., pasture, agriculture, forest).

Sentinel-2 Imagery
COPERNICUS/S2_SR
Higher resolution (10m), useful for more detailed features or smaller clearings.

MODIS Vegetation Indices
MODIS/006/MOD13Q1
For time-series analysis and trend detection.

---

Notebook 1 (data_source): Data sourcing, feature engineering, and export.
Notebook 2 (ml_amazon_model_28): Model training, evaluation, and visualization.
Notebook 3 (time_series_analysis): Time-series analysis or prediction for future years.

