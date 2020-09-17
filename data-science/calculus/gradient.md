# Gradient

A **gradient** is a vector that stores the partial derivatives of multi variable functions, often denoted by $$\nabla$$. It helps us calculate the **slope** at a specific point on a curve for functions with multiple independent variables.

### **Find a Gradient**

Consider a function with two variables \(x and y\): $$f(x,y) = x^2 + y^3$$ 

  
****1\) Find **partial derivative** with respect to **x** \(Treat y as a constant like a random number 12\)

$$
f'_x = \frac{\partial f}{\partial x} =  2x+0=2x
$$

2\) ****Find **partial derivative** with respect to **y** \(Treat x as a constant\)

$$
f'_y =\frac{\partial f}{\partial y}= 0+3y^2=3y^2
$$

3\) Store partial derivatives in a **gradient**

$$
\nabla f(x,y) = \begin{bmatrix}\frac{\partial f}{\partial x}  \\ \frac{\partial f}{\partial y}\end{bmatrix} = \begin{bmatrix}2x \\ 3y^2\end{bmatrix}
$$



### Properties of Gradients

There are two additional properties of gradients that are especially useful in deep learning. A gradient:

1. Always points in the direction of greatest increase of a function \([explained here](https://betterexplained.com/articles/understanding-pythagorean-distance-and-the-gradient)\)
2. Is zero at a local maximum or local minimum

## Directional Derivative

The **directional derivative** $$\nabla_{\vec v} f$$ is the rate at which the function $$f(x,y)$$ changes at a point $$(x_1,y_1)$$ in the direction $${\vec v}$$.

**Directional derivative** is computed by taking the **dot product** of the gradient of $$f$$ and a unit vector $${\vec v}$$

Note: Directional derivative of a function is a **scalar** while gradient is a **vector**.

### Find Directional Derivative

Consider a function with two variables \(x and y\): $$f(x,y) = x^2 + y^3$$

$$
{\vec v} = \begin{bmatrix}2 \\ 3\end{bmatrix}
$$

As described above, we take the **dot product** of the gradient and the directional vector:

$$
\begin{bmatrix}\frac{\partial f}{\partial x}  \\ \frac{\partial f}{\partial y}\end{bmatrix} . \begin{bmatrix}2 \\ 3\end{bmatrix}
\newline
\newline

\newline
$$

We can rewrite the dot product as:

$$
\nabla_{\vec v} f = 2\frac{\partial f}{\partial x} +3 \frac{\partial f}{\partial y} = 2(2x) + 3(3y^2)=4x+9y^2
$$

Hence, the directional derivative $$\nabla_{\vec v} f$$at co-ordinates $$(5, 4) $$ is:  
$$\nabla_{\vec v} f = 4x+9y^2 = 4(5)+9(4)^2 = 164$$ 



Link:  
- [http://wiki.fast.ai/index.php/Calculus\_for\_Deep\_Learning](http://wiki.fast.ai/index.php/Calculus_for_Deep_Learning)

