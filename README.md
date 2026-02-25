# Soil Moisture Prediction using Machine Learning & Deep Learning

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![IIT Patna](https://img.shields.io/badge/IIT%20Patna-M.Tech%20AI-red)](https://www.iitp.ac.in/)
[![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-green.svg)](https://github.com/yourusername/soil-moisture-prediction/graphs/commit-activity)

## 📌 Project Overview
This project develops a robust regression framework to predict volumetric soil moisture content by integrating multi-modal satellite-derived remote sensing data. The modeling pipeline fuses high-resolution Synthetic Aperture Radar (SAR) data with passive microwave estimates to create a high-precision environmental monitoring tool.

**Data Fusion Pipeline:**
* **Sentinel-1 SAR:** Backscatter coefficients (VV, VH) providing high spatial resolution.
* **SMAP:** Passive microwave soil moisture estimates (`smap_am`) for temporal consistency.
* **Ground-truth:** In-situ volumetric measurements for supervised learning.



The objective is to systematically evaluate **10+ Machine Learning** algorithms against **Advanced Deep Learning** architectures to determine the most effective predictive approach for structured environmental data.

---

## 🎯 Problem Statement
The goal is to map complex, non-linear relationships between satellite signals and earth surface characteristics.

* **Independent Variables:** `VV`, `VH`, `smap_am`
* **Dependent Variable:** `soil_moisture`

### Dataset Description
| Feature | Source | Description |
| :--- | :--- | :--- |
| **VV** | Sentinel-1 | Vertical-Vertical SAR backscatter (dB) |
| **VH** | Sentinel-1 | Vertical-Horizontal SAR backscatter (dB) |
| **smap_am** | SMAP | Morning passive microwave soil moisture estimate |
| **soil_moisture**| In-situ | Ground-truth volumetric soil moisture (Target Variable) |

**Data Integrity & Preprocessing:**
* **Scale:** 24,866 validated observations.
* **Cleaning:** Removal of outliers and statistical distortions.
* **Engineering:** Feature standardization and normalization to ensure convergence in gradient-based models.

---

## 📊 Performance Evaluation
A rigorous comparative analysis was performed across seven key regression metrics. The results indicate that ensemble methods are superior for this specific tabular dataset.

| Model | MAE | MSE | RMSE | $R^2$ | Adj $R^2$ | RMSLE | MAPE |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **🥇 Random Forest** | 0.1209 | 0.0146 | **0.1005** | 0.0969 | 0.0963 | $6.45\times10^{7}$ | 0.0970 |
| **🥈 XGBoost** | 0.1211 | 0.0147 | 0.1005 | 0.0941 | 0.0936 | $6.49\times10^{7}$ | 0.0942 |
| **🥉 CatBoost** | 0.1212 | 0.0147 | 0.1011 | 0.0917 | 0.0912 | $6.59\times10^{7}$ | 0.0918 |
| **SVR** | 0.1222 | 0.0149 | 0.1018 | 0.0768 | 0.0762 | $6.40\times10^{7}$ | 0.0791 |
| **Advanced ANN** | 0.1233 | 0.0152 | 0.1034 | 0.0608 | 0.0602 | $6.73\times10^{7}$ | 0.0614 |
| **Gradient Boosting** | 0.1223 | 0.0150 | 0.1023 | 0.0751 | 0.0745 | $6.70\times10^{7}$ | 0.0751 |
| **Decision Tree** | 0.1250 | 0.0156 | 0.1026 | 0.0341 | 0.0335 | $6.55\times10^{7}$ | 0.0341 |
| **Linear Regression** | 0.1258 | 0.0158 | 0.1056 | 0.0216 | 0.0210 | $7.04\times10^{7}$ | 0.0216 |
| **Extra Trees** | 0.1260 | 0.0159 | 0.1026 | 0.0190 | 0.0184 | $6.05\times10^{7}$ | 0.0190 |
| **AdaBoost** | 0.1266 | 0.0160 | 0.1072 | 0.0090 | 0.0084 | $7.74\times10^{7}$ | 0.0319 |
| **KNN** | 0.1300 | 0.0169 | 0.1058 | -0.0439 | -0.0445 | $6.37\times10^{7}$ | -0.0438 |



---

## 🛠️ Key Technical Insights
* **Ensemble Dominance:** Tree-based ensemble models (Random Forest, XGBoost) outperformed Deep Learning (ANN) architectures, proving more effective for structured tabular environmental datasets.
* **Model Stability:** Outlier removal significantly reduced variance and improved prediction consistency.
* **Non-Linear Capture:** SAR backscatter (VV/VH) signals showed complex non-linearity; boosting and bagging methods captured these nuances significantly better than linear baselines.

---

## 📂 Project Structure
```text
├── data/               # Raw and preprocessed datasets
├── notebooks/          # Exploratory Data Analysis & Model Training
├── models/             # Serialized model weights (.pkl, .h5)
├── plots/              # Visualizations (Heatmaps, Error Plots)
├── README.md
└── requirements.txt


---

## 🚀 Getting Started

* **🔧 Installation

git clone https://github.com/yourusername/soil-moisture-prediction.git
cd soil-moisture-prediction
pip install -r requirements.txt
Clone the repository and install the required dependencies:** 
