# Matrix Operations

**Matrix operations** are used in many machine learning algorithms. Linear algebra makes matrix operations fast and easy, especially when training on GPUs.

## Transpose

A transpose is a _matrix_ which is formed by turning all the rows of a given _matrix_ into columns and vice-versa represented as `A^T`.

$$
A=\begin{bmatrix}
a_{11} \hspace{0.2cm} a_{12}
\\ a_{21} \hspace{0.2cm} a_{22}
\\ a_{31} \hspace{0.2cm} a_{32}
\end{bmatrix}, 
A^T=\begin{bmatrix}
a_{11} \hspace{0.2cm} a_{21}\hspace{0.2cm} a_{31}
\\ a_{12} \hspace{0.2cm} a_{22}\hspace{0.2cm} a_{32}
\end{bmatrix}
$$

```python
from numpy import array
A = array([[1, 2], [3, 4], [5, 6]])
C = A.T
print(C)
```

```text
[[1 3 5]
 [2 4 6]]
```

## Inversion

## Trace

## Determinant

![Calculating determinant of a matrix](../../../.gitbook/assets/determinant.png)

## Rank

**Calculating rank mathematically:**  
[https://www.youtube.com/watch?v=59z6eBynJuw](https://www.youtube.com/watch?v=59z6eBynJuw)

Link:  
[https://machinelearningmastery.com/matrix-operations-for-machine-learning/](https://machinelearningmastery.com/matrix-operations-for-machine-learning/)

