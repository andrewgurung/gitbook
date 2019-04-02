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

## Matrix-Scalar Multiplication

## Matrix-Vector Multiplication

## Matrix Multiplication \(Hadamard Product\)

## Matrix-Matrix Multiplication \(Dot Product\)



Link:  
[Introduction to Matrices and Matrix Arithmetic for Machine Learning](https://machinelearningmastery.com/introduction-matrices-machine-learning/)

