The spectral radius of a square [[Matrix]] $A$ is the largest absolute value of it eigenvalues and is defined by
$$
\rho(A)~=~max|\lambda|,~~~~~\text{where }\lambda \text{ is an eigenvalue of}~A
$$

- For any natural (induced) matrix for, $\|\cdot\|$, we have $\rho(A)~\leq~\|A\|$
- The matrix $\ell_{2}$ norm satisfies $\|A\|_{2}~=~\left[\rho(A^{T}A)\right]^{\frac{1}{2}}$
- If $A$ is symmetric, than $\|A\|_{2}~=~\rho(A)$

#### Example

Find $\|A\|_2$ for the matrix 
$$
A~=~\begin{bmatrix}
\frac{3}{2} & \frac{1}{2} \\
\frac{1}{2} & 1
\end{bmatrix}
$$
$A$ is symmetric, so $\|A\|_{2}~=~\rho(A)$

**Eigenvalues of A:**
$$
\begin{align*} 
\det(A - \lambda I) &= \det \begin{bmatrix} \frac{3}{2} - \lambda & \frac{1}{2} \\ \frac{1}{2} & 1 - \lambda \end{bmatrix} \\ &= \left( \frac{3}{2} - \lambda \right) \left(1 - \lambda\right) - \frac{1}{4} \\ &= \lambda^{2} - \frac{5}{2}\lambda - \frac{5}{4} = 0 
\end{align*}

$$
$$
\Longrightarrow \lambda~=\frac{\frac{5}{2}\pm \sqrt{ \frac{25}{4}-4\left( \frac{5}{4} \right) }}{2}~=~\left( \frac{\frac{5}{2}~\pm \sqrt{ \frac{5}{4} }}{4}\right)~=~\frac{5~\pm~\sqrt{ 5 }}{4}
$$
So $\|A\|_{2}~=~\rho(A)~=~max|\lambda|~= \frac{5~+~\sqrt{ 5 }}{4}$






