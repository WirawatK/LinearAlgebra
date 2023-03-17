# LinearAlgebra
This project is a part of PSI2023 Numerical Method course coordinate by Eric and Dustin. Further reading [Data analysis recipes: Fitting a model to data](arXiv:1008.4686v1). This code works on Julia 1.8.5 `(lastest updated 03/16/23)`.

We will investigate in the following: evaluate sin(x) via polynomials using a least square approach, the error of approximate function, antisymmetric ploynomials, and derivative function.

To approximate sin(x), we create a polynomials series matrix, A, to contain the decreatized of x to the power from 0 to pmax (highest order). Then, we solved the coefficient through a least square method:

$$
A*coeffs = sin(x)
$$

Then, we can solve for coeffs by ("A" might not be a square matrix so we use pseudo inverse)

$$
coeffs = A^T sin(x) / (A^TA)
$$

See https://textbooks.math.gatech.edu/ila/least-squares.html for more detail.

In the notebook, it contains the above numerical implementation in Julia as function `approxsin(p_max)` and we will use it to study the error compared to analytic sin(x) function from this function using L2 norm. In order to get more accuracy, we can exploit from the fact that sin(x) can be expaned as only antisymmetric polynomials (1,3,5,...). We then define the new function `Modapproxsin(p_max)` to show that we can improve performance of approximation function. 

![download](https://user-images.githubusercontent.com/108566311/225795423-9969b286-5526-41c6-b438-966a8915f6cb.png)

Finally, we will create the way to do derivative using Linear Algebra by playing with index. We will test our method by defining function `dapproxsin(p_max)` and compared it to approximate cos(x) function `dapproxsin(p_max)`



