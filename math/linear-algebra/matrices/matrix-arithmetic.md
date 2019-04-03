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

A matrix can be multiplied by a scalar represented as**`C = A . b`** where b is a scalar. Note: use '**\*'** in **Numpy** for matrix multiplication

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

A matrix can be multiplied by a vector represented as **`C = A . v`** where v is a vector given it follows the rule of matrix multiplication.

#### Rule of matrix multiplication

For example, matrix **A** has the dimensions **m** rows and **n** columns and matrix **B** has the dimensions **n** and **k**. The **n** columns in **A** and **n** rows **b** are equal. The result is a new matrix with **m** rows and **k** columns.

$$
C(m,k) = A(m,n) * B(n,k)
$$

Example of Matrix-Vector multiplication:

$$
A=\begin{bmatrix}
a_{11} \hspace{0.2cm} a_{12}
\\ a_{21} \hspace{0.2cm} a_{22}
\\ a_{31} \hspace{0.2cm} a_{32}
\end{bmatrix},
v=\begin{bmatrix}
v_{1}
\\ v_{2}
\end{bmatrix}
\newline
C=\begin{bmatrix}
a_{11}  * v_{1} + a_{12} * v_{2}
\\ a_{21}  * v_{1} +  a_{22} * v_{2}
\\ a_{31} * v_{1} + a_{32} * v_{2}
\end{bmatrix}
$$

```python
from numpy import array
from numpy import dot
A = array([[1, 2], [3, 4], [5, 6]])
v = array([0.5, 0.5])
C = dot(A, v)
print(C)
```

```text
[1.5 3.5 5.5]
```

## Matrix Multiplication \(Hadamard Product\)

Two matrices with the same dimension can be simply multiplied element-wise. Also known as Hadamard Product, it is represented with a circle as  **`C = A o B`**

**Note**: Implemented using star operator as in Matrix-Scalar Multiplication

$$
A=\begin{bmatrix}
a_{11} \hspace{0.2cm} a_{12}
\\ a_{21} \hspace{0.2cm} a_{22}
\\ a_{31} \hspace{0.2cm} a_{32}
\end{bmatrix},
B=\begin{bmatrix}
b_{11} \hspace{0.2cm} b_{12}
\\ b_{21} \hspace{0.2cm} b_{22}
\\ b_{31} \hspace{0.2cm} b_{32}
\end{bmatrix}
\newline
C=\begin{bmatrix}
a_{11}  * b_{11} , a_{12} * b_{12}
\\ a_{21}  * b_{21} ,  a_{22} * b_{22}
\\ a_{31} * b_{31} , a_{32} * b_{32}
\end{bmatrix}
$$

```python
from numpy import array
A = array([[1, 2, 3], [4, 5, 6]])
B = array([[2, 2, 2], [.5, .5, .5]])
C = A * B
print(C)
```

```text
[[2.  4.  6. ]
 [2.  2.5 3. ]]
```

## Matrix-Matrix Multiplication \(Dot Product\)

Matrix-Matrix, also called the **matrix dot product** is a complicated multiplication which must follow the **rule of matrix multiplication**. 

This is made clear with the following image:

![Depiction of matrix multiplication](../../../.gitbook/assets/depection-of-matrix-multiplication.png)



Link:  
[Introduction to Matrices and Matrix Arithmetic for Machine Learning](https://machinelearningmastery.com/introduction-matrices-machine-learning/)

