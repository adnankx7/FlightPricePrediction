# Flight Price Prediction

## Overview

This repository presents a comprehensive machine learning project aimed at predicting flight ticket prices. Utilizing a dataset from the 'Ease My Trip' website, this project includes rigorous data cleaning, exploratory data analysis (EDA), feature engineering, and model building using the Random Forest Regressor. The objective is to accurately forecast flight prices based on various attributes such as airline, departure and arrival times, and travel duration.

## Dataset Description

The dataset consists of the following features:

- **Airline**: The name of the airline company (categorical feature with 6 unique airlines).
- **Flight**: The flight code (categorical feature).
- **Source City**: The city from which the flight departs (categorical feature with 6 unique cities).
- **Departure Time**: Categorical feature derived by binning departure times into 6 distinct time intervals.
- **Stops**: The number of stops between the source and destination cities (categorical feature with 3 distinct values).
- **Arrival Time**: Categorical feature derived by binning arrival times into 6 distinct time intervals.
- **Destination City**: The city where the flight arrives (categorical feature with 6 unique cities).
- **Class**: Seat class (categorical feature with two distinct values: Business and Economy).
- **Duration**: The total travel duration between cities in hours (continuous feature).
- **Days Left**: Derived feature representing the number of days between booking and travel date.
- **Price**: Target variable representing the ticket price.

## Data Cleaning and Preprocessing

1. **Date and Time Parsing**:
   - Extracted day, month, and year from `Date_of_Journey`.
   - Parsed departure and arrival times into hours and minutes.

2. **Handling Missing Values**:
   - Addressed missing values in `Total_Stops` by mapping categorical values and filling with mode.

3. **Feature Transformation**:
   - Converted travel `Duration` into separate `Duration_hour` and `Duration_min` columns.
   - Applied log transformation to skewed features (`Price` and `Duration_hour`) to normalize their distributions.

4. **Outlier Detection and Removal**:
   - Used the Interquartile Range (IQR) method to identify and remove outliers from `Price_log` and `Duration_hour_log`.

5. **Categorical Encoding**:
   - Applied One-Hot Encoding to categorical features such as `Airline`, `Source City`, and `Destination City`.
   - Integrated encoded features into the dataset and removed the original categorical columns.

## Exploratory Data Analysis (EDA)

- **Histograms**: Generated histograms for continuous and categorical features to explore their distributions and identify patterns.
- **Correlation Heatmap**: Produced a heatmap to visualize correlations between numerical features, helping to understand relationships and potential multicollinearity.

## Model Building and Evaluation

- **Model**: Implemented a RandomForestRegressor with 100 estimators to predict the `Price_log`.
- **Evaluation Metrics**:
  - **Mean Absolute Error (MAE)**: 0.0002
  - **Mean Squared Error (MSE)**: 1.27e-06
  - **R² Score**: 0.999995

## Usage Instructions

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/your-username/flight-price-prediction.git
