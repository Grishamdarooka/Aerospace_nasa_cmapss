# Turbofan Engine Degradation Analysis — NASA C-MAPSS

A Python project for exploring and analysing turbofan engine degradation data 
using the NASA C-MAPSS dataset, as part of a broader machine learning pipeline 
for the remaining useful life (RUL) prediction.

## Current Progress
This project is currently in the data exploration and preprocessing stage. 
The focus so far has been on understanding the structure of the dataset, 
analysing sensor behaviour across engines, and filtering engines based on 
operational cycle thresholds.

## Dataset
- Source: NASA Ames Prognostics Data Repository
- Subset used: FD001
- Each row contains an engine ID, cycle number, three operational settings, 
  and 21 sensor measurements

## What the Script Does
- Loads and parses the raw C-MAPSS text file into a structured dataframe
- Computes per-engine sensor statistics (e.g., mean of sensor 2)
- Identifies engines that ran for 200 or more cycles
- Filters the dataset down to those engines for further analysis

## Requirements
- Python 3.8 or later
- pandas
- numpy

Install dependencies with:

` `` `
pip install pandas numpy
` `` `

## Usage
1. Download the C-MAPSS dataset from the NASA Ames Prognostics Data Repository
2. Update the file path in the script to point to your local copy of train_FD001.txt
3. Run the script in VS Code or any Python environment

## Author
Grisham Darooka
