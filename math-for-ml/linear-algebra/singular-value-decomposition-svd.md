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

## Calculate Singular-Value Decomposition using NumPy

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

**Note**: **svd\(\)** returns a **sigma vector** which needs to be transformed into a `m x n` matrix for multiplication.  
         - Convert sigma vector into **diagonal matrix** `n x n` using **diag\(\)**  
         - Create a `m x n` empty/zero **Sigma matrix**  
         - Populate the **Sigma matrix** with `n x n` diagonal matrix

```python
from numpy import array
from numpy import diag
from numpy import dot
from numpy import zeros
from numpy.linalg import svd

A = array([[1, 2], [3, 4], [5, 6]])
print('-------------------')
print('Original Matrix')
print(A)

U, d, VT = svd(A)
print('-------------------')
print('2 element Sigma vector')
print(d)

# Convert Sigma vector into diagonal matrix
D = diag(d)
print('-------------------')
print('Diagonal matrix with dimension 2x2 or nxn')
print(D)

# Create an m x n Sigma matrix dimension
Sigma = zeros((A.shape[0], A.shape[1]))
print('-------------------')
print('Empty m x n Sigma matrix')
print(Sigma)

# Populate Sigma matrix with n x n diagonal matrix
Sigma[:A.shape[1], :A.shape[1]] = D
print('-------------------')
print('Sigma matrix m x n')
print(Sigma)

# Reconstruct original matrix
O = U.dot(Sigma.dot(VT))
print('-------------------')
print('Reconstructed original matrix m x n')
print(O)
```

```text
-------------------
Original Matrix
[[1 2]
 [3 4]
 [5 6]]
-------------------
2 element Sigma vector
[9.52551809 0.51430058]
-------------------
Diagonal matrix with dimension 2x2 or nxn
[[9.52551809 0.        ]
 [0.         0.51430058]]
-------------------
Empty m x n Sigma matrix
[[0. 0.]
 [0. 0.]
 [0. 0.]]
-------------------
Sigma matrix m x n
[[9.52551809 0.        ]
 [0.         0.51430058]
 [0.         0.        ]]
-------------------
Reconstructed original matrix m x n
[[1. 2.]
 [3. 4.]
 [5. 6.]]
```



Link:  
[Gentle Introduction to Singular-Value Decomposition for Machine Learning](https://machinelearningmastery.com/singular-value-decomposition-for-machine-learning/)

