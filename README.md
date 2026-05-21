# Weather Trend Forecasting and Global Climate Analysis

A comprehensive weather analytics and forecasting framework built on the **Global Weather Repository** dataset.

This project covers the complete workflow from **data preprocessing, exploratory analysis, trend analysis, correlation analysis, forecasting, hybrid prediction models, geographic visualization, to climate clustering**, aiming to understand global weather dynamics and improve long-horizon temperature forecasting.

The code is run in Google Colab environment and is trained using CPU or L4 GPU.

---

## Project Highlights

### Data Processing
- Missing value auditing and repair pipeline
- Outlier detection combining:
  - Physical constraints
  - IQR
  - Z-score
  - Isolation Forest
  - Temporal continuity analysis

---

### Trend Analysis

Multi-scale temporal analysis including:

- Gaussian kernel smoothing
- STL decomposition
- FFT spectral analysis
- Continuous Wavelet Transform (Morlet CWT)

Extracted:

- Long-term trends
- Seasonal patterns
- Dominant frequencies
- Time-frequency behaviors

---

### Correlation Analysis

Basic correlation:

- Pearson Correlation
- Spearman Correlation
- Mutual Information
- Distance Correlation
- Cross-correlation

Advanced correlation:

- Transfer Entropy
- Dynamic Time Warping (DTW)
- Granger Causality
- Coherence
- Wavelet Coherence

The framework jointly characterizes:

- Linear dependence
- Monotonic dependence
- Nonlinear dependence
- Lagged relationships
- Directional information flow
- Frequency-domain coupling

---

## Forecasting Models

### Classical Models

- SARIMAX
- Kalman Filter
- VAR

### Machine Learning

- XGBoost
- LightGBM

### Deep Learning

- LSTM
- Temporal Fusion Transformer (TFT)

Input variables:

Main input:

- temperature_celsius

High-weight auxiliary inputs:

- STL trend
- STL seasonal

Low-weight auxiliary inputs:

- Gaussian(7)
- Gaussian(30)
- humidity
- pressure_mb
- uv_index
- cloud

---

## Hybrid Forecasting Framework

Final model:

Temperature = Trend + Seasonal + Residual

Trend:

N-BEATS

Seasonal:

SARIMAX

Residual correction:

XGBoost

Final model:

Final = N-BEATS + SARIMAX + XGBoost

Performance:

| Horizon | MAE (°C) | RMSE | R² |
|----------|----------|------|------|
| 20-step | 1.73 | 2.57 | 0.957 |
| 100-step | 1.77 | 2.51 | 0.947 |

Average prediction error:

≈ **1.7°C**

---

## Geographic Analysis

Global spatial analysis:

- Temperature distribution
- Precipitation distribution
- Wind speed
- Humidity
- PM2.5

Generated:

- Global contour maps
- Variability maps
- Extreme-location rankings

---

## Climate Clustering

Climate feature extraction:

- Statistical descriptors
- Entropy metrics
- Wavelet metrics
- STL metrics
- FFT metrics
- Inter-variable correlations

Dimension reduction:

- PCA (202 → 36)

Visualization:

- UMAP (2D / 3D)

Clustering:

- HDBSCAN
- Gaussian Mixture Model (GMM)

Result:

Automatic machine-learning climate classification for global cities.

---

## Project Structure

```text
Weather-Trend-Forecasting/

├── notebooks/
│   ├── preprocessing.ipynb
│   ├── trend_analysis.ipynb
│   ├── correlation_analysis.ipynb
│   ├── forecasting_single.ipynb
│   ├── forecasting_hybrid.ipynb
│   ├── geographic_analysis.ipynb
│   └── climate_clustering.ipynb

├── figures/

├── results/

└── README.md
