# Airbnb Price Prediction ML

An end-to-end machine learning application that predicts the nightly price of an Airbnb listing using listing and location 
characteristics. The project includes data preprocessing, model training, evaluation, model serialization, and an interactive 
Streamlit application.

## Project Overview

This project was developed as an end-to-end machine learning workflow, covering:

- Dataset loading and exploration
- Data preprocessing
- Numerical feature scaling
- Categorical feature encoding
- Train/test splitting
- Ridge Regression model training
- Model evaluation
- Model serialization using Joblib
- Interactive prediction using Streamlit
- Git and GitHub version control

## Dataset

The project uses an Airbnb listings dataset containing Airbnb listing information such as location, room type, minimum nights, 
reviews, host listings, and availability.

**Dataset source:**

https://raw.githubusercontent.com/SagarChhabriya/data-science/refs/heads/main/datasets/TBD/airbnb.csv

## Features Used

The model uses the following features:

### Numerical Features

- Latitude
- Longitude
- Minimum Nights
- Number of Reviews
- Reviews Per Month
- Calculated Host Listings Count
- Availability 365

### Categorical Features

- Neighbourhood Group
- Neighbourhood
- Room Type

## Machine Learning Pipeline

The project uses a Scikit-learn Pipeline to combine preprocessing and model training into a single workflow.

### Preprocessing

- Numerical features are standardized using `StandardScaler`.
- Categorical features are converted into numerical representations using `OneHotEncoder`.
- Unknown categorical values are handled using `handle_unknown="ignore"`.

### Model

**Ridge Regression**

Ridge Regression was selected as the final model for the application.

The complete preprocessing and model pipeline is saved using Joblib so that the Streamlit application can load the trained 
model without retraining it every time.

## Model Evaluation

The trained Ridge Regression model was evaluated on the test dataset using Mean Squared Error, Root Mean Squared Error, Mean 
Absolute Error, and R² Score.

| Metric | Result |
|---|---:|
| Mean Squared Error (MSE) | 38,176.43 |
| Root Mean Squared Error (RMSE) | 195.39 |
| Mean Absolute Error (MAE) | 68.07 |
| R² Score | 0.1370 |

The saved model was successfully loaded and tested after serialization, producing predictions for 9,779 test records.

## Project Structure

```text
airbnb-price-prediction-ml/
│
├── data/
│   └── airbnb.csv
│
├── model/
│   └── airbnb_price_model.pkl
│
├── notebooks/
│   └── model_training.ipynb
│
├── app.py
├── requirements.txt
├── README.md
└── .gitignore

