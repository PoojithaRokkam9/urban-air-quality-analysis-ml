# Urban Air Quality Analysis and Pollution Level Prediction Using Machine Learning

## Project Overview

This project focuses on analyzing air quality data collected from different locations in India and predicting PM2.5 (Particulate Matter 2.5) levels using machine learning.

The project has two main parts:
1. Analysis of air quality data using Python to identify pollution patterns and relationships between different pollutants.
2. Prediction of PM2.5 levels using machine learning models.

## Objectives

- Analyze air quality measurements from different states, cities, and monitoring stations.
- Study the reported values of pollutants such as PM2.5, PM10, NO2, SO2, CO, O3, and NH3.
- Compare PM2.5 levels across different states and cities.
- Study the correlation between different pollutants.
- Build and compare machine learning models for PM2.5 prediction.
- Evaluate the models using MAE, RMSE, and R².

## Dataset

The dataset is obtained from the Government of India's Open Government Data Platform and is based on CPCB air quality data.

Dataset source:
https://www.data.gov.in/catalog/real-time-air-quality-index

The dataset contains information such as state, city, monitoring station, location coordinates, pollutant type, and reported minimum, maximum, and average values.

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Google Colab / Jupyter Notebook

## Machine Learning

PM2.5 is used as the target variable.

The following regression models are implemented and compared:

- Linear Regression
- Decision Tree Regressor
- Random Forest Regressor

The models are evaluated using:

- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)
- R² Score

## Project Files

- `Rokkam_PoojithaKumari_UrbanAirQualityAnalysis.ipynb` - Complete project code, analysis, visualizations, and machine learning implementation.
- `requirements.txt` - Python libraries required to run the project.
- `Rokkam_PoojithaKumari_ProjectReport.docx` - Detailed project report.
- `README.md` - Project overview and instructions.

## How to Run

The project can be opened using Google Colab or Jupyter Notebook.

1. Open the `.ipynb` file.
2. Install the required Python libraries using `requirements.txt`.
3. Run the notebook cells in order.
4. The data analysis, visualizations, model training, evaluation, and prediction results will be generated.

## Result

Three machine learning models were compared for PM2.5 prediction. Among the tested models, Random Forest Regressor achieved the highest R² score in this project.

## Prepared by

Rokkam Poojitha Kumari
