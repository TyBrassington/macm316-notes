An **interpolating polynomial** is a polynomial that passes exactly through a given set of points in the plane. More formally, given a set of $n+1$ data points $(x_0, y_0), (x_1, y_1), \ldots, (x_n, y_n)$ where all $x_i$ are distinct, the interpolating polynomial is a polynomial $P(x)$ of degree at most $n$ such that: $$ P(x_i) = y_i \quad \text{for each } i = 0, 1, \ldots, n $$
One of the most common ways to perform polynomial interpolation is  [[Legrange Interpolation]]
### Properties

1. **Uniqueness**: For any set of $n+1$ distinct points, there exists exactly one polynomial of degree at most $n$ that interpolates the points. 
2. **Degree**: The minimal degree of the interpolating polynomial for $n+1$ points is $n$, assuming no lower-degree polynomial passes through all the points.

### Error in polynomial interpolation

Let $f \in C^{n+1}[a, b]$, and let $x_0, x_1, \dots, x_n$ be $n + 1$ distinct points in $[a, b]$. Let $P_n$ be the (unique) polynomial of degree $\leq n$ which interpolates $f$ at the nodes $x_i$, i.e. $P_n(x_i) = f(x_i)$, for $i = 0, 1, \dots, n$.

Then for each $x \in [a, b]$, there exists $\xi = \xi(x) \in (a, b)$ such that

$$
f(x) = P_n(x) + \frac{f^{(n+1)}(\xi)}{(n+1)!} (x - x_0)(x - x_1) \cdots (x - x_n).
$$

