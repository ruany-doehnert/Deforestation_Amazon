# Deforestation_Amazon
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
