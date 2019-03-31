# Vector Norms and Orthogonality

## Vector Spaces

 A _vector space_ is a set V of vectors on which two operations + and **·** are defined, called _vector addition_ and _scalar multiplication._

The operation + \(**vector addition**\) must satisfy the following conditions, where u, v, w are vectors and c,d are scalars:

1. Commutative law: **u** + **v** = **v** + **u**
2. Associative law:  **u** + \(**v** + **w**\) = \(**u** + **v**\) + **w**
3. Additive identity:  **0** + **v** = **v**   and   **v** + **0** = **v**
4. Additive inverses: **u** + **\(-u\)** = **0**

The operation **·** \(**scalar multiplication**\) must satisfy the following conditions:

1. _Distributive law over vector sum:_ c **·** \(**u** + **v**\) = c **·** **u** + c **·** **v**
2. _Distributive law over scalar sum_: \(c+d\) **·** **v** = c **·** **v** + d **·** **v**
3. _Associative law of scalar product_: c **·** \(d **·** **v**\) = \(cd\) **·** **v**
4. _Unitary law_: 1 **·** **v** = **v**

## Vector Norm

Vector norm is a non**-**negative number which describes the length or extent of the vector in space. Also known as vector length or magnitude. There are different ways to calculate vector norms.

$$
X =\begin{bmatrix}x_1 \\ x_2 \\ x_3 \end{bmatrix}
$$

### L1 Norm

L1 Norm is calculated as the sum of absolute values of the vector.

* Calculates the Manhattan distance from the origin of vector space

$$
L^1 = |x_1| + |x_2|+|x_3|
$$

### L2 Norm

L2 Norm is calculated as the square root of the sum of the squared vector values.

* Calculates the Euclidean distance from the origin of vector space
* More commonly used in ML

$$
L^2 = \sqrt{ x_1^2 + x_2^2+x_3^2}
$$

### Max Norm

Max Norm is calculated as the maximum vector values.

$$
L^\infty = max(|x_1| , |x_2|,|x_3|)
$$

### Calculating Norm using NumPy

```python
from numpy import array
from numpy.linalg import norm
from numpy import inf

x = array([1, 2, -3])
l1 = norm(x, 1)
l2 = norm(x, 2)
lmax = norm(x, inf)

print('L1 norm: ', l1)
print('L2 norm: ', l2)
print('LMax norm: ', lmax)
```

```text
L1 norm:  6.0
L2 norm:  3.7416573867739413
LMax norm:  3.0
```

## Orthogonality

Links:

[What is a Vector Space? \(Abstract Algebra\)  
](https://www.youtube.com/watch?v=ozwodzD5bJM)[Gentle Introduction to Vector Norms in Machine Learning  
](https://machinelearningmastery.com/vector-norms-machine-learning/)[From Norm to Orthogonality](https://towardsdatascience.com/from-norm-to-orthogonality-fundamental-mathematics-for-machine-learning-with-intuitive-examples-57bb898e69f2)

$$
X =\begin{bmatrix}x_1 \\ x_2 \\ x_3 \end{bmatrix}
$$

