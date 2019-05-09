# Matrix Calculus

## Vector Calculus

\*\*\*\*[**Gradients** ](gradient.md)are part of the **vector calculus** world. Instead of having partial derivatives just floating around and not organized in any way, we organize them into a horizontal **vector** also known as gradient.

The gradient of $$f(x,y) = x^2 + y^3$$ is:

$$
\nabla f(x,y) = \begin{bmatrix}\frac{\partial f}{\partial x}  \\ \frac{\partial f}{\partial y}\end{bmatrix} = \begin{bmatrix}2x \\ 3y^2\end{bmatrix}
$$

## Matrix Calculus

When we add derivatives of another function $$g(x,y)$$ to the above function $$f(x,y)$$, we move from the world of **vector** calculus to **matrix** calculus.

The gradient of $$g(x,y) = 2x+y^8$$ is:

$$
\nabla g(x,y) = \begin{bmatrix}\frac{\partial g}{\partial x}  \\ \frac{\partial g}{\partial y}\end{bmatrix} = \begin{bmatrix}2 \\ 8y^7\end{bmatrix}
$$

If we have **two or more** functions, we can also organize their gradients into a matrix by stacking the gradients. When we do so, we get the **Jacobian matrix** _****_\(or just the **Jacobian**\) where the each gradient is represented as a row:

$$
J =
\begin{bmatrix}\nabla f(x,y) \\ \nabla g(x,y)
\end{bmatrix} 
= 
\begin{bmatrix}\frac{\partial f}{\partial x}\frac{\partial f}{\partial y}  
\\ \frac{\partial g}{\partial x}\frac{\partial g}{\partial y}
\end{bmatrix} 
= 
\begin{bmatrix}2x \hspace{0.2cm}3y^2 
\\ 
2 \hspace{0.2cm}8y^7
\end{bmatrix}
$$

Links:

* [The Matrix Calculus You Need For Deep Learning](https://explained.ai/matrix-calculus/index.html)

