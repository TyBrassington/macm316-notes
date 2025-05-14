The stopping criterion is a condition used to terminate an iterative process once a solution has reached desired levels of accuracy or when further iterations are no longer necessary. This condition ensures the method/algorithm terminates and doesn't run indefinitely.

### Possible stopping criteria (for a given tolerance, TOL > 0)

##### Tolerance-Based on Function Value
$$
|f(x)| < TOL
$$
Ensures f(x) may be small, but still could be far from exact root. If there is a steep slope near the root, than a small change in $x$ may lead to a large change in $f(x)$

##### Tolerance-Based on Error Change

- **Absolute Error Criterion**
$$
|x_{new}\:-\:x_{old}| < TOL
$$
	Used when the scale of the problem is known or constant, and the error should be measured directly in terms of the changes in the variable.

- **Relative Error Criterion**
$$
\frac{|x_{new}\:-\:x_{old}|}{|x_{new}|} < TOL
$$
	Used when the values are large or span several orders of magnitude, and the change should be proportional to the size of the estimate itself.

##### Maximum Number of Iterations

Stop after a predefined number $N_{0}$ of iterations. This is used as a safeguard to prevent the method from running indefinitely, especially when the method may not converge.