# Linear Regression From Scratch

A progression of three notebooks: understanding **Simple Linear Regression** from scratch, implementing the same problem with **scikit-learn**, and extending the idea to **Multiple Linear Regression** with 10 input features.

## Project Structure

```
├── data/
│   └── Student.csv
├── notebooks/
│   ├── simple_LR.ipynb           # Simple LR from scratch
│   ├── simple_lr_sklearn.ipynb   # Simple LR with sklearn
│   └── multiple_LR.ipynb         # Multiple LR (sklearn diabetes dataset)
├── graphs/                       # Saved plots
├── Linear_Regression_Project_Summary.docx
└── .gitignore
```

## 1. `simple_LR.ipynb` — Simple Linear Regression From Scratch

Uses `Study_Hours` as the single input feature and `Grade` as the target. A custom class, `my_simple_lr`, calculates the slope and intercept directly from the training data and uses them to predict test values.

**Model equation:** `Grade = m × Study_Hours + b`
**Completed equation:** `Grade ≈ 7.0354 × Study_Hours + 25.7090`

Concepts practiced:
- Loading the student CSV
- Selecting one feature and one target
- 80/20 train-test split with `random_state=42`
- Calculating slope and intercept manually
- Prediction with the learned equation
- MAE, MSE, RMSE, and R² evaluation
- Regression-line and Actual-vs-Predicted visualizations

## 2. `simple_lr_sklearn.ipynb` — Simple Linear Regression With Sklearn

Same dataset and target relationship, but the model is built with `sklearn.linear_model.LinearRegression`.

Workflow:
- Load the dataset and select `Study_Hours` / `Grade`
- Split into training and test sets
- Reshape X for sklearn
- Fit `LinearRegression()`
- Predict the test set
- Calculate MAE, MSE, RMSE, and R²
- Plot the regression line and Actual vs Predicted values
- Display the final regression equation

### Evaluation Results

| Metric | Value |
|--------|-------|
| MAE | 2.014381 |
| MSE | 7.621016 |
| RMSE | 2.760619 |
| R² | 0.984612 |

## 3. `multiple_LR.ipynb` — Multiple Linear Regression

Uses sklearn's diabetes dataset: `X` has shape `(442, 10)`, `y` has shape `(442,)`. After an 80/20 split, training data has 353 rows and test data has 89 rows.

Two approaches are demonstrated:
- **Sklearn's `LinearRegression`**
- **Custom `my_LR` class** — adds a column of ones for the intercept and calculates coefficients using matrix operations based on the normal equation

### Results

| Result | Value |
|--------|-------|
| Sklearn R² | 0.4526027630 |
| Custom-model R² | 0.4526027630 |
| Intercept | 151.345605 |

The sklearn and custom implementations produce essentially identical R² values and matching coefficients/intercept to numerical precision — confirming the custom multiple-regression calculation reproduces the sklearn result.

## Overall Learning Summary

| Area | What was practiced |
|------|--------------------|
| Data handling | CSV loading, feature/target selection, sklearn dataset loading |
| Splitting | 80/20 train-test split with `random_state=42` |
| From scratch | Slope/intercept calculation and matrix-based multiple regression |
| Sklearn | `LinearRegression().fit()` and `.predict()` |
| Evaluation | MAE, MSE, RMSE, and R² |
| Visualization | Regression line, Actual-vs-Predicted plot, coefficient visualization |

## Final Takeaway

The three notebooks build the same regression concept step by step: Simple Linear Regression explains the mathematics with one feature, the sklearn notebook shows how the same model is implemented with a library, and Multiple Linear Regression extends the idea to several features. The custom multiple-regression model closely matches sklearn.

## Requirements

```
numpy
pandas
scikit-learn
matplotlib
```

## Usage

Clone the repo and open the notebooks in Jupyter:

```bash
git clone https://github.com/Laraib-Irfan/linear-regression-project.git
cd linear-regression-project
jupyter notebook
```
