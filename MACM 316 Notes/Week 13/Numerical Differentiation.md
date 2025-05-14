Numerical differentiation involves estimating the [[Derivative|derivative]] of a function, $f(x)$, when the explicit form of the function is unknown or only discrete data points $(x_i, y_i)$ are available.

### [[Limits|Limit]] Definition of a Derivative

The derivative is defined as:

$$
f'(x_0) = \lim_{h \to 0} \frac{f(x_0 + h) - f(x_0)}{h}.
$$

### Forward Difference Approximation

Using the definition above, we can approximate the first derivative using the **forward difference formula**:

$$
f'(x_0) \approx D_+ f(x_0) = \frac{f(x_0 + h) - f(x_0)}{h}, \quad (h > 0),
$$

which represents the slope of the secant line connecting the points $(x_0, f(x_0))$ and $(x_0 + h, f(x_0 + h))$.

> **Note:** This formula is **numerically unstable** and highly sensitive to [[Round-off error|round-off error]] for small $h$.

### Difference Formulas

Using the definition of the derivative (and assuming $h > 0$), we can derive several difference formulas for the first derivative:

- **Forward Difference:**

  $$
  f'(x_0) \approx D_+ f(x_0) = \frac{f(x_0 + h) - f(x_0)}{h},
  $$

- **Backward Difference:**

  $$
  f'(x_0) \approx D_- f(x_0) = \frac{f(x_0) - f(x_0 - h)}{h},
  $$

- **Centered Difference:**

  $$
  f'(x_0) \approx D_0 f(x_0) = \frac{f(x_0 + h) - f(x_0 - h)}{2h}.
  $$
