# NASA CMAPSS - Turbofan Engine RUL Prediction

Predicting Remaining Useful Life (RUL) of aircraft engines using the NASA CMAPSS FD001 dataset.

## Overview
Built a Random Forest regression model achieving RMSE of 41.38 cycles. Analysis includes EDA, feature importance, and actual vs predicted visualization.

## Dataset
NASA Commercial Modular Aero-Propulsion System Simulation (CMAPSS) - FD001 subset.
100 engines, 20,631 operating cycles, 21 sensor measurements.

## Key Finding
Sensor 11 (bypass ratio) is the most important predictor at 40% feature importance.

## Tools Used
Python, Pandas, NumPy, Scikit-learn, Matplotlib