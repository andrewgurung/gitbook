# Singular-Value Decomposition\(SVD\)

**Singular-Value Decomposition**\(SVD\) is a matrix decomposition/factorization method for reducing a given matrix into its constituent elements.

**Note**: All matrices have an **SVD**, which makes it more stable than other methods, such as the eigendecomposition.

$$
A = U . \Sigma.V^T
$$

$$A$$:The real **m x n** matrix that we wish to decompose  
$$U$$: **m x m** matrix where matrix **U** is also known as **left-singlular vectors** of A  
$$\Sigma$$: **m x n** diagonal matrix where the diagonal values are known as **singular values**  
$$V^T$$: Transpose of an **n x n** matrix where matrix **V** is also **right-singular vectors** of A

## Calculate Singular-Value Decomposition using SciPy

```python
# Calculate Singular-Value Decomposition Using SciPy
from numpy import array
from numpy.linalg import svd

A = array([[1, 2], [3, 4], [5, 6]])
print('-------------------')
print('Original Matrix to be decomposed')
print(A)

U, d, VT = svd(A)
print('-------------------')
print('U Matrix')
print(U)

print('-------------------')
print('2 element Sigma vector')
print(d)

print('-------------------')
print('VT Matrix')
print(VT)
```

```text
-------------------
Original Matrix to be decomposed
[[1 2]
 [3 4]
 [5 6]]
-------------------
U Matrix
[[-0.2298477   0.88346102  0.40824829]
 [-0.52474482  0.24078249 -0.81649658]
 [-0.81964194 -0.40189603  0.40824829]]
-------------------
2 element Sigma vector
[9.52551809 0.51430058]
-------------------
VT Matrix
[[-0.61962948 -0.78489445]
 [-0.78489445  0.61962948]]
```

## Reconstruct Matrix from SVD



Link:  
[Gentle Introduction to Singular-Value Decomposition for Machine Learning](https://machinelearningmastery.com/singular-value-decomposition-for-machine-learning/)

