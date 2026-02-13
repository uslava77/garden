### Transformation Theorem
If $X$ is a continuous random variable with pdf $f_X(x)$, and $Y = g(X)$ is a transformation of $X$, then:

- If $g$ is **strictly monotone** (one-to-one, either increasing or decreasing), the pdf of $Y$ is:

$$

f_Y(y) = f_X(g^{-1}(y)) \cdot \left| \frac{d}{dy} g^{-1}(y) \right|,

\quad y \in g(\text{support of }X).

$$
*(The **support** of $X$ is the set of all values $x$ where $f_X(x) > 0$.)*
#### Proof Sketch
Start from the **definition of the CDF**:
$$

F_Y(y) = P(Y \leq y) = P(g(X) \leq y).

$$
If $g$ is strictly increasing:
$$

F_Y(y) = P(X \leq g^{-1}(y))

= \int_{-\infty}^{g^{-1}(y)} f_X(x), dx.

$$
Differentiate with respect to $y$:
$$

f_Y(y) = \frac{d}{dy}F_Y(y)

= f_X(g^{-1}(y)) \cdot \frac{d}{dy}g^{-1}(y).

$$
Since densities must be nonnegative, we take absolute value:
$$

f_Y(y) = f_X(g^{-1}(y)) \cdot \left| \frac{d}{dy} g^{-1}(y) \right|.

$$

If $g$ is **strictly decreasing**, then $g^{-1}(y)$ is also strictly decreasing, so its derivative is **negative**.

  

In the proof step:

  

$$

f_Y(y) = f_X(g^{-1}(y)) \cdot \frac{d}{dy} g^{-1}(y),

$$

  

the derivative $\tfrac{d}{dy}g^{-1}(y) < 0$, which would make the density negative — not allowed.

  

That’s why the formula always uses:

  

$$

f_Y(y) = f_X(g^{-1}(y)) \cdot \left| \frac{d}{dy} g^{-1}(y) \right|.

$$

  

So the **same rule works** whether $g$ is increasing or decreasing: the absolute value fixes the sign.
### Lazy Statistician

The rule of the lazy statistician states that if $Y = r(X)$, then

$$
\mathbb{E}[Y] = \sum_{x \in S_X} r(x) f_X(x).
$$
Continuous case:

$$

\mathbb{E}[Y] = \mathbb{E}[r(X)] = \int_{-\infty}^{\infty} r(x) f(x) \,dx.

$$


Note the following points:
- The reason for the name *"the rule of the lazy statistician"* is that the rule is sometimes mistaken as a definition when, in fact, it is a statement that requires rigorous proof (we won't do that here).
- The rule is sometimes called the **law of the unconscious statistician** (or **LOTUS**).
- **In general**, $\mathbb{E}[r(X)] \neq r(\mathbb{E}[X])$.


#### Variance of a Linear Combination of Random Variables
$$

\mathrm{Var}!\left(\sum_{i=1}^n a_i X_i\right)

= \sum_{i=1}^n a_i^2 ,\mathrm{Var}[X_i]

- 2 \sum_{i<j} a_i a_j ,\mathrm{Cov}[X_i, X_j].
$$
##### **Proof (sketch)**
$$

\mathrm{Var}!\left(\sum_{i=1}^n a_i X_i\right)

= \mathbb{E}!\left[\Big(\sum_{i=1}^n a_i X_i - \mathbb{E}!\left[\sum_{i=1}^n a_i X_i\right]\Big)^2\right].

$$

Since expectation is linear:
$$

\mathbb{E}!\left[\sum_{i=1}^n a_i X_i\right] = \sum_{i=1}^n a_i \mathbb{E}[X_i].

$$

Expanding the square:
$$

\Big(\sum_{i=1}^n a_i (X_i - \mathbb{E}[X_i])\Big)^2

= \sum_{i=1}^n a_i^2 (X_i - \mathbb{E}[X_i])^2

- 2 \sum_{i<j} a_i a_j (X_i - \mathbb{E}[X_i])(X_j - \mathbb{E}[X_j]).
$$
Taking expectation:
- The first sum gives $a_i^2 \mathrm{Var}[X_i]$.
- The cross terms give $2a_i a_j \mathrm{Cov}[X_i, X_j]$.
Thus:
$$
\mathrm{Var}!\left(\sum_{i=1}^n a_i X_i\right)

= \sum_{i=1}^n a_i^2 ,\mathrm{Var}[X_i]

- 2 \sum_{i<j} a_i a_j ,\mathrm{Cov}[X_i, X_j].
$$
