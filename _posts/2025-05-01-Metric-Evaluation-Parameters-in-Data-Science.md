---
tags: Programming
---
In data science, we are dealing with a lot of data. The data is processed, modeled, and analysed based on the proper method. The important key of the analysis is an evaluation of the model. Is the model good enough to be used for predicting or estimating an output given by new input data? We use the statistical methods to evaluate model. Each of the methods has its own characteristic. Here, I share the common methods to asses the quality of model, hereafter I mentioned as the metric evaluation parameters.

## Mean Square Error (MSE)
- This metric calculate the average square residual between actual data ($$ y_i $$) and predicted data ($$ \hat y_i $$).
- The low MSE indicates the model is good enough.
- This method is sensitive to outliers, so make sure the data has removed the outliers.
- The metric can be calculated by using $$ MSE = \frac{1}{n} \sum_{i=1}^{n} (y_i - \hat{y}_i)^2 $$, where $$ n $$ is number of data

## Root Mean Square Error (RMSE)
- This metric calculate the root of average square residual between actual data ($$ y_i $$) and predicted data ($$ \hat y_i $$).
- This will give back the original unit of the data.
- The low RMSE indicates the model is good enough.
- This method is sensitive to outliers (same with the MSE), so make sure the data has removed the outliers.
- The metric can be calculated by using $$ RMSE = \sqrt{\frac{1}{n} \sum_{i=1}^{n} (y_i - \hat{y}_i)^2} $$, where $$ n $$ is number of data

## Mean Absolute Error (MAE)
- This metric calculate the average absolute residual between actual data ($$ y_i $$) and predicted data ($$ \hat y_i $$).
- The best MAE is close to zero. It means that the actual and predicted data are close to each other.
- This metric can be calculated by using $$ MAE = \frac{1}{n} \sum_{i=1}^{n} |y_i - \hat{y}_i| $$

## Mean Absolute Percentage Error (MAPE)
- This metric takes the basic of MAE's formula. It is enchanced to the precentage error calculation respect to the actual data ($$ y_i $$).
- It tells us how much the percentage error of the predicted data respect to the actual data.
- The lower percentage error indicates the good result.
- This metric can be calculated by using $$ MAE = \frac{100 \%}{n} \sum_{i=1}^{n} |\frac{y_i - \hat{y}_i} {y_i}| $$

## Pearson Correlation Coefficient
![pcc](https://upload.wikimedia.org/wikipedia/commons/3/34/Correlation_coefficient.png)
_The pichture by: [Kiatdd, CC BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0), via Wikimedia Commons_

- This metric is used to evaluate the correlation between two variables, Do both variables have correlation to each other? is it positive correlation or negative correlation?
- Let say we have variabel of $$ x $$ and $$ y $$. We do not know both variables are having correlation in the first place. So, we can check by using this metric as the following equation

$$ r = \frac{\sum_{i=1}^{n}(y_i - \bar{y})(\hat{y}_i - \bar{\hat{y}})}{\sqrt{\sum_{i=1}^{n}(y_i - \bar{y})^2} \sqrt{\sum_{i=1}^{n}(\hat{y}_i - \bar{\hat{y}})^2}} $$

where the $$ \hat y_i $$ is the predicted value, $$ \bar y_i $$ is the mean of actual data, $$ \bar {\hat y_i} $$ is the mean of predicted data, and $$ n $$ is number of data.

- If the $$ r $$ is close to the $$ 1 $$, the both variables are having positive correlation. The $$ y $$ increases as the $$ x $$ increases.
- Otherwise, If the $$ r $$ is close to the $$ -1 $$, the both variables are having negative correlation. The $$ y $$ decreases as the $$ x $$ increases.
- If the $$ r $$ is not more than 0.5, the both variables are not significant correlate.


