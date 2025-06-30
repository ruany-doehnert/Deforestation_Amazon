# Deforestation Amazon
🌳 Deforestation Prediction using Machine Learning
This project applies supervised machine learning techniques to predict areas at risk of deforestation in the Amazon rainforest. The goal is to use spatial and environmental data to proactively identify regions likely to be deforested in the near future, helping support conservation and policy decision-making.

🔍 Objective
To build a classification model that predicts whether a given geographical area is at risk of deforestation, based on historical land use, satellite data, proximity to roads, and environmental factors.

🌱 Motivation
Deforestation in the Amazon has a critical impact on biodiversity, climate change, and local communities. By using Machine Learning, we can create tools to support early detection and prevention strategies, contributing to sustainable development and environmental protection.

📦 Datasets Used
PRODES / INPE – Brazilian government satellite monitoring of deforestation
https://terrabrasilis.dpi.inpe.br/download/

MapBiomas – Annual land cover and land use maps for Brazil
https://mapbiomas.org/

OpenStreetMap – Road network data for proximity features
https://www.openstreetmap.org/

🧠 ML Approach
Preprocessing: spatial data cleaning, encoding features like land cover type, proximity to roads, historical trends

Modeling: trained classification models (Random Forest, XGBoost, etc.)

Evaluation: accuracy, F1-score, and spatial visualization of predictions

🛠️ Tech Stack
Python (Pandas, Scikit-learn, GeoPandas, Matplotlib)

Jupyter Notebooks

QGIS / Folium for mapping

GitHub for version control

📈 Results
The model achieved an accuracy of XX% on test data

Prediction maps highlight high-risk deforestation zones with strong spatial patterns

🌍 Impact
This project demonstrates how data science and machine learning can be applied to environmental protection. The methodology can be extended to other biomes or conservation problems and can assist NGOs, researchers, or public agencies in identifying areas of concern more efficiently.

Some files sourcee:
1. Dado principal (label / target):
Incremento anual no desmatamento - Shapefile (2008/2023)
→ Esse arquivo mostra onde e quando houve novo desmatamento a cada ano.
Ele será usado como target (rótulo): desmatado (sim/não) por ano.

2. Dados espaciais que ajudam como variáveis explicativas (features)
Hidrografia - Shapefile
→ Distância de rios pode influenciar acesso à área e probabilidade de desmatamento.

✅ Não floresta - Shapefile
→ Útil para filtrar áreas que não são floresta, e focar só no que pode ser desmatado.

✅ PRODES completo em formato vetorial - GeoPackage (2007-2023)
→ Mais detalhado e completo; você pode extrair todas as áreas de floresta existentes, não só os incrementos.

✅ Máscara de área acumulada de supressão da vegetação nativa - Shapefile (2007)
→ Mostra tudo que já foi desmatado até 2007. Pode ser útil para comparar áreas novas vs antigas.

Global Forest Watch API (WRI)
Dados globais de desmatamento (GLAD alerts, perda de cobertura florestal)

Link: https://data.globalforestwatch.org/

API: https://developers.globalforestwatch.org/

website: https://resourcewatch.org/

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

Notebook 1: Data sourcing, feature engineering, and export.
Notebook 2: Model training, evaluation, and visualization.
Notebook 3 (optional): Time-series analysis or prediction for future years.

