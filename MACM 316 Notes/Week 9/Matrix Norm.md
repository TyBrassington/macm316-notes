
A [[Matrix]] norm $\|\cdot\|$ on the set of all $n \times n$ matrices is a real-valued function (from $\mathbb{R}^{n \times n}$ to $\mathbb{R}$) satisfying the following properties:

For any $n \times n$ matrices $A$, $B$ and scalars $\alpha \in \mathbb{R}$,

- $\|A\| \geq 0$
- $\|A\| = 0$ if and only if $A = 0$ (the zero matrix)
- $\|\alpha A\| = |\alpha| \|A\|$
- $\|A + B\| \leq \|A\| + \|B\|$
- $\|A B\| \leq \|A\| \|B\|$


A matrix norm, like a [[Vector Norm|vector norm]], measures the "size" of a matrix, but may also account for matrix-specific properties, such as how much it stretches vectors.

Given any vector norm $\|\cdot\|$ on $\mathbb{R}^n$, we can define the **natural** (or **induced**) matrix norm:

$$
\|A\| = \max_{\|\mathbf{x}\|=1} \|\mathbf{A x}\|~\Longrightarrow~\|A\vec{y}\|~\leq~\|A\|~\|\vec{y}\|,\text{ for any }\vec{y}\neq0
$$

If $A = [a_{ij}]$ is an $n \times n$ matrix, then

$$
\|A\|_\infty = \max_{1 \leq i \leq n} \sum_{j=1}^n |a_{ij}|
$$

i.e. the matrix $\ell_\infty$ norm is the **maximum row sum** (of absolute values of the entries).
#### Example

Find $\|A\|_\infty$ for the matrix

$$
\begin{bmatrix}
2 & -1 & 0 \\
3 & -3 & -1 \\
-4 & 2 & 0 
\end{bmatrix}.
$$
**Row sums:**
- Row 1: $\sum_{j=1}^3 |a_{1j}| =~|2|+|-1|+|0|=3$
- Row 2: $\sum_{j=1}^3 |a_{2j}| =|3|+|-3|+|-1|=7$
- Row 3: $\sum_{j=1}^3 |a_{3j}| =|-4|+|2|+|0|=6$

Therefore, $\|A\|_{\infty}~=~7$

It turns out:
- The matrix $\ell_1$ norm is the **maximum column sum**
- The matrix $\ell_2$ norm requires the calculation of eigenvalues

### Summary
$$
\begin{align*}
\|A\|_{1}~&=~\text{maximum column sum}~\\
\|A\|_{\infty}~&=~\text{maximum row sum}~\\
\|A\|_{2}~&=~[p(A^{T}A)]^{1/2}~\\
&=\rho(A)~\text{if A is symmetric}

\end{align*}

$$
$$
\rho(A)~=~max|\lambda|
$$