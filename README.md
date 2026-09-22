# Urban Air Quality Analysis and Pollution Level Prediction Using Machine Learning

## Project Overview

This project analyzes air-quality measurements collected from monitoring stations across India. It performs data cleaning, exploratory data analysis, visualization, pollutant relationship analysis, and machine-learning-based prediction of PM2.5 levels.

The project uses a CPCB / Open Government Data Platform India air-quality dataset.

## Objectives

1. Clean and preprocess the air-quality dataset.
2. Analyze pollutant measurements across states, cities, and monitoring stations.
3. Identify relationships between pollutant measurements.
4. Visualize important air-quality characteristics.
5. Build machine-learning models for PM2.5 prediction.
6. Compare model performance using MAE, RMSE, and R².
7. Generate data-driven insights and recommendations.

## Dataset

**Source:** Open Government Data Platform India — Real Time Air Quality Index  
**Provider:** Central Pollution Control Board (CPCB)

Dataset source:
https://www.data.gov.in/catalog/real-time-air-quality-index

The downloaded dataset contains:

- Country
- State
- City
- Monitoring station
- Last update
- Latitude
- Longitude
- Pollutant ID
- Pollutant minimum
- Pollutant maximum
- Pollutant average

The analyzed dataset contains 3,444 records, 31 states, 258 cities, and 492 monitoring stations. Seven pollutant categories are present: CO, NH3, NO2, OZONE, PM10, PM2.5, and SO2.

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook / Google Colab

## Project Workflow

Dataset  
↓  
Data inspection  
↓  
Data cleaning  
↓  
Exploratory data analysis  
↓  
Visualization  
↓  
Station-level dataset creation  
↓  
PM2.5 prediction  
↓  
Model evaluation  
↓  
Insights and recommendations

## Data Preprocessing

The project checks:

- Dataset dimensions
- Data types
- Missing values
- Duplicate records
- Negative pollutant measurements
- Date/time validity

Rows with missing `pollutant_avg` values are removed rather than replacing missing measurements with zero.

After cleaning, 3,115 records remain.

## Exploratory Data Analysis

The analysis includes:

- Pollutant-wise descriptive statistics
- Pollutant measurement distributions
- State-level measurement coverage
- Average PM2.5 by state
- Average PM2.5 by city
- PM2.5 versus PM10 comparison
- Pollutant correlation analysis

Important results from the analyzed snapshot:

- PM10 has the highest average reported value: 77.65.
- NH3 has the lowest average reported value: 4.78.
- Delhi has the highest state-level average PM2.5 measurement in this snapshot: 145.24.
- Manesar has the highest city-level average PM2.5 measurement in this snapshot: 272.00.
- PM10 and PM2.5 have the strongest pollutant correlation: 0.85.
- 355 of 492 stations have complete measurements for all seven pollutant categories.

## Machine Learning

PM2.5 is used as the prediction target.

### Input Features

- PM10
- NO2
- SO2
- CO
- OZONE
- NH3
- Latitude
- Longitude

Only complete station-level observations are used for this multi-pollutant model. This produces 355 machine-learning observations.

### Models

Three regression models are evaluated:

1. Linear Regression
2. Decision Tree Regressor
3. Random Forest Regressor

## Model Results

| Model | MAE | RMSE | R² |
|---|---:|---:|---:|
| Linear Regression | 20.223 | 29.165 | 0.751 |
| Decision Tree | 24.125 | 33.764 | 0.666 |
| Random Forest | 19.303 | 27.167 | 0.784 |

Random Forest produced the highest R² and the lowest MAE and RMSE among the three models tested in this project.

## Random Forest Feature Importance

The recorded feature-importance values were:

| Feature | Importance |
|---|---:|
| PM10 | 0.7475 |
| Latitude | 0.0781 |
| Longitude | 0.0411 |
| CO | 0.0329 |
| OZONE | 0.0294 |
| SO2 | 0.0291 |
| NO2 | 0.0211 |
| NH3 | 0.0207 |

These values describe the contribution of features within the trained Random Forest model; they should not be interpreted as proof of causation.

## How to Run

### 1. Install dependencies

```bash
pip install -r requirements.txt
```

### 2. Open the notebook

Open:

`Rokkam_PoojithaKumari_AirQuality_Project.ipynb`

The notebook was developed for Google Colab and includes a file-upload step for the CSV dataset.

### 3. Upload the dataset

Run the dataset-upload cell and select the downloaded CPCB air-quality CSV.

### 4. Run the notebook

Execute the cells from beginning to end.

## Output Files

The notebook generates:

- `model_comparison_results.csv`
- `pollutant_statistics.csv`
- `pm25_machine_learning_dataset.csv`

## Limitations

- The dataset represents a particular monitoring snapshot rather than a long historical time series.
- Not every station contains measurements for every pollutant.
- The dataset does not directly contain an AQI column.
- The PM2.5 model does not include weather, traffic, or industrial-activity variables.
- Correlation represents statistical association and does not establish causation.
- Snapshot results should not be interpreted as permanent rankings of cities or states.

## Future Scope

Future versions can include:

- Historical observations across multiple months or years
- Weather variables
- Traffic and industrial activity data
- Time-series forecasting
- Multi-pollutant prediction
- AQI calculation using applicable CPCB breakpoints
- Web-based visualization and deployment

## Author

Rokkam Poojitha Kumari
