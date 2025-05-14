 **Divided difference** interpolation constructs an interpolating polynomial by recursive division.
Given data points $(x_0, y_0), (x_1, y_1), \dots, (x_n, y_n)$, the divided differences are computed recursively:

**1. First order divided differences**
$$
f[x_i, x_{i+1}] = \frac{f(x_{i+1}) - f(x_i)}{x_{i+1} - x_i}
$$
**2. Second order divided differences**
$$
f[x_i, x_{i+1}, x_{i+2}] = \frac{f[x_{i+1}, x_{i+2}] - f[x_i, x_{i+1}]}{x_{i+2} - x_i}
$$
**3. k-th order divided differences**
$$
f[x_i, x_{i+1}, \dots, x_{i+k}] = \frac{f[x_{i+1}, \dots, x_{i+k}] - f[x_i, \dots, x_{i+k-1}]}{x_{i+k} - x_i}
$$

Using the divided differences, [[The Interpolating Polynomial|the interpolating polynomial]] in Newton's form is:
$$
P(x) = f(x_0) + f[x_0, x_1](x - x_0) + f[x_0, x_1, x_2](x - x_0)(x - x_1) + \dots + f[x_0, x_1, \dots, x_n](x - x_0)(x - x_1)\dots(x - x_{n-1})
$$


#### Example

Interpolate the data points $(1, 1),~(2,4),~(3,9)$:

$$
\begin{align*}
f[1,2] &= \frac{4 - 1}{2 - 1} = 3 \\
f[2,3] &= \frac{9 - 4}{3 - 2} = 5
\end{align*}
$$
$$
f[1,2,3] = \frac{5 - 3}{3 - 1} = 1
$$

$$
\begin{align*}
P(x) &= f(x_0) + f[x_0, x_1](x - x_0) + f[x_0, x_1, x_2](x - x_0)(x - x_1) \\
&= 1 + 3(x - 1) + 1(x - 1)(x - 2)\\
&= 1 + 3(x - 1) + [(x - 1)^2 - (x - 1)] \\
&= 1 + 3(x - 1) + (x - 1)^2 - (x - 1) \\
&= 1 + 2(x - 1) + (x - 1)^2 \\
&= [x - 1 + 1]^2 \\
&= x^2
\end{align*}
$$

Thus, the interpolating polynomial is $P(x) = x^2$, which fits the given data points exactly.