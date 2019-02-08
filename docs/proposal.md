# Overview

This package is developed to help users calculate correlation coefficients and covariance matrix of a given data with missing values. In order to implement correlation coefficients and covariance matrix, the standard deviation of the data is needed however the world of data is not always clean and tidy. `base` R fails to return standard deviation and calculation of the correlation coefficients when the data has missing values. This package aims to overcome this obstacle and help users handle missing values when calculating correlation coefficients and covariance matrix. `CorrR` uses likewise deletion method to handle missing values: removing the rows of a data frame where the missing values are present.

*Note: If the course timeline permits, `CorrR` will handle missing values via single manipulation with mean value: replacing the missing values with the mean of existing values.* 


## Standard Deviation (`std_plus`)

Standard deviation calculates how close the data points to the mean, in which an insight for the variation of the data points.

<a href="https://www.codecogs.com/eqnedit.php?latex=s&space;=&space;\sqrt{\frac{\sum(x-\overline{x})^2}{n-1}}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?s&space;=&space;\sqrt{\frac{\sum(x-\overline{x})^2}{n-1}}" title="s = \sqrt{\frac{\sum(x-\overline{x})^2}{n-1}}" /></a>

 `std_plus` will omit frustration from workflows.

 ```R
  std_plus(input_data):
   '''
   Standard deviation calculates how close the data
   points are to the mean and the variation of the data points.


   parameters:
   -----------
   input_data (float):  a list or an array of a random variable

   Return:
   ------
   std_value (float): the value of standard deviation of the input data
   '''
 ```
## Correlation Coefficients (`corr_plus`)

Correlation coefficients calculates the relationship between two variables as well as the magnitude of this relationship.


<a href="https://www.codecogs.com/eqnedit.php?latex=r&space;=&space;\frac{1}{n-1}(\frac{\sum(x-\overline{x})(y-\overline{y})}{s_{x}s_{y}})" target="_blank"><img src="https://latex.codecogs.com/gif.latex?r&space;=&space;\frac{1}{n-1}(\frac{\sum(x-\overline{x})(y-\overline{y})}{s_{x}s_{y}})" title="r = \frac{1}{n-1}(\frac{\sum(x-\overline{x})(y-\overline{y})}{s_{x}s_{y}})" /></a>

```R
corr_plus(var1, var2):
  '''
  Correlation coefficients calculates the relationship between
   two variables as well as the magnitude of this relationship.

  parameters:
  -----------
  var1 (float): a list or an array of the first random variable
  var2 (float): a list or an array of the second random variable

  Return:
  -------
  corr (float): a single value correlation between two variables
  '''
```


## Covariance Matrix (`cov_mx`)

Covariance measures the extent to which corresponding observations from two sets of ordered variables vary in a direction.
<a href="https://www.codecogs.com/eqnedit.php?latex=Cov(X,Y)&space;=&space;\frac{\sum(x-\overline{x})(y-\overline{y})}{N}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?Cov(X,Y)&space;=&space;\frac{\sum(x-\overline{x})(y-\overline{y})}{N}" title="Cov(X,Y) = \frac{\sum(x-\overline{x})(y-\overline{y})}{N}" /></a>

A Covariance matrix displays the variance and covariance together. The diagonal elements represent the variances and the covariances are represented by the other elements in the matrix shown below.



<a href="https://www.codecogs.com/eqnedit.php?latex=\Sigma&space;=&space;\begin{bmatrix}Var(X_1)&space;&&space;Cov(X_1&space;X_2)&space;&\cdots&\cdots&space;&\cdots&space;&&space;Cov(X_1&space;X_k)\\&space;Cov(X_2&space;X_1)&space;&Var(X_2)&&space;\cdots&space;&\cdots&space;&\cdots&space;&&space;\cdots\\&space;\cdots&space;&&space;\cdots&space;&\ddots&space;&\cdots&space;&\cdots&space;&&space;\cdots\\&space;\cdots&space;&&space;\cdots&space;&\cdots&space;&\ddots&space;&\cdots&space;&&space;\cdots\\&space;Cov(X_{k-1}&space;X_1)&space;&&space;\cdots&space;&\cdots&space;&\cdots&space;&Var(X_{k-1})&space;&&space;\cdots\\&space;Cov(X_k&space;X_1)&space;&&space;Cov(X_k&space;X_2)&space;&\cdots&space;&\cdots&space;&\cdots&space;&&space;Var(X_k)\\\end{bmatrix}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\Sigma&space;=&space;\begin{bmatrix}Var(X_1)&space;&&space;Cov(X_1&space;X_2)&space;&\cdots&\cdots&space;&\cdots&space;&&space;Cov(X_1&space;X_k)\\&space;Cov(X_2&space;X_1)&space;&Var(X_2)&&space;\cdots&space;&\cdots&space;&\cdots&space;&&space;\cdots\\&space;\cdots&space;&&space;\cdots&space;&\ddots&space;&\cdots&space;&\cdots&space;&&space;\cdots\\&space;\cdots&space;&&space;\cdots&space;&\cdots&space;&\ddots&space;&\cdots&space;&&space;\cdots\\&space;Cov(X_{k-1}&space;X_1)&space;&&space;\cdots&space;&\cdots&space;&\cdots&space;&Var(X_{k-1})&space;&&space;\cdots\\&space;Cov(X_k&space;X_1)&space;&&space;Cov(X_k&space;X_2)&space;&\cdots&space;&\cdots&space;&\cdots&space;&&space;Var(X_k)\\\end{bmatrix}" title="\Sigma = \begin{bmatrix}Var(X_1) & Cov(X_1 X_2) &\cdots&\cdots &\cdots & Cov(X_1 X_k)\\ Cov(X_2 X_1) &Var(X_2)& \cdots &\cdots &\cdots & \cdots\\ \cdots & \cdots &\ddots &\cdots &\cdots & \cdots\\ \cdots & \cdots &\cdots &\ddots &\cdots & \cdots\\ Cov(X_{k-1} X_1) & \cdots &\cdots &\cdots &Var(X_{k-1}) & \cdots\\ Cov(X_k X_1) & Cov(X_k X_2) &\cdots &\cdots &\cdots & Var(X_k)\\\end{bmatrix}" /></a>


```R
cov_mx(matrix):
  '''
  Calculate covariance measures the extent to which corresponding observations from two sets of ordered variables vary in a direction.

  parameters:
  -----------
  matrix (float): a matrix that contains one or more than one random variable

  Return:
  -------
  cov_matrix (float): a matrix that contains the correlation between random variables in the input matrix
  '''
  ```


### How does `CorrR` package fits into the R ecosystem?

Following functions are already present in R ecosystem. However, missing values are not being handles for the following functions and `CorrR` package will implement calculation of standard deviation, correlation coefficients and covariance matrix.

  R Standard Deviation:
  https://stat.ethz.ch/R-manual/R-devel/library/stats/html/sd.html

  R Correlation Coefficients:
  https://stat.ethz.ch/R-manual/R-devel/library/stats/html/cor.html

  R Covariance Matrix:
  https://stat.ethz.ch/R-manual/R-devel/library/stats/html/cor.html
