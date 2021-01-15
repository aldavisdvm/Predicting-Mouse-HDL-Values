# Predicting-Mouse-HDL-Values

## Project Description
The purpose of this project is to compare a multiple regression model with a TPOT regression in predicting the values
of high density lipoproteins(HDL) in the blood of mice using other blood chemistry values as features.

### Methods Used

* Data Cleaning
* Machine Learning
* Data Visualization
* Predictive Modeling
* Linear Regression
* TPOT Classifier

### Technologies

* Jupyter Notebook
* Python
* Pandas and numpy
* Scikit-Learn
* Seaborn and Matplotlib

### Data was obtained from:
https://phenome.jax.org/projects/Stahl1
Stahl1: Blood reference levels for hematology and clinical chemistry for C57BL/6J mice (2018)

Stahl FR, Jung R, Jazbutyte V, Ostermann E, Tödter S, Brixel R, Kemmer A, Halle S, Rose-John S, Messerle M,
 Arck PC, Brune W, Renné T. Laboratory diagnostics of murine blood for detection of mouse cytomegalovirus (MCMV)-induced hepatitis.
 Sci Rep. 2018 Oct 4;8(1):14823. doi: 10.1038/s41598-018-33167-7.

## Project Summary

Data was explored, cleaned, and analyzed. Although the basis for the model - using other blood chemistry values
as features to predict HDL values - was not a great model in general with this data set, it was sufficient to compare 
the differences in performance of these two model strategies.

As the linear regression had a low r-squared value (coefficient of determination: 0.38), it
wasn't surprising that the MSE was so high (210.19).
The TPOT regression model came up with an r-squared of 0.38 and an MSE of 35.97 after five generations.
TPOT found the best pipeline steps to be:
1. StackingEstimator(estimator=KNeighborsRegressor(n_neighbors=12, p=1))
2. PolynomialFeatures(include_bias=False)
3. LassoLarsCV()

Since TPOT found using polynomial features fit the data better, a polynomial regression model might be
a next step comparison.

