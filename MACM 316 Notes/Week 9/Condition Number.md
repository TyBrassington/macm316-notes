The **condition number** of a nonsingular [[Matrix|matrix]] $A$ (with respect to the [[Matrix Norm|norm]] $\|\cdot\|$) is defined as

$$
\kappa(A) = \|A\| \, \|A^{-1}\|.
$$
The condition number tells us how confident we can be in the solution if the residual is small.
$$
\frac{\|\mathbf{e}\|}{\|\mathbf{x}\|} = \frac{\|\mathbf{x} - \mathbf{z}\|}{\|\mathbf{x}\|} \leq \kappa(A) \frac{\|\mathbf{r}\|}{\|\mathbf{b}\|}
$$
#### Some properties
- If $A$ is singular, then we define $\kappa(A) = \infty$.
- The condition number depends on the norm: we denote this explicitly by $\kappa_1(A)$, $\kappa_2(A)$, $\kappa_\infty(A)$.
- $\kappa(I) = 1$ for the identity matrix $I$ (for any norm $\|\cdot\|$).
- For any natural norm $\|\cdot\|$, we have $\kappa(A) \geq 1$, since
- $\kappa(\alpha A) = \kappa(A)$ for any scalar $\alpha \neq 0$.
- The size of $\kappa(A)$ indicates how close a matrix is to being singular; it is a more reliable measure than the determinant $\det A$!

An $n~\times~n$ matrix is said to be:
- **well-conditioned** if the condition number $\kappa(A)$ is "small" (near / slightly above 1)
- **ill-conditioned** if $\kappa(A) \gg 1$ (large condition number $\Longrightarrow$ $A$ is close to singular)


### Example 1: Calculate Condition Number in $\|\cdot\|_2$ Norm

Given:

$$
A = \begin{bmatrix} 1 & 2 \\ 3 & 4 \end{bmatrix},
$$

1. Compute the $\|A\|_2$ (2-norm of $A$):
   - The 2-norm is the largest singular value of $A$.

2. Compute $\|A^{-1}\|_2$:
   - First, calculate $A^{-1}$: 
   $$
   A^{-1} = \frac{1}{\det A} \begin{bmatrix} 4 & -2 \\ -3 & 1 \end{bmatrix},
   $$
   where:
   $$
   \det A = (1)(4) - (2)(3) = -2.
   $$
   Substituting:
   $$
   A^{-1} = \begin{bmatrix} -2 & 1 \\ 1.5 & -0.5 \end{bmatrix}.
   $$
   - Then compute the 2-norm of $A^{-1}$.

3. Finally, calculate the condition number: $$ \kappa_2(A) = \|A\|_2 \cdot \|A^{-1}\|_2. $$ Substituting the values: $$ \kappa_2(A) = 5.464985 \cdot 7.928203 = 43.047027. $$

If $\kappa_2(A)$ is large (e.g., $\gg 1$), then $A$ is ill-conditioned.

---

### Example 2: Residual Analysis for Solution Accuracy

Consider a system $A \mathbf{x} = \mathbf{b}$ with approximate solution $\mathbf{z}$ and residual $\mathbf{r} = \mathbf{b} - A\mathbf{z}$:

Let 

$$
A = \begin{bmatrix} 1 & 3 \\ 2 & 4 \end{bmatrix}, \quad \mathbf{b} = \begin{bmatrix} 7 \\ 10 \end{bmatrix}, \quad \mathbf{z} = \begin{bmatrix} 1 \\ 2 \end{bmatrix}.
$$

1. Compute the residual $\mathbf{r}$:
   $$
   \mathbf{r} = \mathbf{b} - A\mathbf{z}.
   $$
   Substitute the values:
   $$
   \mathbf{r} = \begin{bmatrix} 7 \\ 10 \end{bmatrix} - \begin{bmatrix} 1 & 3 \\ 2 & 4 \end{bmatrix} \begin{bmatrix} 1 \\ 2 \end{bmatrix}.
   $$
   Perform the [[Matrix Multiplication|matrix multiplication]]:
   $$
   A\mathbf{z} = \begin{bmatrix} (1)(1) + (3)(2) \\ (2)(1) + (4)(2) \end{bmatrix} = \begin{bmatrix} 7 \\ 10 \end{bmatrix}.
   $$
   Hence:
   $$
   \mathbf{r} = \begin{bmatrix} 7 \\ 10 \end{bmatrix} - \begin{bmatrix} 7 \\ 10 \end{bmatrix} = \begin{bmatrix} 0 \\ 0 \end{bmatrix}.
   $$

2. Analyze the error:
   $$
   \frac{\|\mathbf{e}\|}{\|\mathbf{x}\|} \leq \kappa(A) \frac{\|\mathbf{r}\|}{\|\mathbf{b}\|}.
   $$

Since $\|\mathbf{r}\| = 0$, the solution $\mathbf{z}$ is exact. For non-zero $\|\mathbf{r}\|$, a large $\kappa(A)$ amplifies residual errors, reducing confidence in the solution.




#### **Key Properties**

- $\kappa(A) = \infty$ if $A$ is singular.
- Depends on the norm: $\kappa_1(A)$, $\kappa_2(A)$, $\kappa_\infty(A)$.
- $\kappa(I) = 1$, and $\kappa(A) \geq 1$ for natural norms.
- $\kappa(\alpha A) = \kappa(A)$ for $\alpha \neq 0$.
- Large $\kappa(A)$ means $A$ is close to singular.

#### **Conditioning**

- **Well-conditioned**: $\kappa(A)$ close to 1.
- **Ill-conditioned**: $\kappa(A) \gg 1$.