# LASSO-Algorithm
Implemented  the LASSO algorithm in 'R' and compared algorithm with other feature selection methods
There is one R code file that are used for this algorithm:
This code file contains the lasso implementation, the bootstrapping 
approximation of standard error and the simulation part.

How to run the program:
load the lasso code.R file in R and execute.

Output:
You will see the lasso algorithm applied to the standardized Prostate data.
The result about the coefficients, standard error, z values will be displayed.
The boxplots about all the coefficients using bootstrapping samples(200 times)
is also shown.
The final plots show the comparison of the estimates calculated by OLS, lasso function 
implemented in the R code and the Ridge regression.

Instruction on applying lasso method to other data sets:
We assume that the data is clean (no N/A or missing values) and assume all the assumptions for the general regression techniques.

a) We provide a function “standize_data” to standardize the data set.
	usage: standize_data(X) where X is the dataset not including the response variable

b) The lasso coefficient (without intercept) can be calculated using the function “lassoImp” 
with given input matrix, response variable and t constraint.
	usage: lassoImp(X,Y,s)  where X is the matrix of the predictors (model matrix in case of factored variables)
					Y is the matrix of the response Variable and
					s is the constraint >= 0  (not normalised).
if the constraint s is normalised, is should be converted into non-normalised form by 
multiplying it by the sum of absolute values of the ols estimates.


c) the lasso intercept coefficient can be computed by extracting the first element 
from the result of function ”calc_olsbeta” with given input matrix and response variable.
	usage: calc_olsbeta(X,Y) where X is the matrix of the predictors (model matrix in case of factored variables) 
					Y is the matrix of the response Variable.

d) If standard error and z-score are also required, prepare the design matrix and lasso coefficients with intercept.
Then use “calc_se_Z” function, (with design matrix(whose first column are all 1), response variable and coefficients with intercept) to calculate standard error and z-score of the variable and display all of them in a table.
	usage: calc_se_Z(X,Y,b) where X is the matrix of the predictors (model matrix in case of factored variables) 
					Y is the matrix of the response Variable and
					b is the beta vector including the intercept.

