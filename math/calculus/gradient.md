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

Link:  
- [http://wiki.fast.ai/index.php/Calculus\_for\_Deep\_Learning](http://wiki.fast.ai/index.php/Calculus_for_Deep_Learning)

