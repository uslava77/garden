## 0) Motivation: “Change from a base point”
In one variable, the best local description of a curve is a **line**; in several variables, it is a **plane** (or hyperplane).  
The pattern is always:  
> **change in output** ≈ **sum of slopes** × **changes in inputs** (measured **relative to a base point**).

The subtractions like $y-y_0$, $x-x_0$, and $z-z_0$ simply measure **how far we’ve moved from the point of tangency** so that the approximation both (i) passes through the base point and (ii) has the correct slopes.

---

## 1) Single–Variable Recap (tangent line ↔ differentiability)
Let $y=g(x)$ and $y_0=g(x_0)$. Differentiability at $x_0$ means
$$
g'(x_0)=\lim_{x\to x_0}\frac{g(x)-g(x_0)}{x-x_0},
\qquad 
g(x)=g(x_0)+g'(x_0)(x-x_0)+o(|x-x_0|).
$$
The tangent line is
$$
\boxed{\,y-y_0=g'(x_0)(x-x_0)\,}.
$$
- Plugging $x=x_0$ forces $y=y_0$ (the line is **anchored** at the point).
- The coefficient $g'(x_0)$ is the slope (the line has the right **tilt**).

---

## 2) From Curves to Surfaces: Linearization in $\mathbb{R}^2\to\mathbb{R}$
Let $z=f(x,y)$ with $z_0=f(x_0,y_0)$.  
**Differentiability at $(x_0,y_0)$** means there exists a linear map
$$
L(h,k)=f_x(x_0,y_0)\,h+f_y(x_0,y_0)\,k
$$
such that
$$
\lim_{(h,k)\to(0,0)}
\frac{f(x_0+h,y_0+k)-f(x_0,y_0)-L(h,k)}{\sqrt{h^2+k^2}}=0.
$$
Equivalently, the **first-order (linear) approximation** is
$$
\boxed{\,f(x,y)\approx f(x_0,y_0)+f_x(x_0,y_0)(x-x_0)+f_y(x_0,y_0)(y-y_0)\,}.
$$

### Tangent plane to the graph $z=f(x,y)$
Rewriting the approximation as an equation for $z$ gives the tangent plane:
$$
\boxed{\,z-z_0=f_x(x_0,y_0)(x-x_0)+f_y(x_0,y_0)(y-y_0)\,}.
$$
- $z-z_0$ is the **change in height** from the base point; setting $(x,y)=(x_0,y_0)$ yields $z=z_0$, so the plane is positioned correctly.
- $f_x$ and $f_y$ are the slopes of the surface along the $x$- and $y$-directions, so the plane has the correct **tilt**.

---

## 3) The Gradient and Its Geometry
The **gradient**
$$
\nabla f(x,y)=\langle f_x(x,y),\,f_y(x,y)\rangle
$$
packages the local slopes.

- **Directional derivative** in a unit direction $\mathbf u$:
  $$
  D_{\mathbf u}f(x_0,y_0)=\nabla f(x_0,y_0)\cdot \mathbf u.
  $$
  Hence $\nabla f$ points in **steepest ascent**, and $\|\nabla f\|$ is the maximal directional slope.

- **Orthogonality to level sets**: $\nabla f$ is perpendicular to level curves $f(x,y)=c$.

### Gradient as a normal to the graph
Consider the level-set formulation $F(x,y,z)=f(x,y)-z$. Then
$$
\nabla F(x_0,y_0,z_0)=\big\langle f_x(x_0,y_0),\,f_y(x_0,y_0),\, -1\big\rangle
$$
is **normal to the surface** $z=f(x,y)$ at $(x_0,y_0,z_0)$.  
Thus the tangent plane can be written compactly as
$$
\boxed{\,\nabla F(x_0,y_0,z_0)\cdot\langle x-x_0,\,y-y_0,\,z-z_0\rangle=0\,},
$$
which expands to the plane equation above.

---

## 4) Implicit Surfaces (general viewpoint)
For an implicit surface $G(x,y,z)=0$ with $\nabla G\neq 0$ at a point $\mathbf p$,
- **Normal vector at $\mathbf p$**: $\nabla G(\mathbf p)$.
- **Tangent plane at $\mathbf p$**:
  $$
  \boxed{\,\nabla G(\mathbf p)\cdot(\mathbf x-\mathbf p)=0\,}.
  $$

---

## 5) Practical “recipe” at a point $(x_0,y_0)$
1. Compute partial derivatives $f_x(x_0,y_0)$, $f_y(x_0,y_0)$.
2. **Linearization**: 
   $$
   f(x,y)\approx f(x_0,y_0)+\nabla f(x_0,y_0)\cdot\langle x-x_0,\,y-y_0\rangle.
   $$
3. **Tangent plane to the graph**:
   $$
   z-z_0=f_x(x_0,y_0)(x-x_0)+f_y(x_0,y_0)(y-y_0).
   $$
4. **Normal to the graph**:
   $$
   \mathbf n=\langle f_x(x_0,y_0),\,f_y(x_0,y_0),\,-1\rangle.
   $$

---

## 6) Higher–Dimensional Snapshot
For $f:\mathbb{R}^n\to\mathbb{R}$ at $\mathbf x_0$,
$$
f(\mathbf x)=f(\mathbf x_0)+\nabla f(\mathbf x_0)\cdot(\mathbf x-\mathbf x_0)+o(\|\mathbf x-\mathbf x_0\|).
$$
The tangent **hyperplane** to the graph $x_{n+1}=f(\mathbf x)$ is
$$
\boxed{\,x_{n+1}-f(\mathbf x_0)=\nabla f(\mathbf x_0)\cdot(\mathbf x-\mathbf x_0)\,},
$$
with normal $\big(\nabla f(\mathbf x_0),-1\big)$.

---

## 7) Key Takeaways
- “Subtract the base point” ($y-y_0$, $z-z_0$, etc.) to **anchor** the approximation and express **changes**.
- Linearization = **best first-order model**: output change $\approx$ gradient $\cdot$ input change.
- Gradient encodes local slopes, gives **steepest ascent**, and is **orthogonal to level sets**.
- For graphs $z=f(x,y)$, the normal is $\langle f_x,f_y,-1\rangle$ and the tangent plane is $z-z_0=f_x(x_0,y_0)(x-x_0)+f_y(x_0,y_0)(y-y_0)$.