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

---
## 🌍 Impact

This project demonstrates how data science and machine learning can be applied to environmental protection. The methodology can be extended to other biomes or conservation problems and can assist NGOs, researchers, or public agencies in identifying areas of concern more efficiently.

---

## 📦 Data Sources

### **Active in Clean Model (87.6% Accuracy):**
- **Landsat 8 Surface Reflectance** [`LANDSAT/LC08/C02/T1_L2`]
  - NDVI (Normalized Difference Vegetation Index)
  - NBR (Normalized Burn Ratio)
- **SRTM Elevation** [`USGS/SRTMGL1_003`]
  - Topographic elevation data

### **Used for Labeling Only:**
- **Hansen Global Forest Change v1.10** [`UMD/hansen/global_forest_change_2022_v1_10`]
  - Creates forest/non-forest labels (treecover > 30%)
  - Removed from features to prevent data leakage

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

- Load the exported dataset (2,000 samples from Amazon region)
- **Data Leakage Discovery**: Initial model achieved suspicious 100% accuracy
- **Problem Resolution**: Identified treecover as both feature and label source
- **Clean Model Development**: Removed treecover from features, retained for labeling
- Train Random Forest classifier using **NDVI, NBR, elevation only**
- Achieve realistic **87.6% accuracy** with excellent **90% forest recall**
- Comprehensive evaluation with confusion matrix and business-focused metrics
- Save clean model and predictions to Google Drive

### 🔍 **Data Leakage Resolution**
- **Problem**: Original model included `treecover` as both feature and label source
- **Solution**: Removed `treecover` from features, kept for labeling only  
- **Result**: Accuracy dropped from 100% (suspicious) to 87.6% (realistic)
- **Impact**: Model now generalizes properly without data leakage

---

## 📈 Time-Series & Scenario Analysis (Notebook 3)

- Project features into the future using linear regression or scenario modeling.
- Predict forest/non-forest for each year up to 2028.
- Visualize predicted forest area trends over time.
- Save future predictions for further analysis.

---

## 🎯 Key Results
| Metric | Value | Importance for Conservation |
|--------|-------|----------------------------|
| 🌳 **Forest Recall** | **90%** | 🥇 Catches 9/10 deforestation events |
| 🏞️ **Non-Forest Precision** | **89%** | 🥈 Low false alarms for teams |
| 🎯 **Overall Accuracy** | **87.6%** | 🏆 Professional grade |
| 📊 **Overfitting Gap** | **0.7%** | ✅ Excellent generalization |

- **87.6% Accuracy** with 0.7% overfitting gap
- **90% Forest Recall** - catches 9/10 deforestation events  
- **Production-ready** pipeline without data leakage
- **Portfolio-quality** code demonstrating professional ML practices

[📈 **Detailed Performance Analysis**](PERFORMANCE_ANALYSIS.md)

---

## 🌍 Business Impact

**Environmental Protection**: Model optimized for Brazil forest conservation with emphasis on early deforestation detection.

### 🎯 **Conservation Applications**
- **Early Warning System**: 90% forest recall enables rapid response to deforestation
- **Resource Optimization**: 89% precision reduces false alarms and wasted field investigations  
- **Policy Support**: Data-driven insights for environmental policy decisions
- **Carbon Monitoring**: Framework adaptable for carbon credit verification

### 💰 **Economic Value**
- **Prevention > Restoration**: Early detection costs significantly less than reforestation
- **Compliance Monitoring**: Automated tracking of environmental regulations
- **Risk Assessment**: Identify high-risk deforestation areas for targeted protection

---
## 🛠️ Technologies
Python | Google Earth Engine | Scikit-learn | Random Forest | Satellite Imagery

---

## 💡 Technical Highlights
- Fixed data leakage (treecover variable removal)
- Google Earth Engine integration
- Professional Random Forest optimization
- Brazil conservation-focused metrics

---
## 💡 Next Steps & Improvements

### 🔬 **Model Enhancement**
- [ ] **Hyperparameter Optimization**: Use GridSearchCV to fine-tune Random Forest parameters
- [ ] **Advanced Models**: Test XGBoost, LightGBM for potential performance gains  
- [ ] **Threshold Optimization**: Adjust classification threshold to maximize forest recall (target: 95%+)

### 📊 **Feature Engineering** 
- [ ] **Temporal Features**: Add seasonal patterns and time-based variables
- [ ] **Derived Indices**: Create custom vegetation indices (EVI, SAVI, MSAVI)
- [ ] **Multi-temporal Analysis**: Compare current vs historical satellite data

### 🚀 **Production Deployment**
- [ ] **Real-time Pipeline**: Build automated data processing from Google Earth Engine
- [ ] **API Development**: Create REST API for model predictions
- [ ] **Web Dashboard**: Interactive monitoring dashboard for conservationists

### 🌍 **Geographic Scaling**
- [ ] **Regional Models**: Create region-specific models (Cerrado, Atlantic Forest)
- [ ] **Cross-Border Analysis**: Extend to neighboring countries (Peru, Colombia)
- [ ] **Protected Areas Focus**: Specialized models for conservation units

> **Portfolio Focus**: Implementing 2-3 of these improvements would demonstrate both technical depth and business acumen to potential employers! 🚀


---
## 📁 Project Structure

```
amazon-deforestation-ml/
├── 📄 README.md                           # Project overview & results
├── 📊 PERFORMANCE_ANALYSIS.md             # Detailed metrics & business impact
├── 📁 notebooks/
│   ├── 01_data_source.ipynb               # Google Earth Engine data extraction
│   ├── 02_ml_amazon_model_28.ipynb        # ML pipeline & evaluation  
│   └── 03_time_series_analysis.ipynb      # Future predictions & trends
├── 📁 data/                               # Training datasets
├── 📄 requirements.txt                    # Python dependencies
└── 📄 .gitignore                          # Git ignore file
```




---

Notebook 1 (data_source): Data sourcing, feature engineering, and export.
Notebook 2 (ml_amazon_model_28): Model training, evaluation, and visualization.
Notebook 3 (time_series_analysis): Time-series analysis or prediction for future years.

---

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

## 📚 License & Acknowledgments

- Data sources are publicly available via Google Earth Engine.
- Project for educational and research purposes.

---

**🌟 Star this repo if it helped you! Feel free to fork and improve.**  
Questions or suggestions? Open an issue or connect with me on [LinkedIn](https://www.linkedin.com/in/ruany-doehnert-83092558/).**

