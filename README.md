# Energy-Prediction-Using-BDG2-Data

# BDG2 Energy Prediction

Welcome to the BDG2 Energy Prediction project!  
This repository contains all the code, data, and resources used to predict energy consumption in educational buildings using the Building Data Genome 2 (BDG2) dataset. This project leverages advanced machine learning models to improve energy efficiency in educational institutions, contributing to broader sustainability goals.

## 🚀 Project Overview

Educational buildings, due to their extensive operational hours and diverse functional areas, are significant consumers of energy. This project aims to accurately estimate energy consumption in these buildings, providing insights that can guide energy efficiency improvements and support sustainability initiatives.

### Key Highlights:

- **Data-Driven Approach**: The project uses the comprehensive BDG2 dataset, which includes detailed information on building metadata, weather conditions, and energy consumption.
- **Advanced Modeling**: The project employs state-of-the-art machine learning models, including Light Gradient Boosting (LGBM), Random Forest, and Neural Networks, to predict energy usage.
- **Sustainability Impact**: By improving energy consumption predictions, the project supports initiatives to reduce greenhouse gas emissions and enhance energy efficiency in educational settings.

## 📊 Dataset

The project utilizes three primary datasets from the BDG2 collection, covering the years 2016 and 2017:

- **Building Metadata**: This dataset includes descriptive attributes for 1,636 buildings, such as primary usage, the number of floors, total area, and site ID, which groups buildings in the same location.
- **Weather Data**: Provides daily weather conditions for each site, including air temperature, cloud coverage, and wind direction. The weather data was analyzed for seasonality and compared across the two years.
- **Meter Readings**: Contains hourly energy consumption data for eight different energy sources, including electricity, chilled water, steam, hot water, gas, water, irrigation, and solar. The analysis focuses on the five most prevalent meter types: electricity, chilled water, hot water, and gas, excluding steam due to data inconsistencies.
- Link to data: https://drive.google.com/drive/folders/1XwDgH2sRt3vHiWx-207atXLFmgMyXmVa?usp=drive_link 

### Data Preprocessing

- **Exploratory Data Analysis (EDA)**: Initial data exploration was performed to understand distributions, identify outliers, and assess correlations.
- **Logarithmic Transformation**: Meter readings exhibited a highly right-skewed distribution, so a logarithmic transformation was applied to normalize the data.
- **Feature Selection**: Focused on buildings used for educational purposes (~617 buildings) and the most reliable meter types.
- **Data Consolidation**: Combined datasets and transformed timestamps into date formats. Weather data was aggregated from hourly to daily readings, and the data was split into training and validation sets for the years 2016 and 2017.

## 🛠️ Methodology

### 1. Data Preprocessing

- **Normalization**: Numerical features were normalized using MinMaxScaler to standardize them between zero and one.
- **Encoding**: Categorical features were one-hot encoded using Scikit-Learn’s OneHotEncoder, allowing the use of these features in machine learning models without introducing ordinal relationships.
- **Transformation**: A logarithmic transformation was applied to the target variable (energy consumption) to address skewness and improve model performance.

### 2. Modeling

**Models Used**:

- **Light Gradient Boosting Machine (LGBM)**: Known for its efficiency and accuracy, particularly on large datasets.
- **Random Forest**: Offers robustness and interpretability, handling outliers and non-linear data effectively.
- **Neural Networks (Nnet)**: Capable of modeling complex, non-linear relationships in large datasets, useful for capturing detailed energy usage patterns.

**Hyperparameter Tuning**: Grid search was used to fine-tune parameters for each model:

- **LGBM**: Adjusted parameters like the number of leaves and learning rate.
- **Random Forest**: Tuned the number of trees and tree depth.
- **Neural Networks**: Optimized the number of hidden layers, neurons per layer, and learning rate.

**Evaluation Metrics**: The models were evaluated using R-squared and negative Mean Squared Error (MSE) to select the best-performing parameters for each meter type.

### 3. Training and Testing

The models were trained on the 2016 data and validated on the 2017 data to ensure they generalize well to unseen data.  
After training, the models were used to predict energy consumption for the next year, with LGBM emerging as the most accurate model.

## 📈 Results and Insights

The LGBM model showed superior performance across most metrics:

- **Electricity**: LGBM R-squared = 0.818
- **Chilled Water**: LGBM R-squared = 0.726
- **Hot Water**: LGBM R-squared = 0.601
- **Gas**: LGBM R-squared = 0.726

These results indicate that the LGBM model is highly effective in predicting energy consumption, explaining a significant portion of the variance in energy usage within educational buildings.

### Model Performance Summary

- **Neural Networks**: While capable of capturing complex patterns, they underperformed relative to LGBM and Random Forest.
- **Random Forest**: Provided robust performance and interpretability, though not as accurate as LGBM.
- **LGBM**: Best overall performer, offering a balance of speed, accuracy, and ease of tuning.

## 🔮 Future Work

There are several areas for future research to further enhance the accuracy and applicability of the energy consumption predictions:

- **Real-Time Data Integration**: Incorporating real-time energy consumption and weather data could improve the model's responsiveness and accuracy.
- **Advanced Modeling Techniques**: Exploring the use of Recurrent Neural Networks (RNNs) and Seasonal Autoregressive Integrated Moving Average (SARIMA) models to capture temporal dependencies and seasonal patterns in energy usage.
- **Contextual Variables**: Including additional contextual variables, such as occupancy rates or specific usage patterns, to refine predictions.

## 📝 Conclusion

This project successfully demonstrated the potential of machine learning models, particularly LGBM, in accurately predicting energy consumption in educational buildings. The results provide valuable insights for energy management, supporting efforts to improve sustainability and reduce operational costs in educational institutions.

## 📂 Repository Structure

- **Data Preprocessing & EDA**: Contains notebooks and scripts for data cleaning, feature engineering, and exploratory data analysis.
- **Modeling**: Scripts for training, tuning, and evaluating machine learning models, with a focus on LGBM, Random Forest, and Neural Networks.
- **Results**: Final models, performance metrics, and visualizations comparing predicted vs. actual energy consumption.
- **Reports**: Detailed reports and presentations summarizing the project’s methodology, results, and conclusions.

## 💻 How to Use

Clone the repository:

```bash
git clone https://github.com/sameerab04/BDG2_Energy_Prediction.git

