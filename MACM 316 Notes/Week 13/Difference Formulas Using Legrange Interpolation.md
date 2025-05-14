Given a set of points $x_0 < x_1 < x_2 < \cdots < x_n$, we approximate a function $f(x)$ using the [[Legrange Interpolation|Lagrange]] interpolating polynomial of degree $n$:

$$
P_n(x) = \sum_{k=0}^n L_k(x) f(x_k),
$$

where the Lagrange basis polynomials are defined as:

$$
L_k(x) = \prod_{\substack{i=0 \\ i \neq k}}^n \frac{x - x_i}{x_k - x_i}.
$$

### Error in Polynomial Interpolation

Using a theorem for polynomial interpolation, we express $f(x)$ as:

$$
f(x) = P_n(x) + \frac{f^{(n+1)}(\xi)}{(n+1)!} \underbrace{ (x - x_0)(x - x_1)\cdots(x - x_n) }_{ \ell(x) },
$$

where:
- $\xi$ is some point in the interval $[x_0, x_n]$,
- $\ell(x) = \prod_{i=0}^n (x - x_i)$.

---

### Derivation of the Derivative Formula

Since $P_n(x)$ is known explicitly, we can differentiate it to approximate $f'(x)$:

$$
f'(x) = \frac{d}{dx} P_n(x) + \frac{d}{dx} \left[ \frac{f^{(n+1)}(\xi)}{(n+1)!} \ell(x) \right].
$$

Expanding this, we have:

$$
f'(x) = \underbrace{ \sum_{k=0}^n L_k'(x) f(x_k) }_{\text{approx to } f'(x_j)} + \frac{f^{(n+1)}(\xi)}{(n+1)!} \frac{d}{dx} \ell(x) + \ell(x) \frac{d}{dx} f^{(n+1)}(\xi).
$$

### Simplification at Node $x_j$

At $x = x_j$, $\ell(x_j)$ vanishes, simplifying the expression for $f'(x_j)$:

$$
f'(x_j) = \sum_{k=0}^n L_k'(x_j) f(x_k).
$$

The error term at $x_j$ becomes:

$$
\text{Error} = \frac{f^{(n+1)}(\xi)}{(n+1)!} \prod_{\substack{i=0 \\ i \neq j}}^n (x_j - x_i).
$$

---

### Properties of the Formula

1. **Values of $L_k'(x_j)$ and $\ell'(x_j)$**:
   - These can be computed exactly, independent of the function $f(x)$.
   - $\ell'(x_j) = \prod_{\substack{i=0 \\ i \neq j}}^n (x_j - x_i) = \frac{1}{w_j},$ where $w_j$ is a weight.

2. **Final Derivative Formula**:
   For $n+1$ points, the derivative at $x_j$ is approximated as:

   $$
   f'(x_j) \approx \sum_{k=0}^n L_k'(x_j) f(x_k).
   $$

---

### Special Case: Equally Spaced Nodes

If the nodes are equally spaced with step size $h$, such that:

$$
x_1 = x_0 + h, \quad x_2 = x_0 + 2h, \quad \dots, \quad x_j = x_0 + jh,
$$

then:

- $L_k'(x_j)$ becomes a pure number, depending only on $j$, $k$, and $n$.
- $\ell'(x_j)$ simplifies, leading to coefficients that depend linearly on $h$.

This produces an $n^{th}$-order accurate formula for $f'(x_j)$.
