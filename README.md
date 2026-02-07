# Time Series Forecasting with Deep Learning and Explainability

This project focuses on **multivariate time series forecasting** using deep learning models with an emphasis on **model interpretability, robust validation, and qualitative analysis**.  
It is designed to avoid black-box modeling by explicitly explaining *how* and *why* predictions are made.


## Project Objectives

Build deep learning models for time series forecasting  
Compare performance with a classical **SARIMAX baseline**
Apply **Explainable AI (XAI)** techniques to interpret model predictions  
Use **walk-forward cross-validation** instead of a single train/test split  
Provide detailed **architectural, validation, and qualitative analysis**


## Models Implemented

LSTM-based forecasting model  
Attention-based (Transformer-inspired) model  
SARIMAX statistical baseline  



## Model Explainability

To ensure interpretability, the project incorporates **Explainable AI techniques**:

### SHAP (SHapley Additive Explanations)

Measures feature contribution to each prediction  
Identifies dominant input features across forecasting horizons  
Helps explain model behavior beyond accuracy metrics  

Explainability is used not only for visualization but also for **model validation and error analysis**.


## Validation Strategy

### Walk-Forward Cross-Validation

Instead of a single train/test split, the project applies:

Expanding training windows  
Sequential evaluation on future time steps  
Multiple validation folds  

This approach simulates real-world forecasting scenarios and reduces data leakage.



## Baseline Comparison (SARIMAX)

SARIMAX is used as a **classical baseline model**
Forecasts are aligned carefully with deep learning outputs
Feature-level limitations of SARIMAX on multivariate data are explicitly discussed
Evaluation is performed using identical metrics for fair comparison



## Transformer Architecture Discussion

A simplified attention-based architecture is implemented  
Attention weights are analyzed to understand temporal focus  
Architectural trade-offs and limitations are documented  

Note: This is not a full encoder-decoder Transformer; limitations are acknowledged and justified.



## Evaluation Metrics

Mean Absolute Error (MAE)  
Root Mean Squared Error (RMSE)  
Forecast vs actual visualization  

Results are reported **across validation folds**, not from a single split.


## Qualitative Analysis

The project includes:
Justification of architectural choices  
Interpretation of prediction errors  
Explainability-driven insights from SHAP outputs  
Comparative strengths and weaknesses of each model  

Code is accompanied by **markdown analysis**, not standalone scripts.
