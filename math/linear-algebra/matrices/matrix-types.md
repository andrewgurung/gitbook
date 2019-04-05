# Matrix types

## Square Matrix

A matrix where the number of rows\(m\) equals to the number of columns\(n\).

**Main diagonal**: The vector of values along the diagonal of the matrix from the top left to the bottom right. $$(a_{11}, a_{22}, a_{33})$$ 

$$
Square\hspace{0.1cm}Matrix\hspace{0.1cm}of\hspace{0.1cm}order\hspace{0.1cm}3;\hspace{0.1cm}A=\begin{bmatrix}
a_{11} \hspace{0.2cm} a_{12} \hspace{0.2cm} a_{13}
\\ a_{21} \hspace{0.2cm} a_{22}\hspace{0.2cm} a_{23}
\\ a_{31} \hspace{0.2cm} a_{32}\hspace{0.2cm} a_{33}
\end{bmatrix}
$$

## Symmetric Matrix

A type of square matrix where the top-right triangle is the same as the bottom-left triangle.  
**Note:** The axis of symmetry is always the **main diagonal.**

$$
A=\begin{bmatrix}
1 \hspace{0.2cm} 2 \hspace{0.2cm} 3\hspace{0.2cm}4\hspace{0.2cm}5
\\ 2\hspace{0.2cm}1\hspace{0.2cm}2\hspace{0.2cm}3\hspace{0.2cm}4
\\ 3\hspace{0.2cm}2\hspace{0.2cm}1\hspace{0.2cm}2\hspace{0.2cm}3
\\ 4\hspace{0.2cm}3\hspace{0.2cm}2\hspace{0.2cm}1\hspace{0.2cm}2
\\ 5\hspace{0.2cm}4\hspace{0.2cm}3\hspace{0.2cm}2\hspace{0.2cm}1
\end{bmatrix}, A = A^T
$$

## Triangular Matrix

A type of square matrix that has values in the upper-right or lower-left triangle and filled with zeros in the rest.

$$
Upper Triangular Matrix A=\begin{bmatrix}
1 \hspace{0.2cm} 2 \hspace{0.2cm} 3
\\ 0 \hspace{0.2cm} 2\hspace{0.2cm} 3
\\ 0 \hspace{0.2cm} 0\hspace{0.2cm} 3
\end{bmatrix},
Lower Triangular Matrix B=\begin{bmatrix}
1 \hspace{0.2cm} 0 \hspace{0.2cm} 0
\\ 1 \hspace{0.2cm} 2\hspace{0.2cm} 0
\\ 1 \hspace{0.2cm} 2\hspace{0.2cm} 3
\end{bmatrix}
$$

```python
from numpy import array
from numpy import tril
from numpy import triu

M = array([[1, 2, 3], [1, 2, 3], [1, 2, 3]])
upper = triu(M)
lower = tril(M)
print(upper)
print(lower)
```

```text
[[1 2 3]
 [0 2 3]
 [0 0 3]]
 
 [[1 0 0]
 [1 2 0]
 [1 2 3]]
```

## Diagonal Matrix

A matrix where values outside the main diagonal have zero value; often represented as **D**.  
**Note**: A diagonal matrix does not have to be square.

$$
D=\begin{bmatrix}
1 \hspace{0.2cm} 0 \hspace{0.2cm} 0
\\ 0 \hspace{0.2cm} 2\hspace{0.2cm} 0
\\ 0 \hspace{0.2cm} 0\hspace{0.2cm} 3
\end{bmatrix},
D=\begin{bmatrix}
1 \hspace{0.2cm} 0 \hspace{0.2cm} 0 \hspace{0.2cm} 0 
\\ 0 \hspace{0.2cm} 2\hspace{0.2cm} 0 \hspace{0.2cm} 0 
\\ 0 \hspace{0.2cm} 0\hspace{0.2cm} 3 \hspace{0.2cm} 0 
\\ 0 \hspace{0.2cm} 0\hspace{0.2cm} 0 \hspace{0.2cm} 4 
\\ 0 \hspace{0.2cm} 0\hspace{0.2cm} 0 \hspace{0.2cm} 0 
\end{bmatrix}
$$

```python
from numpy import array
from numpy import diag
M = array([[1, 2, 3], [1, 2, 3], [1, 2, 3]])

# extract diagonal vector
d = diag(M)
print(d)

# create diagonal matrix from diagonal vector
D = diag(d)
print(D)
```

```text
[1 2 3]

[[1 0 0]
 [0 2 0]
 [0 0 3]]
```

## Identity Matrix

## Orthogonal Matrix

Link:  
- [Introduction to Matrix Types in Linear Algebra for Machine Learning](https://machinelearningmastery.com/introduction-to-types-of-matrices-in-linear-algebra/)

