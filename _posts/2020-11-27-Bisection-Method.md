---
layout: post
title: "Bisection Method"
description: Understanding the Bisection Method to find the root of a nonlinear equation
tags: Numerical-Method
---
## Bisection Method - Finding the Root of a Nonlinear Equation
<p align="center">
	<img src="https://github.com/auliakhalqillah/Bisection-Method/blob/master/Bisection2_result.png" width="500" height="400" />
</p>

### Introduction
A bisection method is one of the brackets methods to solve a root of equations problem numerically. This method is also called binary chopping or interval halving. The main idea of 
the bisection method is to find the root ($xr$) that is always divided in half between two ranges, $xi$ (initial boundary) and $xf$ (final boundary) by using Equation (1.1). By analytic process, 
the root will be produced when the function is equal to zero, $f(x) = 0$ and at least one root will be identified from a function. However, numerically the root of the function will be produced 
when the function of $f(x)$ is close to 0, (not exact to 0).

$xr = \frac {(xi+xf)} {2}$ eq 1.1

$error = |\frac {(xr - xrold)} {xrold}|$ eq 1.2

### Numerical Steps
```
a. Set initial initial boundary xi, final boundary xf
b. Check f(xi) * f(xf) < 0. If f(xi) * f(xf) > 0, the root is not in the range xi to xf. So, you have to update the new boundary. However, in this algorithm, the new boundary will be changed automatically. To do this automatically,
	1. Do while f(xi) * f(xf) > 0
	2. Check the f(xi) * f(xf) is exceed a limit of range, limrange = 1e12. If the f(xi) * f(xf) > limrange, update the initial value, xi = xi + 1 and check the condition again to
	number 1. Otherwise, if the f(xi) * f(xf) < limrange, update the final boundary, xf = xf – 1, and check the condition again to number 1.
	3. This process will stop when the f(xi) * f(xf) < 0
c. Set the estimation root, xrold = 0 
d. If the point b is TRUE, calculate the new root by using Equation (1.1)
e. Calculating the relative error by using Equation (1.2)
f. Set the limit of error, limit = 1e-10 and iteration, iter = 1
g. Do while the error is greater than the limit, error > limit or error is NaN:
	1. If f(xi)*f(xr) < 0, condition = 1, set the xf = xr, xrold = xr, calculate the new root of xr, and calculate the new error.
	2. If f(xi)*f(xr) > 0, condition = 2, set the xi = xr, xrold = xr, calculate the new root of xr, and calculate the new error.
	3. If f(xi)*f(xr) = 0, condition = 3, set the root xr = xr,
		i. If f(xr) = 0, set the root xr = xr.
		ii. Otherwise, if f(xr) is not 0, set the root xr = xi, set the xrold = xr
		update iter = iter + 1
h. The process will stop when error < limit.
```

### Example
Given a function of $f(x) = x^2-2x+1$. By using bisection method to solve this equation, set the initial boundary $xi = -3$, final boundary $xf = 3$, limit $range = 1e12$, and limit of $error = 1e-10$. 

__Answer__
```
iter    xi       	      xf       		f(xi)          f(xf)      	xrold       	xr           f(xr)		error          conditioin
1    -1.000000000       1.00000000       4.00000000       0.00000000      -1.00000000       0.00000000       1.00000000       1.00000000               2
2     0.000000000       1.00000000       1.00000000       0.00000000       0.00000000      0.500000000      0.250000000             Infinity           2
3     0.500000000       1.00000000      0.250000000       0.00000000      0.500000000      0.750000000       6.25000000E-02  0.500000000               2
4     0.750000000       1.00000000       6.25000000E-02   0.00000000      0.750000000      0.875000000       1.56250000E-02  0.166666672               2
5     0.875000000       1.00000000       1.56250000E-02   0.00000000      0.875000000      0.937500000       3.90625000E-03   7.14285746E-02           2
6     0.937500000       1.00000000       3.90625000E-03   0.00000000      0.937500000      0.968750000       9.76562500E-04   3.33333351E-02           2
7     0.968750000       1.00000000       9.76562500E-04   0.00000000      0.968750000      0.984375000       2.44140625E-04   1.61290318E-02           2
8     0.984375000       1.00000000       2.44140625E-04   0.00000000      0.984375000      0.992187500       6.10351562E-05   7.93650839E-03           2
9     0.992187500       1.00000000       6.10351562E-05   0.00000000      0.992187500      0.996093750       1.52587891E-05   3.93700786E-03           2
10    0.996093750       1.00000000       1.52587891E-05   0.00000000      0.996093750      0.998046875       3.81469727E-06   1.96078443E-03           2
11    0.998046875       1.00000000       3.81469727E-06   0.00000000      0.998046875      0.999023438       9.53674316E-07   9.78473574E-04           2
12    0.999023438       1.00000000       9.53674316E-07   0.00000000      0.999023438      0.999511719       2.38418579E-07   4.88758553E-04           2
13    0.999511719       1.00000000       2.38418579E-07   0.00000000      0.999511719      0.999755859       5.96046448E-08   2.44259892E-04           2
14    0.999755859       1.00000000       5.96046448E-08   0.00000000      0.999755859      0.999877930       0.00000000       1.22100129E-04           2
15    0.999755859       1.00000000       5.96046448E-08   0.00000000      0.999877930      0.999877930       0.00000000       0.00000000               3
```
By using the bisection method after 15 times iterations of the process, the root of f(x) = x2-2+1 is found around 0.999877930. It is not exactly equal to 1 but close to 1 with a range of error 0.000244 – 0. When the root of 0.999877930 is substituted to the f(x), the real result is 1.4901e-08, but the program result above the f(x) = 0. This is because the process of (0.9998779302)-(2x0.999877930) = -0.999999985098915 and in Fortran95, it will be rounded to -1. So, in Fortran 95 the function of f(0.999877930) = (0.9998779302)-(2x0.999877930)+1 = -1+1= 0. The program code of this method has been implemented in Fortran 95 and can be downloaded [here](https://github.com/auliakhalqillah/Bisection-Method)

### Reference
1. [Chapra, S (2014) - Numerical Methods for Engineers](https://books.google.co.id/books/about/Numerical_Methods_for_Engineers.html?id=3GpzCgAAQBAJ&redir_esc=y)
