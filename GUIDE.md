# Assignment Solution Guide

## Problem Understanding
The objective is to model the demand for shared bikes (`cnt`) using available independent variables. The dataset consists of daily records containing weather information, dates, and casual/registered user counts.

**Target Variable**: `cnt` (Total count of rental bikes)

## Solution Steps

### 1. Data Understanding & Cleaning
- **Loaded Data**: `day.csv`.
- **Dropped Columns**:
  - `instant`: Just a record index.
  - `dteday`: Redundant (we already have year, month, weekday).
  - `casual`, `registered`: These sum up to the target `cnt`. Including them would cause **Data Leakage** (predicting the target using the target itself).
  - `atemp`: Dropped after checking VIF due to high multicollinearity with `temp`.

### 2. Preprocessing
- **Categorical Encoding**:
  - Variables like `season`, `weathersit`, `mnth`, and `weekday` are numeric in the dataset (e.g., season 1, 2, 3, 4) but they are actually **categorical**.
  - **Action**: Converted them to dummy variables using One-Hot Encoding (`pd.get_dummies`) to avoid the model misinterpreting them as ranked numbers.

### 3. Assumption Checking
- **Multicollinearity**: Checked Variance Inflation Factor (VIF).
  - Found strict correlation between `temp` and `atemp`. Removed `atemp`.
- **Linearity**: The relationship between key numeric vars (`temp`) and demand is linear.

### 4. Model Building
- **Train-Test Split**: Data was split 70% for Training and 30% for Testing to prevent overfitting.
- **Algorithm**: Ordinary Least Squares (OLS) Linear Regression using `statsmodels`.

### 5. Model Evaluation
- **Residual Analysis**:
  - Residuals are normally distributed (Bell curve).
  - Residuals vs. Fitted values plot shows no clear pattern (Homoscedasticity).
- **Metrics**:
  - **Train R2**: 0.85
  - **Test R2**: 0.83
  - **Verdict**: The model generalizes well and does not overfit.

## Conclusion
The model successfully identifies key drivers of demand. Temperature and Year allow for strong positive predictions, while adverse weather (High Wind, Humidity, Rain) allows for negative corrections.
