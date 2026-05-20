# NASA CMAPSS - Turbofan Engine RUL Prediction

Predicting Remaining Useful Life (RUL) of aircraft engines using the NASA CMAPSS FD001 dataset.

## Overview
Comprehensive ML project comparing multiple models for RUL prediction on turbofan engine sensor data. Includes exploratory data analysis, feature selection, hyperparameter tuning, and deep learning.

## Dataset
NASA Commercial Modular Aero-Propulsion System Simulation (CMAPSS) - FD001
- 100 engines, 20,631 operating cycles
- 21 sensor measurements per cycle
- Single operating condition, single fault mode

## Results

| Model | RMSE |
|-------|------|
| Random Forest (baseline) | 41.38 |
| XGBoost (baseline) | 43.37 |
| Random Forest (tuned, 200 trees, depth 10) | 41.09 |
| Random Forest (capped RUL at 125)  | **18.59** |
| XGBoost (capped RUL at 125) | 19.89 |
| LSTM (PyTorch, 2 layers, hidden 128) | 41.89 |

## Key Findings
- Capping RUL at 125 cycles reduced RMSE by 55% — early life engine behaviour is similar across engines making high RUL values noisy targets
- Sensor 11 (bypass ratio) is the most important predictor at ~40% importance in both RF and XGBoost
- Removing 7 low-importance sensors (1, 5, 6, 10, 16, 18, 19) had negligible effect on accuracy
- Random Forest outperformed LSTM on FD001 — consistent with research findings that simpler single-condition datasets don't always benefit from sequential models

## Project Structure
- **EDA** — data loading, sensor analysis, cycle distribution
- **RUL Calculation** — sliding window target engineering
- **Feature Selection** — importance analysis across RF and XGBoost
- **Model Comparison** — RF, XGBoost, LSTM with hyperparameter tuning
- **Streamlit App** — interactive RUL predictor (coming soon)

## Tools Used
Python, Pandas, NumPy, Scikit-learn, XGBoost, PyTorch, Matplotlib

## Author
Grisham Darooka, M.Tech Aerospace Engineering, IIT Bombay