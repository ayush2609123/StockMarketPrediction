# Stock Market Prediction Analysis

## StockPredictor

This project aims to predict stock price movements using advanced machine learning models. The analysis involves using data from major stock tickers and applies Random Forest and Long Short-Term Memory (LSTM) networks to forecast significant price movements and future stock prices, respectively.

---

## Table of Contents
1. [Data Collection](#data-collection)
2. [Data Preprocessing](#data-preprocessing)
    - [Percentage Change Calculation](#percentage-change-calculation)
    - [Lag Features](#lag-features)
3. [Feature Engineering](#feature-engineering)
4. [Model Training and Evaluation](#model-training-and-evaluation)
    - [Random Forest Model](#random-forest-model)
    - [LSTM Network for Price Prediction](#lstm-network-for-price-prediction)

---

## Data Collection

Data for various stock tickers is collected using the Yahoo Finance API. This dataset includes historical prices from January 2021 to the present, capturing daily opening, closing, high, low prices, and volume for each stock. This comprehensive dataset provides the foundation for our subsequent analyses.

---

## Data Preprocessing

### Percentage Change Calculation

- Daily percentage changes in the adjusted close prices are calculated to understand day-to-day volatility.
- A significant daily percentage change is defined as a movement greater than 5%. This threshold helps identify days with unusually high volatility, which are critical for predicting future price movements.

### Lag Features

- Lag features are created by shifting the significant movement indicator over a five-day period.
- These features capture temporal dependencies essential for time-series forecasting, providing insights into whether significant stock price movements in the recent past are likely to influence future movements.

---

## Feature Engineering

Lagged features of significant movements are used as predictors. This approach is based on the hypothesis that past volatility patterns can provide insights into future price behaviors, which is a common assumption in financial time-series analysis.

---

## Model Training and Evaluation

### Random Forest Model

- **Objective**: A Random Forest Classifier is trained to predict whether there will be a significant price movement on a given day.
- **Rationale**: This model was chosen for its effectiveness in handling non-linear relationships and robustness against overfitting with high-dimensional data.
- **Evaluation Metrics**: The F1 score is used to assess the model’s performance, focusing on balancing precision and recall. This metric is particularly useful for imbalanced datasets like ours, where significant movements are rare events.

### LSTM Network for Price Prediction

#### Model Setup

An LSTM network is used to predict future stock prices based on historical data. This neural network architecture is well-suited for sequential data, like stock prices, where the order of data points is crucial for accurate forecasting.

#### Scaling

Data is scaled using `MinMaxScaler` to normalize input features, ensuring that the LSTM model receives input within a scaled range, optimizing weight updates during training.

#### Training

The model is trained on historical price data, learning to predict the next day’s closing price based on patterns observed over the past 100 days. Training involves adjusting the model to recognize complex patterns in the historical price sequences.

---

## Conclusion

This project demonstrates the application of machine learning models, specifically Random Forest and LSTM, for predicting stock price movements and forecasting future stock prices. With effective data preprocessing, feature engineering, and appropriate model selection, the project provides valuable insights into significant price movements, helping in decision-making for stock market investors.

---

## Authors

- **Ayush Kushwaha , Aman Kumar , Amartya Mazumbder**

