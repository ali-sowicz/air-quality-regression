# air-quality-regression
An exploratory and predictive data analysis project focusing on air quality data collected from an Italian city. The project involves cleaning the dataset, analyzing pollutant levels, and developing regression models to predict nitrogen dioxide (NO2) concentrations.

## Dataset

The dataset used in this project is the **Air Quality Data Set** obtained from the UCI Machine Learning Repository. This dataset contains air quality measurements from an Italian city, including data on pollutants and weather conditions.

- **Source:** [UCI Machine Learning Repository - Air Quality Data Set](https://archive.ics.uci.edu/dataset/360/air+quality%E2%9A%A0%EF%B8%8F)
- **Description:** This dataset includes hourly averaged responses from an array of 5 metal oxide chemical sensors embedded in an Air Quality Chemical Multisensor Device. The dataset includes various atmospheric conditions and concentrations of pollutants like CO, NOx, and others.

Please refer to the [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/360/air+quality%E2%9A%A0%EF%B8%8F) for more detailed information about the dataset and its features.

---

This format ensures clarity and provides the necessary context for anyone reviewing your project or the README.

## Models Implemented

### 1. Linear Regressor
Linear regression predicts a continuous target variable (log(NO2)) by modeling the relationship between it and independent variables through a linear equation. The model optimizes the fit by minimizing the sum of squared residuals, allowing for straightforward interpretability of feature effects.

- **Residual Plot Analysis**: Residuals are generally well-distributed around zero, with some outliers. This suggests that while the linear model captures the trend, there may be complexities it cannot fully explain.
- **Evaluation Metrics**:
  - **MSE**: Train: 0.048, Test: 0.050
  - **RMSE**: Train: 0.220, Test: 0.223
  - **R²**: Train: 0.783, Test: 0.761
  - **MAE**: Train: 0.158, Test: 0.155

### 2. K-Nearest Neighbors (KNN) Regressor
KNN predicts the target value by averaging the values of the nearest neighbors, determined based on feature similarity.

- **Residual Plot Analysis**: The residuals are more tightly clustered around zero compared to linear regression, indicating potentially better model performance.
- **Evaluation Metrics**:
  - **MSE**: Train: 0.014, Test: 0.027
  - **RMSE**: Train: 0.120, Test: 0.165
  - **R²**: Train: 0.935, Test: 0.870
  - **MAE**: Train: 0.081, Test: 0.106

### 3. Decision Tree Regressor
Decision trees partition the feature space into regions, assigning the mean target value to each region. They can capture non-linear relationships but are prone to overfitting.

- **Residual Plot Analysis**: The residuals are mostly concentrated around zero, with fewer outliers, suggesting a good fit.
- **Evaluation Metrics**:
  - **MSE**: Train: 0.010, Test: 0.029
  - **RMSE**: Train: 0.098, Test: 0.172
  - **R²**: Train: 0.957, Test: 0.859
  - **MAE**: Train: 0.070, Test: 0.117

### 4. Random Forest Regressor
An ensemble of decision trees that averages their predictions, leading to improved accuracy and reduced overfitting.

- **Residual Plot Analysis**: Shows a very tight distribution around zero, indicating high accuracy and consistency in predictions.
- **Evaluation Metrics**:
  - **MSE**: Train: 0.006, Test: 0.016
  - **RMSE**: Train: 0.079, Test: 0.128
  - **R²**: Train: 0.972, Test: 0.922
  - **MAE**: Train: 0.054, Test: 0.089

### 5. Multi-Layer Perceptron (MLP) Regressor
An artificial neural network that captures complex non-linear relationships through multiple hidden layers and non-linear activation functions.

- **Residual Plot Analysis**: Shows a normal distribution with more scatter compared to the Random Forest, indicating slight overfitting.
- **Evaluation Metrics**:
  - **MSE**: Train: 0.015, Test: 0.022
  - **RMSE**: Train: 0.124, Test: 0.149
  - **R²**: Train: 0.931, Test: 0.894
  - **MAE**: Train: 0.089, Test: 0.100

### 6. AdaBoost Regressor
Combines multiple weak learners to create a strong predictor, emphasizing data points with higher error in successive models.

- **Residual Plot Analysis**: Similar distribution to other models but with some skew, indicating potential areas of improvement.
- **Evaluation Metrics**:
  - **MSE**: Train: 0.033, Test: 0.035
  - **RMSE**: Train: 0.181, Test: 0.187
  - **R²**: Train: 0.852, Test: 0.833
  - **MAE**: Train: 0.146, Test: 0.146

### 7. Ridge Regressor
A regularized version of linear regression that penalizes large coefficients, helping to prevent overfitting.

- **Residual Plot Analysis**: Residuals are fairly evenly distributed, with some outliers, indicating reasonable performance.
- **Evaluation Metrics**:
  - **MSE**: Train: 0.048, Test: 0.050
  - **RMSE**: Train: 0.220, Test: 0.223
  - **R²**: Train: 0.783, Test: 0.761
  - **MAE**: Train: 0.158, Test: 0.155

## Model Comparison and Best Model Selection
The models were evaluated based on MSE, RMSE, R², and MAE metrics. The Random Forest Regressor consistently outperformed other models across these metrics, indicating its superior ability to generalize and accurately predict NO2 concentrations.

- **Best Model**: RandomForestRegressor
  - **R²**: 0.922 (Test)
  - **MSE**: 0.016 (Test)
  - **RMSE**: 0.128 (Test)
  - **MAE**: 0.089 (Test)
