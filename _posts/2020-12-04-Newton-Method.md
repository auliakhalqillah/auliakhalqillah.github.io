---
layout: post
title: "Newton's Method"
description: Understanding the Newton's Method to find the root of a nonlinear equation
tags: Numerical-Method
---
## Newton's Method - Finding the Root of a Nonlinear Equation
### Introduction
Newton’s method is the fastest method for finding the root. This method uses f(x) 's first derivative and initial root estimation. Therefore, this method requires an analytical process
to determine the first derivative of $f(x)$. The root estimation ($x$) can be calculated by using Equation (1).

$x_r = x_{initial} - \frac {f(x_{initial})} {f'(x_{initial})}$ Equation 1

$error = |\frac {{x_r} - x_{rold}} {x_{rold}}|$  Equation 2

By using this method, the root estimation can be convergence or not convergence. If the root estimation is convergence that means it is close to the expected root of $f(x)$.
Otherwise, if the root estimation is not convergence that means it is far to the expected root of $f(x)$, so you have to input another initial root estimation again.

### Numerical Steps
```
a. Set initial root estimation, x
b. Set the error limit, error = 1e-6
c. Set initial iter, iter = 1
d. Calculate the initial root estimation by using Equation (1)
e. Set xrold is equal to x
f. Set x is equal to root estimation (xr)
g. Calculate the error by using equation (2)
h. If the error is less than the limit of error OR the root estimation is NaN, the root estimation is the xrold and the error is zero. Otherwise, point i is processed.
i. Do while error greater than equal to the limit of error:
  1. Calculating the Newton’s Method by using Equation (1)
  2. Set xrold is equal to x
  3. Set x is equal to root estimation (xr)
  4. Calculate the error by using equation (2)
  5. If the absolute function of f(x) is less than equal to the error limit, the root is convergence. Otherwise, if the absolute function of f(x) is greater than or equal to the error, the root is not convergence.
  6. Show the results: iter, x, f(x)
  7. Update iteration, iter = iter + 1
```

### Example
Given a function of $f(x) = x^2-2x+1$. By using Newton’s Method, set the maximum iteration (`maxiter`) equal to 100, and set the initial root estimation ($x = 3$).

After 100 times iterations, the final root is 1.00024414 (precision in Fortran) by using Newton’s Method, where the $f(x)$ is 0 and convergence to the expected root of 1.
The program code of this method has been implemented in Fortran 95 and can be downloaded [here](https://github.com/auliakhalqillah/Newton-sMethod)

### Reference
1. [Jeffrey R. Chasnov(2012), Numerical Methods](https://www.math.hkust.edu.hk/~machas/numerical-methods.pdf)

