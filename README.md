# Flight Ticket Price Prediction Using Machine Learning

This project aims to develop a machine learning model for predicting flight ticket prices based on historical data. The analysis involves data preprocessing, feature engineering, model training, and evaluation using regression techniques.

---

## Table of Contents
1. [Project Overview](#project-overview)
2. [Data Preprocessing](#data-preprocessing)
3. [Feature Engineering](#feature-engineering)
4. [Exploratory Data Analysis](#exploratory-data-analysis)
5. [Model Building](#model-building)
6. [Model Evaluation](#model-evaluation)
7. [Installation](#installation)
8. [Dependencies](#dependencies)
9. [Conclusion](@conclusion)

---

## Project Overview

The goal of this project is to predict flight ticket prices using machine learning. The dataset consists of various factors such as airline, source, destination, total stops, and time-related features. The **Random Forest Regressor** was found to be the most effective model for this task.

This project includes:
- **Data Preprocessing**: Cleaning and preparing data for training.
- **Feature Engineering**: Extracting useful features such as time-based attributes.
- **Exploratory Data Analysis (EDA)**: Visualizing key relationships in the data.
- **Model Training & Evaluation**: Implementing machine learning models and comparing their performance.

---

## Data Preprocessing

The dataset was loaded from Excel files and underwent the following preprocessing steps:
1. **Loading Data**:
   - Training and test datasets were loaded.
   - Initial inspection was performed using `head()`, `shape`, and `info()` methods.
   
2. **Handling Missing Values**:
   - Missing values were imputed where necessary to ensure data completeness.

---

## Feature Engineering

Various techniques were applied to create meaningful features:

### **1. Time-Based Features**
- **Journey Day and Month**: Extracted from the date column to capture seasonal price variations.
- **Departure & Arrival Time**: Categorized into "Morning", "Noon", and "Night" to capture pricing patterns.

### **2. Airline and Route Features**
- **Total Stops**: Encodes the complexity of the journey, influencing price.
- **Airline Type**: Differentiates between budget and premium carriers.

### **3. Source and Destination Features**
- **Distance Calculation**: Estimated flight distance based on airport locations.
- **Popular Routes**: Identified frequently traveled paths impacting demand and pricing.

### **4. Booking Class and Offers**
- **Economy vs. Premium**: Encodes different pricing structures.
- **Promotions**: Integrated discounts and offers as binary features.

---

## Exploratory Data Analysis

### **1. Airline vs. Price Analysis**
- **Jet Airways Business** has the highest median price.
- Other airlines have relatively similar price distributions.

### **2. Source vs. Price Analysis**
- Ticket prices vary based on the journey's source.
- Pricing dynamics are influenced by distance, demand, and economic factors.

### **3. Correlation Analysis**
- A heatmap was used to analyze correlations between numeric variables.
- Flight duration showed a moderate correlation with ticket prices.

---

## Model Building

This is a regression problem, and the following models were used:

1. **Random Forest Regressor**: An ensemble-based method for improved accuracy.
2. **Randomized Search CV**: Used for hyperparameter tuning.

### **Feature Selection**
Key features used for training:
- **Categorical Features** (One-Hot Encoded): Airline, Source, Destination.
- **Numerical Features**: Total stops, journey time, departure and arrival times.
- **Booking Class Features**: Economy vs. Premium.

---

## Model Evaluation

| Model                  | MSE          | MAE         | RMSE         |
|------------------------|-------------|-------------|-------------|
| **Random Forest Regressor** | 1392.30     | 5161.21     | 2271.83     |
| **Randomized Search CV**    | 1696.49     | 6147.96     | 2479.50     |

- The **Random Forest Regressor** performed best, with lower MSE, MAE, and RMSE.
- The **Randomized Search CV** model did not significantly improve performance.

---

## Installation

- Install dependencies:
pip install -r requirements.txt

---

## Dependencies

- The following libraries are required:

Python >= 3.7

Pandas >= 1.0

NumPy >= 1.18

Scikit-learn >= 0.22

Matplotlib >= 3.1

Seaborn >= 0.10

XGBoost >= 1.0

---

## Conclusion

The Random Forest Regressor was the most effective model for predicting flight ticket prices, outperforming the Randomized Search CV method. The analysis highlights key factors influencing ticket prices, including airline, route, travel time, and booking class.


