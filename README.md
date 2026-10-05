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
| Random Forest (baseline) | 42.21 |
| XGBoost (baseline) | 44.31 |
| Random Forest (tuned, 200 trees, depth 10) | 42.01 |
| XGBoost (tuned) | 44.45 |
| Random Forest (capped RUL at 125)  | **16.72** |
| XGBoost (capped RUL at 125) | 18.63 |
| LSTM (2 layers, hidden 64) | 42.11 |

## Key Findings
- Capping RUL at 125 cycles reduced RMSE by 60% — early life engine behaviour is similar across engines, making high RUL values noisy targets
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

## Live Demo
 [Try the RUL Predictor](https://nasarulpredict.streamlit.app/)

## Author
Grisham Darooka, M.Tech Aerospace Engineering, IIT Bombay
