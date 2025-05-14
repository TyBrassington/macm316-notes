Given a set of nodes $a = x_0 < x_1 < x_2 < \cdots < x_n = b$: 
A **spline of degree $m$** is a piecewise polynomial function $S(x) \in C^{m-1}[a, b]$ such that:

- On each interval $[x_i, x_{i+1}]$ $(i = 0, 1, \dots, n-1)$, the [[The Interpolating Polynomial|interpolant]] $S(x)$ is a polynomial $S_i(x)$ of degree $\leq m$. 
- $S$ and its first $m-1$ derivatives are continuous at the interior nodes. $$ \lim_{x \to x_i^-} S_{i-1}^{(k)}(x) = \lim_{x \to x_i^+} S_i^{(k)}(x), \quad 0 \leq k \leq m-1, \quad i = 1, 2, \dots, n-1. $$
