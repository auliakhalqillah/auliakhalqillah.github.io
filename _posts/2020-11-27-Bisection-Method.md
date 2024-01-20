---
layout: post
title: "Bisection Method"
description: Understanding the Bisection Method to find the root of a nonlinear equation
tags: Numerical-Method
---
## Bisection Method - Finding the Root of a Nonlinear Equation
### Introduction
A bisection method is one of the brackets methods to solve a root of equations problem numerically. This method is also called binary chopping or interval halving. The main idea of 
the bisection method is to find the root ($xr$) that is always divided in half between two ranges, $xi$ (initial boundary) and $xf$ (final boundary) by using Equation (1.1). By analytic process, 
the root will be produced when the function is equal to zero, $f(x) = 0$ and at least one root will be identified from a function. However, numerically the root of the function will be produced 
when the function of $f(x)$ is close to 0, (not exact to 0).

$xr = \frac {(xi+xf)} {2}$ eq 1.1

$error = |\frac {(xr - xrold)} {xrold}|$ eq 1.2

### Numerical Steps
```
a.	Set initial initial boundary xi, final boundary xf
b.	Check f(xi) * f(xf) < 0. If f(xi) * f(xf) > 0, the root is not in range xi to xf. So, you have to update new boundary. However, in this algorithm, the new boundary will be changed automatically. To do this automatically,
1.	Do while f(xi) * f(xf) > 0
2.	Check the f(xi) * f(xf) is exceed a limit of range, limrange = 1e12. If the f(xi) * f(xf) > limrange, update the initial value, xi = xi + 1 and check the condition again to number 1. Otherwise, if the f(xi) * f(xf) < limrange, update the final boundary, xf = xf – 1 and check the condition again to number 1.
3.	This process will stop when the f(xi) * f(xf) < 0
c.	Set the estimation root, xrold = 0 
d.	If the point b is TRUE, calculate the new root by using Equation (1.1)
e.	Calculating the relative error by using Equation (1.2)
f.	Set the limit of error, limit = 1e-10 and iteration, iter = 1
g.	Do while the error is greater the limit, error > limit or error is NaN:
1.	If f(xi)*f(xr) < 0, condition = 1, set the xf = xr, xrold = xr, calculate the new root of xr, and calculate new error.
2.	If f(xi)*f(xr) > 0, condition = 2, set the xi = xr, xrold = xr, calculate the new root of xr, and calculate new error.
3.	If f(xi)*f(xr) = 0, condition = 3, set the root xr = xr,
i.	If f(xr) = 0, set the root xr = xr.
ii.	Otherwise, if f(xr) is not 0, set the root xr = xi
set the xrold = xr
		update iter = iter + 1
h.	The process will stop when error < limit.

```
