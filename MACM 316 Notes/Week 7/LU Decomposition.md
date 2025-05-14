xIf Gaussian elimination can be performed on the system $AX=b$ without row interchanges, then the [[Matrix]] A can be factored as the product of a lower triangular matrix L and an upper triangular matrix U:
$$
A=LU=
\begin{bmatrix}
l_{11} & 0 & \cdots & 0 \\
l_{21} & l_{22} & \cdots & 0 \\
\vdots & \vdots & \ddots & \vdots \\
l_{n1} & l_{n2} & \cdots & l_{nn}
\end{bmatrix}
\begin{bmatrix}
u_{11} & u_{12} & \cdots & u_{1n} \\
0 & u_{22} & \cdots & u_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
0 & 0 & \cdots & u_{nn}
\end{bmatrix}
$$
Set the intermediate vector $Y~=~UX$:
$$
AX=b~\to~L\underbrace{ UX }_{ Y~=~UX}=b~\to~LY~=~b
$$
Solve for $y$ using $LY=b$ using forward substitution:
$$
\begin{bmatrix}
l_{11} & 0 & \cdots & 0 \\
l_{21} & l_{22} & \cdots & 0 \\
\vdots & \vdots & \ddots & \vdots \\
l_{n1} & l_{n2} & \cdots & l_{nn}
\end{bmatrix}
\begin{bmatrix}
y_{1} \\
y_{2} \\
\vdots \\
y_{n}
\end{bmatrix}
=
\begin{bmatrix}
b_{1} \\
b_{2} \\
\vdots \\
b_{n}
\end{bmatrix}
$$
Having computed $y$, solve $UX=Y$ using back substitution:
$$
\begin{bmatrix}
u_{11} & u_{12} & \cdots & u_{1n} \\
0 & u_{22} & \cdots & u_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
0 & 0 & \cdots & u_{nn}
\end{bmatrix}
\begin{bmatrix}
x_{1} \\
x_{2} \\
\vdots \\
x_{n}
\end{bmatrix}
=
\begin{bmatrix}
y_{1} \\
y_{2} \\
\vdots \\
y_{n}
\end{bmatrix}
$$

LU decomposition only takes $2n^{2}~=~\mathcal{O}(n^{2})$ operations versus $2n^{3}~=~\mathcal{O}(n^{3})$ operations by solving $AX~=~b$ using $A^{-1}$.