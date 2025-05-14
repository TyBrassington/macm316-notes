For higher derivatives (such as $f''(x)$), it is usually easier to use [[Taylor Series|Taylor polynomials]] than [[Legrange Interpolation|Legrange interpolation]].

---

### Taylor's Theorem

Taylor's theorem expands a function $f(x)$ around a point $x_0$ as:

$$
f(x_0 + h) = f(x_0) + h f'(x_0) + \frac{1}{2} h^2 f''(\xi),
$$

where $\xi$ is some point between $x_0$ and $x_0 + h$.

---

### Derivation of the Forward Difference Formula

To approximate the derivative $f'(x_0)$, we start with Taylor's theorem:

$$
f(x_0 + h) = f(x_0) + h f'(x_0) + \frac{1}{2} h^2 f''(\xi).
$$

Rearranging terms:

$$
f'(x_0) = \frac{f(x_0 + h) - f(x_0)}{h} - \frac{1}{2} h f''(\xi).
$$

### Forward Difference Formula

By neglecting the truncation error term $-\frac{1}{2} h f''(\xi)$, we arrive at the **forward difference approximation**:

$$
f'(x_0) \approx \frac{f(x_0 + h) - f(x_0)}{h}.
$$

---

### Truncation Error

The truncation error arises from neglecting higher-order terms in Taylor's expansion. For the forward difference formula, the error is:

$$
\text{Error} = -\frac{1}{2} h f''(\xi),
$$

where $\xi$ lies between $x_0$ and $x_0 + h$. The error depends on:

- The step size $h$: Smaller $h$ reduces the error.
- The second derivative $f''(\xi)$: A larger curvature leads to higher error.

---

### Higher-Order Taylor Expansions

Including more terms from Taylor's theorem provides additional information about the error. For instance:

$$
f(x_0 + h) = f(x_0) + h f'(x_0) + \frac{1}{2} h^2 f''(x_0) + \frac{1}{3!} h^3 f'''(x_0) + \frac{1}{4!} h^4 f^{(4)}(\xi).
$$

This allows for deriving higher-order difference formulas and analyzing their error more precisely.


![[Pasted image 20241209015506.png]]
![[Pasted image 20241209015642.png]]