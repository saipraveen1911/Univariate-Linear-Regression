# Implementation of Univariate Linear Regression
## Aim:
To implement univariate Linear Regression to fit a straight line using least squares.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Get the independent variable X and dependent variable Y.
2.	Calculate the mean of the X -values and the mean of the Y -values.
3.	Find the slope m of the line of best fit using the formula.
 ![eqn1](./eq1.jpg)
4.	Compute the y -intercept of the line by using the formula:
![eqn2](./eq2.jpg)  
5.	Use the slope m and the y -intercept to form the equation of the line.
6.	Obtain the straight line equation Y=mX+b and plot the scatterplot.
## Program
```
import numpy as np
import matplotlib.pyplot as plt

# Preprocessing input data
X = np.array([0, 1, 2, 3, 4, 5, 6, 7, 8, 9])
Y = np.array([1, 3, 2, 5, 7, 8, 8, 9, 10, 12])

# Scatter plot of input data
plt.scatter(X, Y)
plt.show()

# Building the model
X_mean = np.mean(X)
Y_mean = np.mean(Y)

num = 0
den = 0

for i in range(len(X)):
    num += (X[i] - X_mean) * (Y[i] - Y_mean)
    den += (X[i] - X_mean) ** 2

m = num / den          # slope
c = Y_mean - m * X_mean  # intercept

print(m, c)

# Making predictions
Y_pred = m * X + c
print(Y_pred)

# Plotting regression line
plt.scatter(X, Y)
plt.scatter(X, Y_pred, color='red')
plt.plot([min(X), max(X)], [min(Y_pred), max(Y_pred)], color='red')
plt.show()
```
## Output

![Ex 9(a) Maths for AI](https://github.com/user-attachments/assets/941e1a2e-b5df-4ac3-b9c2-76386ac645cf)

![Ex 9(b) Maths for AI](https://github.com/user-attachments/assets/f368cf46-f368-4642-a0d9-7f679e7557bc)

![Ex 9(c) Maths for AI](https://github.com/user-attachments/assets/9c3e27d3-13ff-46dd-b437-b67b40e34053)


## Result
Thus the univariate Linear Regression was implemented to fit a straight line using least squares.
