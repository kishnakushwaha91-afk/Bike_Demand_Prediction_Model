# Bike Demand Prediction Assignment
### Machine Learning - Linear Regression

This project involves building a Multiple Linear Regression model to predict the demand for shared bikes based on independent variables such as temperature, weather, season, etc.

## 📌 Problem Statement
A bike-sharing system wants to understand the factors affecting the demand for these shared bikes. The goal is to:
- Identify significant variables predicting the demand.
- Build a predictive model to estimate the demand.

## 📂 Project Structure
- 'bike_demand_assignment.ipynb': The main Jupyter Notebook containing the code for EDA, Preprocessing, Model Building, and Evaluation.
- 'day.csv': The dataset used for training the model.
- 'GUIDE.md': A detailed report on the problem and the solution approach.
- 'requirements.txt': List of Python libraries required to run the project.

## 🚀 How to Run
1. Clone this repository.
2. Install dependencies:

       pip install -r requirements.txt

3. Open the Jupyter Notebook:

       jupyter notebook bike_demand_assignment.ipynb

## 📊 Key Findings
- **R-squared**: 0.828 (Test Set) - The model explains ~83% of the variance in demand.
- **Top Significant Variables**:
  - 'temp' (Temperature): Positive correlation.
  - 'yr' (Year): Demand increased significantly in the second year.
  - 'hum' (Humidity) & 'windspeed': Negative correlation.
  - 'season_spring' & 'light_snow': Negative impact on demand.

## 🛠 Technologies Used
- Python
- Pandas, NumPy (Data Manipulation)
- Seaborn, Matplotlib (Visualization)
- Statsmodels (Statistical Modeling)
- Scikit-learn (Evaluation)
