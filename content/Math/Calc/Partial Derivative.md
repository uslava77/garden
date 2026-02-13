Let $f(x, y)$ be a function of two variables.  
The **partial derivative** of $f$ with respect to $x$ is computed by taking the derivative of $f$ with respect to $x$ using the usual rules **while treating $y$ as a constant**.
### Notation  
The partial derivative of $f$ with respect to $x$ is written $\frac{\partial f}{\partial x}$
### Definition  
$$
\frac{\partial f}{\partial x} = \lim_{h \to 0} \frac{f(x+h,\,y) - f(x,\,y)}{h}
$$
### Vector Definition
For $\vec{x} \in \mathbb{R}^n$ the $i$-th partial is:
$$
\frac{\partial f}{\partial x_i} = \lim_{h \to 0} \frac{f(\vec{x}+h \hat{x_i}) - f(\vec{x})}{h}
$$
where $\hat {x_i}$ is the basis/unit vector in the $i$-th direction.
### Shorthand notation  
$$
f_x = \frac{\partial f}{\partial x}, \qquad
f_y = \frac{\partial f}{\partial y}
$$
