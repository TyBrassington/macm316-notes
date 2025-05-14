A [[Splines|spline]] interpolant to a function $f$ is a piecewise polynomial of degree $m$ that matches $f$ at specific points (nodes). This means:
$$
S(x_i) = f(x_i), \quad i = 0, 1, \dots, n,
$$
and the first $m-1$ derivatives of $S(x)$ are smooth (continuous) at the interior nodes, often called "knots."

**Example:** A piecewise linear interpolant (a line between each pair of nodes) is a spline interpolant of degree 1.

![[Spline Interpolant.png]]