# Sales-Linear-Regression
# Sales.ipynb: Salary Prediction and Analysis

## Overview
This notebook performs an exploratory data analysis and builds a linear regression model to predict salaries based on academic rank, discipline, years of experience, and gender. The dataset used is `Salaries.csv`.

## Contents

1.  **Data Loading and Initial Inspection**: Loads the `Salaries.csv` file into a pandas DataFrame and displays the first few rows.
2.  **Exploratory Data Analysis (EDA)**: 
    *   Visualizes the distribution of salaries using a histogram.
    *   Analyzes the distribution of academic ranks.
    *   Examines the relationship between sex and rank.
3.  **Data Preprocessing**: 
    *   Performs one-hot encoding for categorical variables (`rank`, `discipline`, `sex`).
    *   Splits the data into features (`X`) and target (`y`, which is `salary`).
4.  **Linear Regression Model (sklearn)**: 
    *   Trains and evaluates a `LinearRegression` model using multiple train-test splits (100 iterations) to assess its stability and average R-squared score.
5.  **OLS Regression Analysis (statsmodels)**: 
    *   Fits an Ordinary Least Squares (OLS) model using `statsmodels` for detailed statistical analysis, including p-values, confidence intervals, and various diagnostic statistics.
    *   Initially, all features (including `sex_Male`) are used.
    *   The `sex_Male` variable is then removed to observe its impact on the model, as it was not statistically significant in the initial OLS summary.

## Key Findings

*   The initial OLS model achieved an R-squared of approximately 0.455, indicating that about 45.5% of the variance in salary can be explained by the included features.
*   `yrs.since.phd`, `yrs.service`, `rank_AsstProf`, `rank_Prof`, and `discipline_B` were found to be statistically significant predictors of salary.
*   The `sex_Male` variable was not statistically significant in the first OLS model, suggesting that after accounting for rank, years of experience, and discipline, gender alone did not show a significant impact on salary within this dataset.
*   Removing the `sex_Male` variable did not significantly alter the R-squared score, confirming its limited individual predictive power in this context.
