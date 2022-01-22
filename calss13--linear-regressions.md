# Linear Regressions Using Scikit-learn
* Linear Regression is used to predict output values from input values using a line that fits the data.
* Linear regression is one of the fundamental statistical and machine learning techniques.
* Regression analysis is one of the most important fields in statistics and machine learning. There are many regression methods available. Linear regression is one of them.
* Typically, you need regression to answer whether and how some phenomenon influences the other or how several variables are related.
* Simple or single-variate linear regression is the simplest case of linear regression with a single independent variable, 𝐱 = 𝑥.
* Scikit-learn is a Python model for machine learning.
* Scikit-learn contains many functions such as for regression, classification and clustering.
* sklearn.linear_model contains functions for regression.
* We import the required Python libraries:
```
import numpy as np
import pandas as pd
import schipy.stats as stats
import matplot.pyplot as plt
import sklearn
```
* the least squares method is used to estimate the coefficients.
* The available data is called target data and represented on the y-axis
* X-axis represents the independent  variables 
* We import linear regression from sci-kit using `from sklearn.linear_model import LinearRegression
* We store linear regression object in a variable such as `lm = LinearRegression()`
* To get suggestions or see LR we can type LinearRegression a dot and a tap.
* Some of the important function are:
`lm.fit()` -> fits a linear model
`lm.predict()` -> Predict Y using the linear model with estimated coefficients
`m.score()` -> Returns the coefficient of determination (R^2)

<br />

 ## Fitting a Linear Model

* to plot a scatter plot between two datas we use `plt.scatter(data1, data1)`
* to give x axis a labe `plt.xlabel("somet description")`
* to give y axis a labe `plt.ylabel("somet description")`
* to give the pot a title `plt.title("some title")`
* to show the plot `plt.show`
* to calculate some predicted data we use the `lm.predict(x)`
* To do train-test split you have to divide your data sets randomly and then Scikit learn provides a function called train_test_split.
* Residual plots are a good way to visualize the errors in data. Data should be randomly scatter if you did it well.

<br />

## References:

[How to run Linear regression in Python scikit-Learn](https://bigdata-madesimple.com/how-to-run-linear-regression-in-python-scikit-learn/)

[Linear Regression in Python](https://realpython.com/linear-regression-in-python/)


<br />

## [<-- Back](README.md)
