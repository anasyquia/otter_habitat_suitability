# 🦦 Sea Otter Habitat Suitability Modeling  
**Neural Network Classification Using Multi-Source Geospatial Data**

---

## Project Overview  

Designed and trained a neural network to predict sea otter habitat suitability along the Central California coast using integrated satellite oceanographic data and species observations.

This project demonstrates end-to-end machine learning development: geospatial data engineering, model design, regularization, threshold tuning, and interpretability.

---

## Problem  

Given environmental raster data and observed otter sightings, predict whether a coastal pixel represents suitable habitat.

Framed as a binary classification problem at the pixel level.

---

## Data Engineering  

Integrated and aligned multi-source datasets (2002–present):

- GBIF sea otter sightings → binary presence target  
- Sea Surface Temperature (~1 km resolution)  
- Chlorophyll-a (~1.4 km resolution)  
- Bathymetry (~30 m resolution)  
- Kelp biomass (~30 m resolution)  

Key steps:
- Raster alignment and spatial resampling  
- Marine masking and domain filtering  
- Feature extraction at pixel level  
- Train/test split with stratification  
- Standardization of input features  

---

## Modeling Approach  

### Neural Network Architecture
- 4 input features  
- Hidden layers: 64 → 32 → 16 neurons  
- Dropout at each layer  
- L2 regularization  
- Early stopping  
- Learning rate scheduling  

Optimized probability threshold (0.3) to maximize recall for domain-specific objectives.

---

## Performance  

- **94.7% Accuracy**  
- **99.3% Recall**  
- **98.5% ROC-AUC**  

High recall was intentionally prioritized to reduce false negatives.

---

## Model Interpretation  

Used SHAP to quantify feature importance and understand nonlinear effects.

Key drivers:
- Chlorophyll concentration (strongest predictor)  
- Bathymetry  
- Sea Surface Temperature  
- Kelp biomass  

---

## Technical Stack  

Python · NumPy · Pandas · Xarray · Scikit-learn · TensorFlow/Keras · SHAP · Matplotlib · Seaborn · Cartopy · SciPy  

---

## Skills Demonstrated  

- Geospatial ML pipeline development  
- Multi-source data integration  
- Neural network architecture design  
- Regularization and overfitting control  
- Threshold tuning for domain-specific objectives  
- Model evaluation and interpretability  
