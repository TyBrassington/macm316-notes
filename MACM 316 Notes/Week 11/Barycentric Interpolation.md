The barycentric interpolation formula is derived from the [[Legrange Interpolation]] by simplifying its computation through precomputed weights, $w_k$, which allow for a more efficient evaluation.

### 1. Lagrange Interpolating Polynomial
The Lagrange interpolation polynomial $p(x)$ at distinct points $x_0, x_1, \dots, x_n$ is given by:
$$
p(x) = \sum_{k=0}^{n} f(x_k) L_k(x)
$$
where $L_k(x)$ are the Lagrange basis polynomials:
$$
L_k(x) = \prod_{j=0,~j \neq k}^{n} \frac{x - x_j}{x_k - x_j}
$$

### 2. Definition of $\ell(x)$ and Weights for Efficiency
We define the function $\ell(x)$ as:
$$
\ell(x) = (x - x_0)(x - x_1) \cdots (x - x_n) = \prod_{i=0}^{n} (x - x_i)
$$
The direct computation of $L_k(x)$ can be computationally heavy due to the repeated product terms. To address this, we define weights $w_k$ for each term, which involve the [[Derivative|derivative]] of $\ell(x)$ evaluated at the nodes. Specifically:
$$
w_k = \frac{1}{\ell'(x_k)} = \left( \prod_{\substack{i=0 \\ i \neq k}}^{n} (x_k - x_i) \right)^{-1}
$$

### 3. Barycentric Form
Using these weights, we can rewrite $L_k(x)$ in terms of $w_k$, allowing us to avoid recalculating the product terms every time:
$$
L_k(x) = \frac{w_k}{x - x_k} \Bigg/ \sum_{j=0}^{n} \frac{w_j}{x - x_j}
$$
Substituting this back, [[The Interpolating Polynomial|the interpolating polynomial]] $p(x)$ becomes:
$$
p(x) = \frac{\displaystyle\sum_{k=0}^{n} f(x_k) \frac{w_k}{x - x_k}}{\displaystyle\sum_{k=0}^{n} \frac{w_k}{x - x_k}}
$$
