# **House Pricing Prediction using PCA**

## Overview

This project focuses on predicting house prices using various regression models and dimensionality reduction techniques, including Principal Component Analysis (PCA). The dataset includes detailed features of homes and their corresponding sale prices. PCA is used for feature reduction, aiming to reduce the dimensionality of the dataset while preserving as much variance as possible.

## Dataset

The dataset contains 1460 rows and 81 columns, with both numerical and categorical features. Some columns have missing values, which are handled through preprocessing steps. The dataset includes features such as:

- **LotFrontage**: Linear feet of street connected to property
- **LotArea**: Lot size in square feet
- **YearBuilt**: Original construction date of the house
- **GrLivArea**: Above ground living area in square feet
- **BsmtFinSF1**: Type 1 finished square feet
- **FullBath**: Full bathrooms above grade
- **Fireplaces**: Number of fireplaces
- **GarageCars**: Size of garage in car capacity
- **SalePrice**: The target variable, representing the sale price of the house

Additionally, several categorical features are included, such as the neighborhood, garage type, and exterior materials.

### Data Columns:
- **Id**: Unique identifier for each house
- **MSSubClass**: Type of dwelling
- **MSZoning**: General zoning classification
- **LotFrontage**: Frontage of the lot
- **LotArea**: Area of the lot
- **Street**: Type of road access
- **Alley**: Type of alley access
- **LotShape**: General shape of the property
- **LandContour**: Flatness of the property
- **Utilities**: Type of utilities available
- **SalePrice**: Sale price of the house (target variable)

Many columns have missing values, particularly those related to the basement, garage, and pool features, which will be handled during preprocessing.

## Data Preprocessing

- **Handling Missing Values**: Columns with high percentages of missing values, such as `Alley`, `PoolQC`, `Fence`, and `MiscFeature`, were either dropped or imputed as needed.
- **Categorical Features Encoding**: Categorical columns were encoded into numerical values using techniques like one-hot encoding.
- **Numerical Features Scaling**: Numerical features were scaled using StandardScaler to normalize the data before feeding it into models.
- **Target Variable**: The `SalePrice` column is used as the target variable for prediction.

### PCA (Principal Component Analysis)
PCA was applied to reduce the dimensionality of the dataset. By retaining 90% of the variance, we used **n_components=0.9** in PCA to keep the most significant features, thus improving the model's efficiency and reducing overfitting.

## Model Selection

The following regression models were trained and evaluated on the data:

1. **Linear Regression**: A baseline linear model to capture the relationship between the features and the target variable.
2. **Ridge Regression**: A regularized version of linear regression to mitigate overfitting.
3. **Lasso Regression**: Another regularized linear regression method that performs feature selection.
4. **SVR (Support Vector Regression)**: A non-linear regression model based on support vector machines.
5. **KNN Regressor**: A non-parametric method that predicts the target based on the k-nearest neighbors.
6. **Decision Tree Regressor**: A decision tree model that splits the data based on feature values.
7. **Random Forest**: An ensemble of decision trees to improve predictive accuracy.
8. **Voting Regressor**: A model that combines multiple regression models (SVR, KNN, and Decision Tree) to improve accuracy.
9. **XGBoost**: A gradient boosting method known for its predictive power and efficiency.

## Model Evaluation

After training the models, we evaluated their performance using R², accuracy, and RMSE on the test set. Below are the evaluation results:

- **KNN**:
  - Training Accuracy: 99%
  - Testing Accuracy: 83%
  - RMSE: 35,507.59
  - R² Score: 0.75

- **Random Forest**:
  - Training Accuracy: 97%
  - Testing Accuracy: 88%
  - RMSE: 29,953.52
  - R² Score: 0.83

- **Voting Regressor**:
  - Training Accuracy: 96%
  - Testing Accuracy: 86%
  - RMSE: 31,618.09
  - R² Score: 0.83

- **XGBoost**:
  - Training Accuracy: 99%
  - Testing Accuracy: 89%
  - RMSE: 28,187.18
  - R² Score: 0.83

## Conclusion

- **PCA** with `n_components=0.9` was successfully applied for dimensionality reduction, retaining 90% of the dataset's variance.
- Among the models tested, **XGBoost** achieved the best performance with 99% training accuracy and 89% testing accuracy.
- **Random Forest** and **Voting Regressor** also performed well, achieving testing accuracies of 88% and 86%, respectively.

### Summary of Results:
- **KNN**: 83% Testing Accuracy
- **Random Forest**: 88% Testing Accuracy
- **Voting Regressor**: 86% Testing Accuracy
- **XGBoost**: **Best Model**, 89% Testing Accuracy

## Future Work

- Experiment with different hyperparameters to further optimize model performance.
- Explore advanced feature engineering techniques and handle missing data more effectively.
- Incorporate additional ensemble methods or stacking models for better predictions.



## Author

- **[Hossam Taha]**
- LinkedIn: [[Your LinkedIn Link](https://www.linkedin.com/in/hossam-taha-41b724288/)]
