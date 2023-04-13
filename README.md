# Advanced_Stats_Problems

# Comparison of Model Selection Methods
Problem Description

Permeability is an important factor for drug development as it measures the ability of a molecule to cross the cell membrane. In this project, we will compare different model selection methods to predict permeability using binary molecular predictors. The data can be obtained in R using the following commands:

```ruby
library(AppliedPredictiveModeling)
data(permeability)
```
Steps

Split the data set into a training set and a test set in a 70:30 split.
Filter out predictors with low frequencies using the nearZeroVar function from the caret package. Report the number of predictors left for modeling.

Fit a linear model using least squares on the training set and report the test error obtained.

Fit a ridge regression model on the training set with λ chosen by cross-validation. Report the test error obtained.

Fit a lasso model on the training set with λ chosen by cross-validation. Report the test error obtained, along with the number of non-zero coefficient estimates.

Fit a PCR model on the training set with M chosen by cross-validation. Report the test error obtained, along with the value of M selected by cross-validation.

Fit a PLS model on the training set with M chosen by cross-validation. Report the test error obtained, along with the value of M selected by cross-validation.

Commented on the results obtained. Compared the optimal number of latent variables in PLS and PCR, and compared the test errors resulting from these approaches.

# Problem 2

A loan offering company wants to build a default risk model to target high-risk customers early and prevent default events. The data consists of historical loan records for 2400 past customers, with 30 features and a binary outcome variable indicating whether the borrower has defaulted or not. There is also a test set with 600 customers and only the 30 features are provided.

Steps
Build a risk score (probability of default) for each customer in the test set using any tools.

Write up a report describing the steps taken and how the final model was selected. Indicate which variables were important in calculating the risk score.

Provide the Mean Absolute Error (MAE) of the loss on the test dataset.


# PCA Vs Least Squares
This is a project to compare the effectiveness of PCA and least squares regression algorithms in inferring linear relationships among data variables in the presence of noise. The analysis is done on a simple example of two variables, x and y, where the true relationship between the variables is y = 2x.

Functions

pca_recover

This function takes a vector X of xi’s and a vector Y of yi’s and returns the slope of the first component of the PCA (namely, the second coordinate divided by the first).

ls_recover

This function takes X and Y and returns the slope of the least squares fit.

Exercise
Sanity check

Set X = [.001, .002, .003, ..., 1] and Y = 2X. Make sure both functions return 2 as a sanity check.

Case 1
Consider the case when the elements of X and Y were chosen identically and independently at random in the square [0, 1] × [0, 1]. What would PCA recover, and what would LS recover?

Case 2
Consider the case where x is an independent (a.k.a. explanatory) variable, and we get noisy measurements of y. Fix X = [x1, x2, . . . , x1000] = [.001, .002, .003, . . . , 1]. For a given noise level c, let ˆyi = 2xi +N (0, c) = 2i/1000+N (0, c), and ˆY = [ˆy1, ˆy2, . . . , ˆy1000]. Make a scatter plot with c on the horizontal axis, and the output of pca_recover and ls_recover on the vertical axis. For each c in [0, 0.05, 0.1, . . . , .45, .5], take a sample ˆY , plot the output of pca_recover as a red dot, and the output of ls_recover as a blue dot. Repeat 30 times. You should end up with a plot of 660 dots, in 11 columns of 60, half red and half blue.

Case 3
We now examine the case where our data consists of noisy estimates of both x and y. For a given noise level c, let ˆxi = xi + N (0, c) = i/1000 + N (0, c) and ˆyi = yi + N (0, c) = 2i/1000 + N (0, c). For each c in [0, 0.05, 0.1, . . . , .45, .5], take a sample ˆX and ˆY , plot the output of pca_recover as a red dot, and the output of ls_recover as a blue dot. Repeat 30 times. You should have a plot with 330 red dots and 330 blue dots.

Conclusion

Which case does PCA do better? Why?

PCA performs better when there is noise in the dependent variable and the independent variable is noise-free. This is because PCA is more robust to noise in the data than least squares regression. PCA can identify the underlying structure of the data even when there is noise, while least squares regression is highly sensitive to noise and can produce unreliable results. In cases where both variables have noise, both PCA and least squares regression perform similarly, but PCA is still more robust to noise.

# Causal Inference Questions
This repository contains a set of questions and answers related to Causal Inference, a field of statistics that deals with inferring causality between variables in observational studies and experiments.

