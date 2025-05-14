Given a function $f$ on $[a, b]$ and nodes $a = x_0 < x_1 < x_2 < \cdots < x_n = b$, a **cubic [[Spline Interpolant|spline interpolant]]** $S(x)$ satisfies:

1. $S$ is **piecewise cubic**; that is, $S(x)$ is defined piecewise: $S(x) = S_i(x)$ if $x \in [x_i, x_{i+1}]$ (for $i = 0, 1, \dots, n-1$), where $S_i(x)$ is a cubic polynomial.

2. $S$ agrees with the function $f$ at the nodes, and (consequently) is continuous on $[a, b]$:

$$
S_i(x_i) = f(x_i) \quad \text{and} \quad S_i(x_{i+1}) = f(x_{i+1}), \quad i = 0, 1, \dots, n-1,
$$

$$
\implies \ S_i(x_{i+1}) = S_{i+1}(x_{i+1}), \quad i = 0, 1, \dots, n-2.
$$

3. The derivative $S'$ is continuous at the nodes ($\implies S'$ is continuous on $[a, b]$):

$$
S_i'(x_{i+1}) = S_{i+1}'(x_{i+1}), \quad i = 0, 1, \dots, n-2.
$$

4. The second derivative $S''$ is continuous at the nodes ($\implies S''$ is continuous on $[a, b]$):

$$
S_i''(x_{i+1}) = S_{i+1}''(x_{i+1}), \quad i = 0, 1, \dots, n-2.
$$


### Boundary Conditions

Boundary conditions determine how the spline behaves at the endpoints of the interval $[a, b]$. They provide additional constraints needed to make the spline unique. Without these conditions, the system of equations defining the spline would have multiple solutions. Different types of boundary conditions control the smoothness or shape of the spline at the boundaries.

---

1. **Natural (or free) boundary conditions:**

   Require:

   $$
   S''(x_0) = S''(x_n) = 0
   $$

   This gives a **natural (or free) cubic spline**. It assumes that the curvature at the endpoints is zero, making the spline behave like a straight line near the boundaries. This is the simplest choice for boundary conditions.

---

2. **Clamped boundary conditions:**

   Require:

   $$
   S'(x_0) = f'(x_0), \quad S'(x_n) = f'(x_n)
   $$

   This gives a **clamped cubic spline**. It forces the spline's slope at the endpoints to match the slope of the function $f(x)$. This minimizes approximation errors but requires the derivatives $f'(x_0)$ and $f'(x_n)$ to be known.

---

3. **Not-a-knot conditions:**

   Require:

   $$
   S''_0(x_1) = S''_1(x_1), \quad S''_{n-2}(x_{n-1}) = S''_{n-1}(x_{n-1})
   $$

   This gives a **not-a-knot cubic spline**. It enforces continuity of the second derivative at the first interior node $x_1$ and the last interior node $x_{n-1}$. This is equivalent to treating the first two and last two intervals as part of the same cubic polynomial. Nodes $x_1$ and $x_{n-1}$ are treated as "not knots," meaning they don’t impose extra constraints.

#### Example

Construct a natural cubic spline through the data:

| $x_i$    | 0   | 1   | 2   |
| -------- | --- | --- | --- |
| $f(x_i)$ | 1   | 2   | 1   |

The spline consists of two cubic polynomials:

$$
S_0(x) = a_0 + b_0(x - x_0) + c_0(x - x_0)^2 + d_0(x - x_0)^3, \quad x \in [0, 1],
$$

$$
S_1(x) = a_1 + b_1(x - x_1) + c_1(x - x_1)^2 + d_1(x - x_1)^3, \quad x \in [1, 2].
$$

We need to determine the eight unknowns $a_0, b_0, c_0, d_0$ (for $S_0(x)$) and $a_1, b_1, c_1, d_1$ (for $S_1(x)$) by solving the following conditions:

1. **Interpolation conditions:**

   - $S_0(x_0) = f(x_0) \implies a_0 = 1$,
   - $S_0(x_1) = f(x_1) \implies a_0 + b_0(1) + c_0(1)^2 + d_0(1)^3 = 2$,
   - $S_1(x_1) = f(x_1) \implies a_1 = 2$,
   - $S_1(x_2) = f(x_2) \implies a_1 + b_1(2-1) + c_1(1)^2 + d_1(1)^3 = 1$.

2. **Continuity of $S'$:**

   - $S_0'(x_1) = S_1'(x_1) \implies b_0 + 2c_0 + 3d_0 = b_1$.

3. **Continuity of $S''$:**

   - $S_0''(x_1) = S_1''(x_1) \implies 2c_0 + 6d_0 = 2c_1$.

4. **Natural boundary conditions:**

   - $S_0''(x_0) = 0 \implies 2c_0 = 0 \implies c_0 = 0$,
   - $S_1''(x_2) = 0 \implies 2c_1 + 6d_1 = 0 \implies c_1 + 3d_1 = 0$.

---

**Solving the system:**

From the equations above, solving the system of eight equations gives:

$$
a_0 = 1, \quad b_0 = \frac{3}{2}, \quad c_0 = 0, \quad d_0 = -\frac{1}{2},
$$
$$
a_1 = 2, \quad b_1 = 0, \quad c_1 = -\frac{3}{2}, \quad d_1 = \frac{1}{2}.
$$

---

**The cubic spline interpolant is:**
$$ S(x) = \begin{cases} 1 + \frac{3}{2}x - \frac{1}{2}x^{3}, & \quad 0 \leq x \leq 1, \\[8pt] 2 - \frac{3}{2}(x - 1)^2 + \frac{1}{2}(x - 1)^3, & \quad 1 < x \leq 2. \end{cases} $$
