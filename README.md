Multivariate Time Series Forecasting

LSTM vs Transformer vs SARIMAX

Overview

This project implements and compares multiple forecasting approaches for multivariate time series data. It evaluates deep learning architectures (LSTM and Transformer) against a classical statistical model (SARIMAX) for multi-step forecasting.

The project also integrates model explainability using Integrated Gradients to interpret feature importance.

Problem Statement

Given past observations of a multivariate time series, predict the next 10 future time steps of the primary target variable.

The system uses:

40 past time steps as input

10 future time steps as output

3 correlated features
Dataset

The dataset is synthetically generated and contains:

Trend component

Multiple seasonal patterns

Correlated multivariate Gaussian noise

Increasing variance over time (heteroscedasticity)

Features:

f1: Trend + Seasonality + Noise (Primary target)

f2: Scaled trend + Alternate seasonality + Noise

f3: Combined seasonal components + Noise

Total time steps: 1500
Notebook contains:

Data generation

Preprocessing

Model training

Evaluation

Explainability

Visualization
Methodology
1. Data Preprocessing

MinMaxScaler normalization

Supervised sequence creation

Temporal train-test split (70% train, 30% test)
2. Models Implemented
LSTM Model

Architecture:

LSTM (64 units, return_sequences=True)

Dropout (0.3)

LSTM (32 units)

Dense output layer (10 steps)

Strength:

Captures short and mid-term dependencies.
Transformer Model

Architecture:

MultiHeadAttention (4 heads)

Layer Normalization

Dropout

Dense (ReLU)

GlobalAveragePooling1D

Dense output layer (10 steps)

Strength:

Captures long-range dependencies using attention mechanism.

SARIMAX Model

Configuration:

Order: (2, 1, 2)

Seasonal Order: (1, 1, 1, 50)

Strength:

Provides strong linear statistical baseline.
Evaluation Metrics

Performance is measured using:

Mean Absolute Error (MAE)

Root Mean Squared Error (RMSE)

Metrics are calculated across all forecasted steps.

Explainability

Integrated Gradients is implemented for the LSTM model to compute feature importance.

This helps identify which input features contribute most to the model’s predictions.

Visualizations

Forecast comparison (Actual vs LSTM vs Transformer)

Feature importance bar chart
Key Insights

LSTM effectively models temporal patterns.

Transformer handles long-range dependencies.

SARIMAX provides a reliable classical benchmark.

Recent time steps show higher importance in predictions.

Model comparison increases forecasting confidence.

Future Improvements

Hyperparameter tuning

Model ensembling

Use real-world datasets

Probabilistic forecasting

Deployment using FastAPI or Flask

Cross-validation for time series
Technologies Used

Python

NumPy

Pandas

Scikit-learn

Statsmodels

TensorFlow / Keras

Matplotlib
