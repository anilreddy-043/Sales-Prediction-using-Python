# Sales Prediction Using Python 📊

## Project Overview

This project focuses on predicting product sales based on advertising expenditure across different marketing channels.

The project analyzes the relationship between advertising spending on:

* TV
* Radio
* Newspaper

and the resulting **Sales**.

A **Linear Regression** machine learning model is trained to predict sales based on the advertising budget.

## Objective

The main objectives of this project are:

* Analyze advertising expenditure and its relationship with sales.
* Clean and prepare the dataset.
* Perform Exploratory Data Analysis (EDA).
* Identify the impact of different advertising channels on sales.
* Build a Linear Regression model.
* Evaluate model performance.
* Predict sales for a new advertising budget.
* Perform what-if analysis for different advertising scenarios.

## Dataset

The project uses an `Advertising.csv` dataset.

### Dataset Features

| Feature   | Description                               |
| --------- | ----------------------------------------- |
| TV        | Advertising expenditure through TV        |
| Radio     | Advertising expenditure through Radio     |
| Newspaper | Advertising expenditure through Newspaper |
| Sales     | Sales generated                           |

An unnecessary `Unnamed: 0` column is removed during data preprocessing.

## Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Jupyter Notebook

## Machine Learning Algorithm

### Linear Regression

Linear Regression is used to model the relationship between advertising expenditure and sales.

The input features are:

```text
TV
Radio
Newspaper
```

The target variable is:

```text
Sales
```

## Project Workflow

```text
Load Dataset
      ↓
Data Inspection
      ↓
Data Cleaning
      ↓
Exploratory Data Analysis
      ↓
Correlation Analysis
      ↓
Feature Selection
      ↓
Train-Test Split
      ↓
Linear Regression
      ↓
Sales Prediction
      ↓
Model Evaluation
      ↓
Residual Analysis
      ↓
What-If Analysis
      ↓
Business Insights
```

## Data Cleaning

The following preprocessing steps are performed:

1. Load the CSV dataset.
2. Check dataset shape.
3. Inspect the first few records.
4. Check column names and data types.
5. Remove the unnecessary `Unnamed: 0` column.
6. Check missing values.
7. Check duplicate rows.
8. Generate descriptive statistics.

## Exploratory Data Analysis

Several visualizations are created to understand the dataset.

### 1. Sales Distribution

A histogram with KDE is used to understand the distribution of sales.

### 2. Correlation Matrix

A heatmap is used to analyze correlations between:

* TV advertising
* Radio advertising
* Newspaper advertising
* Sales

### 3. Advertising vs Sales

Scatter plots are created for:

* TV vs Sales
* Radio vs Sales
* Newspaper vs Sales

These visualizations help understand the relationship between advertising expenditure and sales.

## Correlation Analysis

The project calculates the correlation between each advertising channel and sales:

```python
df["TV"].corr(df["Sales"])
df["Radio"].corr(df["Sales"])
df["Newspaper"].corr(df["Sales"])
```

This helps identify which advertising channels have stronger relationships with sales.

## Feature Selection

The following features are selected:

```python
X = df[['TV', 'Radio', 'Newspaper']]
```

The target variable is:

```python
y = df['Sales']
```

## Train-Test Split

The dataset is divided into:

* **80% Training Data**
* **20% Testing Data**

The split uses:

```python
random_state=42
```

## Model Training

A Linear Regression model is created using Scikit-learn:

```python
from sklearn.linear_model import LinearRegression

model = LinearRegression()

model.fit(X_train, y_train)
```

## Prediction

After training, the model predicts sales for the test dataset:

```python
y_pred = model.predict(X_test)
```

## Model Evaluation

The model is evaluated using:

### R² Score

R² measures how well the model explains the variation in sales.

```python
r2 = r2_score(y_test, y_pred)
```

### Mean Squared Error

```python
mse = mean_squared_error(y_test, y_pred)
```

### Root Mean Squared Error

```python
rmse = np.sqrt(mse)
```

## Model Coefficients

The project analyzes the regression coefficients to understand the contribution of each advertising channel.

```python
coefficients = pd.DataFrame({
    "Feature": X.columns,
    "Coefficient": model.coef_
})
```

The coefficients are visualized using a bar chart titled:

**Advertising Impact on Sales**

## Actual vs Predicted Sales

A scatter plot is created to compare:

* Actual Sales
* Predicted Sales

This helps visually evaluate the model's prediction performance.

## Residual Analysis

Residuals are calculated as:

```python
residuals = y_test - y_pred
```

A residual plot is created to examine prediction errors and identify possible patterns.

## New Sales Prediction

The trained model is used to predict sales for a new advertising budget:

```python
new_data = pd.DataFrame({
    'TV': [150],
    'Radio': [30],
    'Newspaper': [20]
})

predicted_sales = model.predict(new_data)
```

This demonstrates how the model can be used to estimate sales for a new advertising plan.

## What-If Analysis

The project also evaluates different TV advertising budgets while keeping Radio and Newspaper spending fixed.

Example scenarios:

```text
TV: 100, 150, 200, 250, 300
Radio: 40
Newspaper: 30
```

The model predicts sales for each scenario.

This can help understand how changing the advertising budget may influence expected sales.

## Visualizations

The project includes:

* Sales distribution histogram
* Correlation heatmap
* TV vs Sales scatter plot
* Radio vs Sales scatter plot
* Newspaper vs Sales scatter plot
* Actual vs Predicted Sales plot
* Residual plot
* Advertising Impact bar chart

## Project Structure

```text
Sales-Prediction/
│
├── TASK-4Sales_Prediction_using_Python.ipynb
├── Advertising.csv
├── README.md
└── requirements.txt
```

## How to Run the Project

### 1. Clone the repository

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
```

### 2. Open the project folder

```bash
cd Sales-Prediction
```

### 3. Create a virtual environment

```bash
python -m venv .venv
```

### 4. Activate the environment

For Windows:

```bash
.venv\Scripts\activate
```

### 5. Install dependencies

```bash
pip install -r requirements.txt
```

### 6. Start Jupyter Notebook

```bash
jupyter notebook
```

Open:

```text
TASK-4Sales_Prediction_using_Python.ipynb
```

## Business Insights

This project demonstrates how machine learning can support marketing decisions by:

* Understanding the relationship between advertising and sales.
* Comparing the impact of different advertising channels.
* Estimating sales for a proposed advertising budget.
* Performing what-if analysis before changing advertising expenditure.
* Supporting data-driven marketing decisions.

## Conclusion

The project demonstrates an end-to-end **Sales Prediction workflow using Python and Linear Regression**.

The analysis starts with data cleaning and exploratory analysis and continues through model development, evaluation, residual analysis, and sales prediction.

The resulting model can be used as a basic predictive tool to estimate expected sales based on advertising expenditure.

## Author

**Seelam Anil Reddy**

Aspiring Data Scientist | Python Developer

GitHub: https://github.com/anilreddy-043
