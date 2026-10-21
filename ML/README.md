# ML Learning Projects

This folder contains hands-on Machine Learning exercises completed while learning Python, Pandas, and Scikit-learn.

## Project 1: Advertising Sales Prediction

**Notebook:** [Linear Regression Model on Advertising dataset.ipynb](./Linear%20Regression%20Model%20on%20Advertising%20dataset.ipynb)

### Business problem

Use advertising budgets to predict product sales. This project starts with TV advertising as a single feature, then uses TV, radio, and newspaper advertising together.

### Dataset

The Advertising dataset contains 200 observations and these columns:

| Column | Description | Role |
|---|---|---|
| `TV` | TV advertising budget (thousands of dollars) | Feature |
| `radio` | Radio advertising budget (thousands of dollars) | Feature |
| `newspaper` | Newspaper advertising budget (thousands of dollars) | Feature |
| `sales` | Product sales (thousands of units) | Target |

Source: [An Introduction to Statistical Learning — resources](https://www.statlearning.com/resources-second-edition) (Advertising dataset).

The original CSV may include an `Unnamed: 0` column containing a saved row index. The notebook inspects and removes this non-business column before modeling.

### What this notebook covers

- Load the CSV with Pandas and inspect its rows, columns, and data types.
- Check missing values and duplicate rows.
- Review descriptive statistics and explore TV advertising versus sales.
- Calculate correlation as a measure of linear association (not causation).
- Split the data into training and test sets.
- Train Linear Regression using TV advertising alone, then using all three advertising features.
- Generate test predictions and compare actual versus predicted sales.
- Evaluate predictions with Mean Absolute Error (MAE).
- Compare the regression models against a mean-prediction `DummyRegressor` baseline.

### Current experiment results

Using the 80/20 train-test split with `random_state=42`:

| Model | Test MAE (thousands of sales units) |
|---|---:|
| Mean-prediction baseline | 4.9625 |
| Linear Regression (TV only) | 2.4444 |
| Linear Regression (TV, radio, newspaper) | 1.4608 |

On this test split, the model using all three features has the lowest MAE of these tested approaches. These are learning-experiment results from one split, not a guarantee of performance on new business data. Additional validation would be needed before selecting a production model.

### How to run

1. Install the libraries if needed:

   ```bash
   pip install pandas matplotlib seaborn scikit-learn jupyter
   ```

2. Download `Advertising.csv` from the source linked above.
3. Place `Advertising.csv` in the same working directory used by the notebook (the notebook reads it using `pd.read_csv("Advertising.csv")`).
4. Open the notebook in Jupyter and run the cells from top to bottom.

### Important limitation

The dataset is intended for learning and illustrates relationships in observational data. Correlation and model coefficients do not establish that advertising spending causes sales to increase.
