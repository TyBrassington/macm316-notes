	 ### Definition

Given $n + 1$ data points $(x_0, y_0), (x_1, y_1), \dots, (x_n, y_n)$ with $x_0 < x_1 < \cdots < x_n$, the **Lagrange (basis) polynomial** $L_{k}(x)$ is defined for each $k = 0, 1, \dots, n$ and is the unique polynomial of degree $n$ such that:

$$
L_k(x_j) = \delta_{jk} = \begin{cases}
1, & j = k \\
0, & j \neq k
\end{cases} \quad \text{for } j = 0, 1, \dots, n.
$$

The Lagrange interpolating polynomial $P(x)$ is then constructed as a linear combination of the basis polynomials and is written as:

$$
P(x) = \sum ^{n}_{k=0}y_{k}L_{k}(x)= y_0 L_0(x) + y_1 L_1(x) + \cdots + y_n L_n(x)
$$

More explicitly, the Lagrange interpolating polynomial can be written as:

$$
P(x) = \sum_{i=0}^{n} \left(y_i \prod_{\substack{0 \leq j \leq n \\ j \neq i}} \frac{x - x_j}{x_i - x_j}\right)
$$

### Expanded Form

Alternatively, we can write the expanded version:

$$
y = \frac{(x - x_1)(x - x_2) \cdots (x - x_n)}{(x_0 - x_1)(x_0 - x_2) \cdots (x_0 - x_n)} y_0
  + \frac{(x - x_0)(x - x_2) \cdots (x - x_n)}{(x_1 - x_0)(x_1 - x_2) \cdots (x_1 - x_n)} y_1
  + \cdots
  + \frac{(x - x_0)(x - x_1) \cdots (x - x_{n-1})}{(x_n - x_0)(x_n - x_1) \cdots (x_n - x_{n-1})} y_n
$$

This form emphasizes how the interpolation is built as a weighted sum of the function values $y_i$, with each weight being a product of linear terms involving $x$ and the $x_j$ values from the data points.


#### Example

The equation of the line passing through the points $(x_0, y_0)$ and $(x_1, y_1)$ using Lagrange interpolation is given by:

$$
P(x) = y_0 L_0(x) + y_1 L_1(x)
$$

where the basis polynomials $L_0(x)$ and $L_1(x)$ are:

$$
L_0(x) = \frac{x - x_1}{x_0 - x_1}, \quad L_1(x) = \frac{x - x_0}{x_1 - x_0}
$$

Thus, the **Lagrange interpolation polynomial** is:

$$
P(x) = y_0 \frac{x - x_1}{x_0 - x_1} + y_1 \frac{x - x_0}{x_1 - x_0}
$$

Simplifying:

$$
P(x) = \frac{y_0 (x - x_1) - y_1 (x - x_0)}{x_0 - x_1}
$$

Expanding the numerator:

$$
\begin{aligned}
    y_0 (x - x_1) - y_1 (x - x_0) &= y_0 x - y_0 x_1 - y_1 x + y_1 x_0 \\
                                  &= (y_0 - y_1) x + (y_1 x_0 - y_0 x_1)
\end{aligned}
$$

Thus:

$$
P(x) = \frac{(y_0 - y_1) x + (y_1 x_0 - y_0 x_1)}{x_0 - x_1}
$$

**Final Simplified Form**

The final simplified form of the Lagrange interpolation polynomial for a line through two points $(x_0, y_0)$ and $(x_1, y_1)$ is:

$$
P(x) = \frac{y_0 - y_1}{x_0 - x_1} x + \frac{y_1 x_0 - y_0 x_1}{x_0 - x_1}
$$

This represents the equation of a line passing through the two given points, where:

- The slope is $\frac{y_0 - y_1}{x_0 - x_1}$
- The y-intercept is $\frac{y_1 x_0 - y_0 x_1}{x_0 - x_1}$


#### Example 2

**Finding the Quadratic Interpolating Polynomial and Estimating $f(2.5)$****

Given $f(x) = \frac{1}{x}$ and nodes:

$$
x_0 = 1, \quad x_1 = 2, \quad x_2 = 3
$$

find the quadratic interpolating polynomial $P(x)$ and estimate $f(2.5)$.

**Lagrange Interpolation Formula**

The polynomial $P(x)$ is:

$$
P(x) = y_0 L_0(x) + y_1 L_1(x) + y_2 L_2(x)
$$

where $y_0 = 1$, $y_1 = \frac{1}{2}$, $y_2 = \frac{1}{3}$ and the basis polynomials are:

$$
\begin{align}
L_0(x) &= \frac{(x - x_1)(x - x_2)}{(x_0 - x_1)(x_0 - x_2)} &= \frac{(x - 2)(x - 3)}{2}\\\\
L_1(x) &= \frac{(x - x_0)(x - x_2)}{(x_1 - x_0)(x_1 - x_2)}&=- (x - 1)(x - 3)\\\\
L_2(x) &= \frac{(x - x_0)(x - x_1)}{(x_2 - x_0)(x_2 - x_1)}&= \frac{(x - 1)(x - 2)}{2}

\end{align}
$$

**Constructing and Simplifying $P(x)$**

Substituting the values of $L_0(x)$, $L_1(x)$, and $L_2(x)$:

$$
\begin{align}
P(x) &= 1 \cdot \frac{(x - 2)(x - 3)}{2} + \frac{1}{2} \left( - (x - 1)(x - 3) \right) + \frac{1}{3} \cdot \frac{(x - 1)(x - 2)}{2} \\
&=\frac{1}{6}x^{2}-x+\frac{11}{6}
\end{align}
$$

**Estimating $f(2.5)$**

Substituting $x = 2.5$:
$$ L_0(2.5) = \frac{(2.5 - 2)(2.5 - 3)}{2} = \frac{0.5 \cdot (-0.5)}{2} = -0.125 $$$$ L_1(2.5) = -\frac{(2.5 - 1)(2.5 - 3)}{1} = -(1.5 \cdot (-0.5)) = 0.75 $$ $$ L_2(2.5) = \frac{(2.5 - 1)(2.5 - 2)}{2} = \frac{1.5 \cdot 0.5}{2} = 0.375 $$
Thus:
$$
P(2.5) = -0.125 + 0.375 + 0.125 = 0.375
$$
Exact Value: $$f(2.5)=\frac{1}{2.5}=0.4$$
Estimating $f(2.5)$ by interpolating higher degree polynomials (adding an extra point $x_{j}$) than this quadratic example will result in higher accuracy.