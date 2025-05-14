A **vector norm** on $\mathbb{R}^{n}$ is a function $||\cdot||$ from $\mathbb{R}^{n}~to~\mathbb{R}$ with the following properties:

- $||x||~\geq~0~for~all~x~\epsilon~\mathbb{R}^{n}$
- $||x||~=~0$ if and only if $x=0=[0,~0,~\dots~0]^{T}$
- $||\alpha x||=|\alpha|~||x||$ for all $\alpha~\epsilon~\mathbb{R}$ and $x\epsilon~\mathbb{R}^{n}$
- $||x+y||~\leq||x||+||y||~for~all~x,~y~\epsilon~\mathbb{R}^{n}$     (triangle inequality)

The $l_{2}$ norm (or Euclidean norm) of $x$ if defined by
$$
||x||_{2}~=~\sqrt{ x_{1}^{2}~+~x_{2}^{2}~+\cdots+~x_{n}^{2} }~=~\left[ \sum_{i=1}^{n} x_{i}^{2} \right]^{\frac{1}{2}}
$$
The $l_{\infty}$ norm (or maximum norm) of $x$ if defined by
$$
||x||_{\infty}=\max\limits_{1 \leq i \leq n}|x_{i}|
$$
The $l_{1}$ norm (or Manhattan/taxicab norm) of $x$ if defined by
$$
||x||_{1}~=~|x_{1}|~+~|x_{2}|+~\cdots~+~|x_{n}|~=~\sum_{i=1}^{n}|x_{i}|
$$
### Distance

Given a norm $||\cdot||$, the **distance** between vectors $x$ and $y$ is the norm of the difference:
$$
d(x,y)~=~||x-y||
$$
Correspondingly to above, one has the distances between the vectors measured in these norms. In particular, the $\ell_2$ and $\ell_\infty$ distances between $\mathbf{x}, \mathbf{y} \in \mathbb{R}^n$ are:
$$
\|\mathbf{x} - \mathbf{y}\|_2 = \left[ \sum_{i=1}^{n} (x_i - y_i)^2 \right]^{1/2}, \quad
\|\mathbf{x} - \mathbf{y}\|_\infty = \max_{1 \leq i \leq n} |x_i - y_i|;
$$
observe that the $\ell_2$ distance corresponds to the usual geometric notion of distance in $\mathbb{R}^n$.

#### Example

$$
\mathbf{x} = \begin{bmatrix} -1 \\ 0 \\ 2 \end{bmatrix}, \quad \mathbf{y} = \begin{bmatrix} 3 \\ -1 \\ 4 \end{bmatrix} \quad \Longrightarrow \quad \mathbf{y} - \mathbf{x} =~\begin{bmatrix}
4 \\
-1 \\
2
\end{bmatrix}
$$
- $\ell_\infty$ distance: $\|\mathbf{y} - \mathbf{x}\|_\infty =~4$
- $\ell_2$ distance: $\|\mathbf{y} - \mathbf{x}\|_2 = \sqrt{ 4^{2}~+~(-1)^{2}~+~2^{2}}~=~\sqrt{ 21 }$
- $\ell_1$ distance: $\|\mathbf{y} - \mathbf{x}\|_1 = |4|+|-1|+|2|=7$

