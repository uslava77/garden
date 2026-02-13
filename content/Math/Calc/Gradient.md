The **gradient** of a function $f(x, y)$ is a vector that points in the direction of the greatest rate of increase of the function. It combines all the first-order [partial derivatives](Partial%20Derivative.md) of the function.
$$
\nabla f(x, y) = \left[ \frac{\partial f}{\partial x}, \frac{\partial f}{\partial y} \right]
= [f_x, f_y]
$$
More generally, for a function $f(x_1, x_2, \dots, x_n)$ of $n$ variables, the gradient is:

$$
\nabla f = \left[ \frac{\partial f}{\partial x_1}, \frac{\partial f}{\partial x_2}, \dots, \frac{\partial f}{\partial x_n} \right]
$$
### Interpretation
- The gradient vector points in the direction of [Steepest Ascent](#Steepest%20Ascent%20Intuition).
- Its [magnitude](Vectors,%20Lines,%20Planes!.md#Vector%20Length%20and%20Product) represents the rate of increase in that direction.
- At a given point, moving in the direction of the gradient increases the value of $f$ most rapidly.
- "A vector that loves to be dotted with other things"

### Steepest Ascent Intuition
The level curves of f(x,y) will be almost parallel when close together (small changes of the function). The vector that gets there in the shortest path will be perpendicular to the initial point on the curve.
# Directional Derivative
This is a small change from the [definition of the partial](Partial%20Derivative.md#Vector%20Definition); instead of $\hat{x_i}$ we use a $\vec v$.
The change in $f$ at some point $\vec x$, given a small nudge in the direction $\vec v$ ($\lVert \vec{v} \rVert=1$):
$$
\frac{\partial f}{\partial {\vec v}} = \lim_{h \to 0} \frac{f(\vec{x}+h \vec v) - f(\vec{x})}{h}
$$
It is also written as $\nabla_{\vec v} f(\vec x)$ because it turns out that:
$$
\lim_{h \to 0} \frac{f(\vec{x}+h \vec v) - f(\vec{x})}{h} = \nabla f (\vec x) \cdot \vec v
$$
## Proof
Define 
$$
\gamma(h) = \vec x + h \vec v
$$
and
$$
g(h) = f(\gamma (h) ) = f(\vec x + h \vec v)
$$
Using the [Multivariable Chain Rule](Multivariable%20Chain%20Rule.md) we get
$$
g'(h)=\nabla f(\gamma(h)) \cdot \gamma '(h)  = \nabla f(\vec x + h \vec v) \cdot \vec v
$$
Evaluate at zero:
$$
g'(0)=\nabla f(\vec x) \cdot \vec v
$$

Now we show how $g'(0)$ is the limit definition of the directional derivative.
From the definition of $g$:
$$
\lim_{h \to 0} \frac{f(\vec{x}+h \vec v) - f(\vec{x})}{h} =\lim_{h \to 0} \frac {g(h)-g(0)}{h} = g'(0)
$$

## Steepest Ascent Intuition 2
If you take some point $(x_0,y_0)$ and you want to know in which direction $f$ has the steepest ascent, then you would basically want to find $v$ s.t.
$$ 
\max_{\lVert\vec v\rVert = 1} \nabla f(x_0,y_0) \cdot \vec v
$$
We trace a circle around the fixed point, and [dot product](Vectors,%20Lines,%20Planes!.md#Vector%20Length%20and%20Product) the rate of change of $f$ at that point, with a vector of a consistent length.  
This way we check in which direction around that point will $f$ change the most.  
**Equivalently, we maximize the [Directional Derivative](#Directional%20Derivative)!** 

Since dot product is maximized when the vectors point in the same direction, the gradient must point in the direction of steepest ascent.
$$ 
\max_{\lVert\vec v\rVert = 1} \nabla f(x_0,y_0) \cdot \vec v = \frac{\nabla f(x_0,y_0)}{\lVert \nabla f(x_0,y_0) \rVert}
$$
Call the above $\vec w$, we get:
$$
\nabla f(x_0,y_0)\cdot \vec w = \frac{\nabla f(x_0,y_0) \cdot \nabla f(x_0,y_0)}{\lVert \nabla f(x_0,y_0) \rVert} = \lVert \nabla f(x_0,y_0) \rVert
$$
Interpretation: if we compute the directional derivative with a unit vector that points in the steepest ascent of $f$, then we get the magnitude of the gradient at that point (thereby confirming that the gradient points in the same direction).