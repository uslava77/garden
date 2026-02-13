$$
\lim_{x\to c}f(x)=L
$$

$$
(\forall \epsilon > 0) (\exists \delta > 0) (\forall x \in \Re) (0 < |x-c| < \delta \implies |f(x)-L|<\epsilon)
$$
$f(x)$ is near $L$ , when $x$ is _suitably near c_.


**Understand the definition, and move on.**
**[LIMIT THEOREMS](https://math.libretexts.org/Bookshelves/Analysis/Introduction_to_Mathematical_Analysis_I_(Lafferriere_Lafferriere_and_Nguyen)/03%3A_Limits_and_Continuity/3.02%3A_Limit_Theorems)** 

https://personal.math.ubc.ca/~marcus/Math120/Math120_Lectures7-10.pdf
**Proofs seem to be mostly algebra tricks :(**

Proofs
1. Goal is to pick a $\delta$ in terms of $\epsilon$ , and write $f(x)-L$ in terms of $x-c$ 
2. Then you can do algebra to show $f(x)-L$ is less than some modification of $\delta$ 
3. Then substitute $\epsilon$ for $\delta$ 
4. To show the function error from limit is less than $\epsilon$



WORST EXAMPLES:


![[Pasted image 20240709111921.png]]


Cheatsheet
# **1) Algebra of limits (finite values)**

  

Let $\lim_{x\to a}f(x)=L$ and $\lim_{x\to a}g(x)=M$ exist and be finite.

- **Linearity**
    
    $\lim(\alpha f+\beta g)=\alpha L+\beta M$ (constants pull in/out).
    
- **Product**
    
    $\lim(fg)=LM$.
    
- **Quotient**
    
    $\lim!\left(\frac{f}{g}\right)=\frac{L}{M}$ provided $M\neq 0$.
    
- **Powers / Roots (continuity rules)**
    
    If $h$ is continuous at $L$, then $\lim h(f(x))=h(L)$.
    
    Special cases: $\lim f^k=L^k$ for fixed integer $k$; if $L>0$ then $\lim \sqrt[k]{f}= \sqrt[k]{L}$.
    
- **Composition**
    
    If $g$ is continuous at $L$ and $\lim f=L$, then $\lim g!\circ f=g(L)$.
    
- **Absolute value / max / min**
    
    Continuous ⇒ you can pass the limit inside: $\lim|f|=|L|$, $\lim\max(f,g)=\max(L,M)$, etc.
    

  

> ⚠️ If any limit is $\pm\infty$, re-check conditions (some algebra may fail or change meaning).

  

# **2) Inequalities & squeeze tools**

- **Order preservation**
    
    If $f(x)\le g(x)$ near $a$ and limits are finite, then $L\le M$.
    
- **Squeeze (Sandwich) Theorem**
    
    If $h\le f\le k$ near $a$ and $\lim h=\lim k = L$, then $\lim f=L$.
    
    Classics: $\displaystyle \lim_{x\to 0}\frac{\sin x}{x}=1$, $\ \lim_{x\to 0}\frac{1-\cos x}{x^2}=\tfrac12$.
    

  

# **3) Limits at $\infty$ and dominance**

- **Dominant term rule (polynomials/rationals)**
    
    As $x\to\infty$, highest-degree term dominates.
    
    For $\frac{a_n x^n+\dots}{b_m x^m+\dots}$: divide numerator/denominator by $x^{\max(n,m)}$ to read the limit (0 if $n<m$, $\infty$ if $n>m$, ratio of leading coefficients if $n=m$).
    
- **Growth rates (very handy heuristics)**
    
    $\log x \ll x^{\alpha} \ll a^x \ll x! \ll x^x$ for $x\to\infty$ ($\alpha>0$, $a>1$).
    
- **Asymptotic equivalence**
    
    If $\frac{f}{g}\to 1$ and $\lim g=L$ (finite, $L\neq 0$), then $\lim f=L$.
    
    Useful with series/Taylor: $\sin x \sim x$, $e^x-1\sim x$, $\ln(1+x)\sim x$ as $x\to 0$.
    

  

# **4) Indeterminate forms & how to tame them**

  

Common forms: $0/0$, $\infty/\infty$, $0\cdot\infty$, $\infty-\infty$, $1^\infty$, $0^0$, $\infty^0$.

- **Algebraic fixes**
    
    - Factor & cancel (turn $0/0$ into regular form).
        
    - Rationalize with a conjugate for roots.
        
    - Common denominator to handle $\infty-\infty$.
        
    - For exponentials/powers, rewrite $a(x)^{b(x)}=\exp!\big(b(x)\ln a(x)\big)$.
        
    
- **Divide by the “largest thing”**
    
    Especially for rational functions or mixed polynomial–root expressions.
    
- **l’Hôpital’s Rule (when applicable)**
    
    If $f,g$ are differentiable near $a$ and give $0/0$ or $\infty/\infty$, then
    
    $\displaystyle \lim_{x\to a}\frac{f(x)}{g(x)}=\lim_{x\to a}\frac{f’(x)}{g’(x)}$ (if the RHS limit exists/finite or $\pm\infty$).
    
    Repeat if needed; don’t use it when a simpler algebraic/trig identity works.
    

  

# **5) Standard “must-know” limits (local linear/quadratic behavior)**

  

As $x\to 0$:

- $\displaystyle \frac{\sin x}{x}\to 1,\quad 1-\cos x \sim \frac{x^2}{2},\quad \tan x \sim x$.
    
- $e^x-1 \sim x,\quad \ln(1+x)\sim x,\quad (1+x)^\alpha \sim 1+\alpha x$ (fixed $\alpha$).
    
- $\displaystyle \left(1+\frac{x}{n}\right)^{n}\to e^{x}$ (as $n\to\infty$ for fixed $x$); special case $(1+\frac1n)^n\to e$.
    
- $\displaystyle (1+ax)^{1/x}\to e^{a}$ as $x\to 0$.
    

  

# **6) Handy transformations/operations**

- **Change of variable**: If $t=\phi(x)$ with $\phi(x)\to b$ as $x\to a$, then $\lim_{x\to a}f(\phi(x))=\lim_{t\to b} f(t)$.
    
- **Log-exp trick (for powers)**:
    
    To compute $\lim a(x)^{b(x)}$, set $y=\ln(\cdot)=b(x)\ln a(x)$, find $\lim y$, then exponentiate.
    
- **Piecewise/absolute values**: Split into one-sided limits if definition changes sign/branch.
    
- **Series/Taylor** (fast local approximations):
    
    $f(x)=f(a)+f’(a)(x-a)+\tfrac12 f’’(a)(x-a)^2+\cdots$; keep the first nonzero term to read the leading behavior.
    

  

# **7) Sequences (quick rules)**

  

For sequences $(a_n)$:

- **Same algebra as functions** (sum/product/quotient) with the same caveats.
    
- **Monotone + bounded ⇒ convergent**.
    
- **Subsequence test**: if two subsequences have different limits, the sequence doesn’t converge.
    
- **Squeeze** works verbatim.
    

---

## **Mini examples (one per theme)**

- **Product/Quotient**: $\displaystyle \lim_{x\to 2}\frac{3x^2\cdot (x-1)}{x+1}=\frac{3\cdot 4\cdot 1}{3}=4$.
    
- **Dominant term**: $\displaystyle \lim_{x\to\infty}\frac{5x^3-2x}{-x^3+7}=\frac{5}{-1}=-5$.
    
- **Indeterminate fix** ($0/0$):
    
    $\displaystyle \lim_{x\to 1}\frac{x^2-1}{x-1}=\lim_{x\to 1}\frac{(x-1)(x+1)}{x-1}=2$.
    
- **Conjugate**: $\displaystyle \lim_{x\to 0}\frac{\sqrt{1+x}-1}{x}=\lim \frac{x}{x(\sqrt{1+x}+1)}=\frac{1}{2}$.
    
- **Log-exp**: $\displaystyle \lim_{x\to 0^+} x^{,x}=\exp!\big(\lim x\ln x\big)=\exp(0)=1$.
    

  

If you want, I can turn this into an Obsidian-ready note with your preferred formatting and a few extra worked examples.