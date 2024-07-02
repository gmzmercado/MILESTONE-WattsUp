## Watts Up, Doc? Forecasting Electricity Prices
![Header](header.png)

## Abstract

This project focuses on forecasting electricity prices using time series data. The study aims to equip energy traders with a robust forecast model to predict hourly electricity prices for 21 days. Using various machine learning techniques and extensive feature engineering, this project highlights the importance of temporal components in predictive modeling. The study demonstrates the significance of feature engineering and the impact of including additional variables, showcasing the comparative performance of models with and without feature engineering.

## Highlights
This study delves into solving Time Series Machine Learning issues, focusing on Feature Engineering and Data Preprocessing for such problems. Key aspects include:

1. **DateTime Extraction**: Extracting and utilizing date-time data.
2. **Lag Variable Integration**: Incorporating lag variables for better predictions.

The study emphasizes **Mean Absolute Error (MAE)** as the crucial metric for evaluating Time Series models, given its accuracy in measuring prediction errors.

## Data Sources and Description

### Dataset Used
- **Source**: Kaggle - Hourly energy demand, generation, and weather data for Spain over 4 years.
- **Features**: 
  - 'time', 'generation biomass', 'generation fossil brown coal/lignite', 'generation fossil coal-derived gas', 'generation fossil gas', 'generation fossil hard coal', 'generation fossil oil', 'generation fossil oil shale', 'generation fossil peat', 'generation geothermal', 'generation hydro pumped storage aggregated', 'generation hydro pumped storage consumption', 'generation hydro run-of-river and poundage', 'generation hydro water reservoir', 'generation marine', 'generation nuclear', 'generation other', 'generation other renewable', 'generation solar', 'generation waste', 'generation wind offshore', 'generation wind onshore', 'forecast solar day ahead', 'forecast wind offshore eday ahead', 'forecast wind onshore day ahead', 'total load forecast', 'total load actual', 'price day ahead', 'price actual'

### Data Assumptions and Limitations
- **Representativeness** - The dataset represents electricity consumption, generation, and pricing for Spain.
- **Time-Bound Analysis** - The dataset spans 4 years, providing a robust timeline for analysis.
- **Scope of Data** - Focused on Spain's energy market.
- **Potential Bias** - Data is specific to Spain and may not generalize to other regions.

## Methodology

1. **Data Collection**
   - Collected from Kaggle, containing 35,064 rows and 29 columns.

2. **Data Preprocessing**
   - **Handling Missing Values** - Used forward-fill and backward-fill methods to handle missing data.
   - **Categorical Data** - Converted categorical features using one-hot encoding.
   - **Feature Engineering**:
     - **DateTime Extraction** - Extracted and concatenated DateTime variables (year, month, day, hour, weekday) to enhance the model's temporal understanding.
     - **Lag Features** - Introduced lag values for 'price actual' to account for previous hours' prices in predictions.
     - **Rolling Statistics** - Computed rolling mean and standard deviation for selected features to capture trends and volatility.
   - **Correlation Analysis** - Used Pearson Correlation Coefficient to identify and remove highly correlated features to reduce multicollinearity.
   - **Normalization** - Applied Min-Max scaling to normalize the features for better model performance.

3. **Model Training**
   - Evaluated eight models - k-Nearest Neighbors, Linear Regression, Lasso Regression, Ridge Regression, Decision Tree, Random Forest, Gradient Boosting, and XGBoost.
   - **Hyperparameter Tuning** - Used GridSearchCV for hyperparameter tuning to optimize model performance.
   - **Assessment Metric** - Used Mean Absolute Error (MAE) as the primary metric for model evaluation.

## Actionable Insights

The study identified that short-term historical data (lag variables) significantly impacts forecasting accuracy. Gradient Boosting and Random Forest models performed best, demonstrating the effectiveness of feature engineering and thorough data preprocessing. Notably, the absence of feature engineering led to a significant drop in model performance, emphasizing its critical role in predictive accuracy.

## Conclusion

By leveraging advanced feature engineering and robust machine learning techniques, this study provides a reliable model for predicting hourly electricity prices. The insights highlight the critical role of temporal data in forecasting and the superiority of tree-based models for this task. The comparative analysis underscored the necessity of feature engineering in improving model accuracy, with models performing poorly without it.

## Additional Resources

- **Jupyter Notebook**: The detailed analysis and code used in this study are available in the `Watts_Up_Doc.ipynb` file.
- **HTML Technical Report**: The HTML version of the detailed analysis and code used in this study is available in the `Watts_Up_Doc.html` file.

## Citation

If you use this notebook or any part of this study, please cite:

Gabriel Marco Mercado, "Watts Up, Doc? Forecasting Electricity Prices Using Machine Learning," 2024.