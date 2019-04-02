# Matrix Arithmetic

## Matrix Introduction

**Matrix** is a two-dimensional array of numbers often denoted with uppercase letter. **Matrix** is comprised of rows_\(m\)_ and columns_\(n\)_.

**Vector** may be considered a **matrix** with one column and multiple rows.

### Create a matrix using NumPy

```python
from numpy import array
# create a matrix
C = array([['Nepal', 'Kathmandu', 29.3], ['United States', 'Washington D.C', 327.16]])
print(C)
```

```text
[['Nepal' 'Kathmandu' '29.3']
 ['United States' 'Washington D.C' '327.16']]
```

## Matrix Addition

Two matrices with the same dimensions can be added to create a new third matrix. `C = A + B`

$$
A=\begin{bmatrix}a_{11} \hspace{0.2cm} a_{12}\hspace{0.2cm}  .. \hspace{0.2cm} a_{1n}
\\ a_{21} \hspace{0.2cm} a_{22}\hspace{0.2cm}  .. \hspace{0.2cm} a_{2n} 
\\ .. 
\\ a_{m1} \hspace{0.2cm} a_{m2}\hspace{0.2cm}  .. \hspace{0.2cm} a_{mn} \end{bmatrix},
B=\begin{bmatrix}b_{11} \hspace{0.2cm} b_{12}\hspace{0.2cm}  .. \hspace{0.2cm} b_{1n}
\\ b_{21} \hspace{0.2cm} b_{22}\hspace{0.2cm}  .. \hspace{0.2cm} b_{2n} 
\\ ..
\\ b_{m1} \hspace{0.2cm} b_{m2}\hspace{0.2cm}  .. \hspace{0.2cm} b_{mn} \end{bmatrix}
\newline
C=\begin{bmatrix}a_{11} + b_{11} \hspace{0.2cm} a_{12} + b_{12}\hspace{0.2cm}  .. \hspace{0.2cm} a_{1n} + b_{1n}
\\ a_{21} + b_{21} \hspace{0.2cm} a_{22} + b_{22} \hspace{0.2cm}  .. \hspace{0.2cm} a_{2n} + b_{2n}
\\..
\\ a_{m1} + b_{m1} \hspace{0.2cm} a_{m2} + b_{m2}\hspace{0.2cm}  .. \hspace{0.2cm} a_{mn} + b_{mn} \end{bmatrix}
$$

```python
from numpy import array

A = array([[1, 2, 3], [4, 5, 6]])
B = array([[1, 2, 3], [4, 5, 6]])
C = A + B
print(C)
```

```text
[[ 2  4  6]
 [ 8 10 12]]
```

## Matrix-Scalar Multiplication

A matrix can be multiplied by a scalar represented as`C = A . b` where b is a scalar. Note: use '**\*'** in **Numpy** for matrix multiplication

$$
A=\begin{bmatrix}a_{11} \hspace{0.2cm} a_{12}\hspace{0.2cm}  .. \hspace{0.2cm} a_{1n}
\\ a_{21} \hspace{0.2cm} a_{22}\hspace{0.2cm}  .. \hspace{0.2cm} a_{2n} 
\\ .. 
\\ a_{m1} \hspace{0.2cm} a_{m2}\hspace{0.2cm}  .. \hspace{0.2cm} a_{mn} \end{bmatrix},
b=scalar
\newline
C=\begin{bmatrix}a_{11} * b  \hspace{0.2cm} a_{12}  * b\hspace{0.2cm}  .. \hspace{0.2cm} a_{1n}  * b
\\ a_{21} * b \hspace{0.2cm} a_{22} * b \hspace{0.2cm}  .. \hspace{0.2cm} a_{2n} * b
\\..
\\ a_{m1} * b \hspace{0.2cm} a_{m2} * b\hspace{0.2cm}  .. \hspace{0.2cm} a_{mn} * b \end{bmatrix}
$$

```python
from numpy import array
A = array([[1, 2, 3], [4, 5, 6]])
b = 2
C = A * b
print(C)
```

```text
[[ 2  4  6]
 [ 8 10 12]]
```

## Matrix-Vector Multiplication

## Matrix Multiplication \(Hadamard Product\)

## Matrix-Matrix Multiplication \(Dot Product\)



Link:  
[Introduction to Matrices and Matrix Arithmetic for Machine Learning](https://machinelearningmastery.com/introduction-matrices-machine-learning/)

