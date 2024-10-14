# Delhi Climate Time Series Forecasting

This project focuses on time-series forecasting using the **Delhi Climate Dataset** obtained from Kaggle, which contains daily climate data from 1st January 2013 to 24th April 2017, collected through the Weather Underground API. The dataset includes the following attributes: `meantemp` (mean temperature), `humidity`, `wind_speed`, and `meanpressure`. The project is divided into two parts: **Univariate Time-Series Modeling** and **Multivariate Time-Series Modeling**. This README provides an overview of both parts and the methodologies applied.

## Table of Contents
1. [Project Overview](#project-overview)
2. [Dataset](#dataset)
3. [Part 1: Univariate Time-Series Modeling](#part-1-univariate-time-series-modeling)
    - Exploratory Data Analysis (EDA)
    - Modeling Approaches
4. [Part 2: Multivariate Time-Series Modeling](#part-2-multivariate-time-series-modeling)
    - Time-Series Properties
    - Modeling Approaches
5. [Conclusions](#conclusions)
6. [Requirements](#requirements)
7. [Usage](#usage)

## Project Overview

The aim of this project is to develop models that can forecast the `meantemp` attribute from the climate data. The project is split into two phases:

1. **Univariate Time-Series Modeling**: Focuses on forecasting the mean temperature (`meantemp`) using only its historical data.
2. **Multivariate Time-Series Modeling**: Predicts the `meantemp` while also taking into account additional variables like `humidity`, `wind_speed`, and `meanpressure`.

## Dataset

The **Delhi Climate Dataset** contains the following attributes:
- **meantemp**: Daily mean temperature in °C
- **humidity**: Daily average humidity in percentage
- **wind_speed**: Daily average wind speed in km/h
- **meanpressure**: Daily average atmospheric pressure in hPa

Time period: **January 1, 2013 - April 24, 2017**  
Location: **Delhi, India**

The dataset is available on Kaggle via this [link](https://www.kaggle.com/sudalairajkumar/daily-climate-time-series-data).

## Part 1: Univariate Time-Series Modeling

In this part, the focus is on predicting the `meantemp` attribute using **univariate time-series models**. The process is as follows:

### 1. Exploratory Data Analysis (EDA)
- **Univariate analysis**: Trends and seasonality in the `meantemp` data over time.
- **Bivariate analysis**: Although other attributes like `humidity`, `wind_speed`, and `meanpressure` were analyzed, they were not used in this phase of forecasting.

### 2. Modeling Approaches
- **Auto-Regressive (AR) Model**: Models `meantemp` based on its past values.
- **Seasonal Auto-Regressive Integrated Moving Average (SARIMA)**: Captures both trend and seasonal components in the data.
- **Artificial Neural Networks (ANNs)**: Non-linear model using a feedforward neural network.
- **Long Short-Term Memory (LSTM)**: A type of recurrent neural network suitable for sequential data, capturing long-term dependencies.

Hyperparameter tuning for both ANNs and LSTMs was performed using grid search to optimize the models' performance.

## Part 2: Multivariate Time-Series Modeling

This section extends the previous work by incorporating all the attributes (`meantemp`, `humidity`, `wind_speed`, and `meanpressure`) into the forecasting models to predict `meantemp`.

### 1. Time-Series Properties
Before applying models, the relevant time-series properties of each attribute (e.g., stationarity, seasonality) were studied.

### 2. Modeling Approaches
- **Vector Autoregression (VAR)**: A multivariate model that predicts multiple time-series attributes simultaneously, including `meantemp`, `humidity`, `wind_speed`, and `meanpressure`.
- **Support Vector Regression (SVR)**: A machine learning approach applied specifically for `meantemp` prediction.
- **Gradient Boosting (GB)**: Ensemble learning method to improve predictive accuracy.
- **Long Short-Term Memory (LSTM)**: This deep learning model was again utilized for multivariate forecasting due to its ability to model complex time dependencies.

## Conclusions

- **Univariate models** like SARIMA and LSTM showed the potential to capture trends and seasonal patterns in `meantemp`.
- **Multivariate models** like VAR and LSTM improved forecasting accuracy by incorporating additional climate attributes.
- Hyperparameter tuning and careful model selection significantly impacted the performance of the models.