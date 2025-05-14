
Consider the solution of a linear system $A \mathbf{x} = \mathbf{b}$, where $A$ is a nonsingular [[Matrix]]. Let $\mathbf{z}$ be an approximate solution to $\mathbf{x}$, and define:

- **Solution Error:** $\mathbf{e} = \mathbf{x} - \mathbf{z}$
- **Residual Vector:** $\mathbf{r} = \mathbf{b} - A \mathbf{z}$

The residual vector is what is left over when $\mathbf{z}$ is substituted into the linear system. The residual vector $\mathbf{r}$ vanishes ($\mathbf{r} = 0$) if and only if $\mathbf{z}$ is the exact solution (i.e., $\mathbf{z} = \mathbf{x}$).

### Error Bound Theorem

For any natural norm, we have:
$$
\|\mathbf{x} - \mathbf{z}\| \leq \|A^{-1}\| \cdot \|\mathbf{r}\|
$$
Moreover, if $\mathbf{x} \neq 0$ and $\mathbf{b} \neq 0$, we also have:
$$
\underbrace{ \frac{\|\mathbf{x} - \mathbf{z}\|}{\|\mathbf{x}\|} }_{ \text{relative error} } \leq \|A\| \cdot \|A^{-1}\| \cdot \frac{\|\mathbf{r}\|}{\|\mathbf{b}\|}
$$
These results provide bounds on the solution error in terms of the [[Matrix Norm|matrix norm]] and the residual, showing that small residuals don't guarantee small errors, particularly for [[Condition Number#Some properties|ill-conditioned]] matrices.

**Note: $\|A^{-1}\|$ represents the *[[Condition Number|condition number]]* of matrix $A$, often denoted as $\kappa(A)$.**
