# Sales Forecasting Pipeline

Version 1 : A complete machine learning pipeline for predicting retail sales using Random Forest regression with comprehensive data preprocessing and feature engineering. This version is not giving best results
Version 2 : A complete machine learning pipeline for predicting retail sales using AdaBoost with comprehensive data preprocessing and feature engineering.

## Overview

This project implements an end-to-end sales forecasting solution that processes multiple data sources including store information, product details, oil prices, and holiday events to predict unit sales. The pipeline uses scikit-learn's transformer architecture for reproducible and scalable preprocessing.

## Features

### Data Processing Pipeline
- **Oil Price Interpolation**: Handles missing oil price data using linear interpolation with forward/backward fill
- **Holiday Detection**: Marks dates as holidays based on events calendar
- **Store & Item Integration**: Merges store characteristics and product information
- **Date Feature Engineering**: Extracts temporal features (year, month, day, weekday, weekend indicator)

### Encoding Strategies
- **Frequency Encoding**: For high-cardinality categorical variables (city, state, family)
- **One-Hot Encoding**: For low-cardinality categorical variables (type, holiday flags, perishable indicator)

### Model
- **Random Forest Regressor**: Robust ensemble method with configurable hyperparameters
- **Performance Metrics**: MSE and R² score evaluation

## Data Requirements

The pipeline expects the following CSV files:

| File | Description |
|------|-------------|
| `train_cut.csv` | Training data with sales records |
| `stores.csv` | Store information (location, type, cluster) |
| `oil.csv` | Daily oil price data |
| `items.csv` | Product information (family, class, perishable flag) |
| `holidays_events.csv` | Holiday and event calendar |
| `cut_market_info.csv` | Combination of the above 5 data |


## Model Performance

The pipeline includes comprehensive evaluation metrics:
- **Mean Squared Error (MSE)**: Measures average squared prediction errors
- **R² Score**: Explains variance captured by the model
- **Correlation Analysis**: Visualizes feature relationships with target variable

## Performance Considerations

- **Sampling Strategy**: Uses random sampling for large datasets to improve training speed
- **Parallel Processing**: Leverages multiple CPU cores with `n_jobs=-1`
- **Memory Optimization**: Drops unnecessary columns before model training
- **Efficient Encoding**: Uses frequency encoding for high-cardinality variables

## Requirements

- Python 3.7+
- pandas >= 1.3.0
- numpy >= 1.20.0
- scikit-learn >= 1.0.0
- matplotlib >= 3.3.0
- seaborn >= 0.11.0
