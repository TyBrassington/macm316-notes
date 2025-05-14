
Least-squares approximation fits a function to data points $(x_1, y_1), (x_2, y_2), \dots, (x_m, y_m)$, minimizing the [[Error Bounds for Linear Systems|error]] without requiring the function to pass through all points.

---

### Calculating the Least Squares Polynomial

To compute the linear least squares polynomial for a dataset, assume the linear model:
$$
y = ax + b
$$
where $a$ (slope) and $b$ (intercept) are to be determined.

#### 1. Construct the design [[Matrix|matrix]] and vector

For a dataset with $n$ points $(x_i, y_i)$, define the design matrix $A$ and the vector $y$:
   $$
   A = \begin{bmatrix} x_1 & 1 \\ x_2 & 1 \\ \vdots & \vdots \\ x_n & 1 \end{bmatrix}, \quad
   y = \begin{bmatrix} y_1 \\ y_2 \\ \vdots \\ y_n \end{bmatrix}.
   $$

#### 2. Derive the least-squares solution formula

Compute $\begin{bmatrix} a \\ b \end{bmatrix}$ using:
   $$
   \begin{bmatrix} a \\ b \end{bmatrix} = (A^T A)^{-1} A^T y,
   $$
where:
   - $A^T$ is the transpose of $A$,
   - $(A^T A)^{-1}$ is the inverse of $A^T A$.

#### 3. Compute intermediate matrices ($A^{T}A$ and $A^{T}y$)

$$
     A^T A = \begin{bmatrix}
     \sum x_i^2 & \sum x_i \\
     \sum x_i & n
     \end{bmatrix}.
     $$

$$
     A^T y = \begin{bmatrix}
     \sum x_i y_i \\
     \sum y_i
     \end{bmatrix}.
     $$

#### 4. Solve for $\begin{bmatrix} a \\ b \end{bmatrix}$

Substitute the values into:
   $$
   \begin{bmatrix} a \\ b \end{bmatrix} = \left( \begin{bmatrix}
   \sum x_i^2 & \sum x_i \\
   \sum x_i & n
   \end{bmatrix} \right)^{-1} \begin{bmatrix}
   \sum x_i y_i \\
   \sum y_i
   \end{bmatrix}.
   $$

#### 5. Formulate the resulting polynomial  

Substitute the computed $a$ and $b$ into:
$$
   y = ax + b.
   $$

---

### Example (Section 8.1 #1)

#### 1. Define the dataset
Given:
$$ x_i = [0, 0.25, 0.50, 0.75, 1.00], \quad y_i = [1.0000, 1.2840, 1.6487, 2.1170, 2.7183]. $$

The design matrix $A$ is:
$$
A = \begin{bmatrix} x_1 & 1 \\ x_2 & 1 \\ \vdots & \vdots \\ x_n & 1 \end{bmatrix} = \begin{bmatrix} 0 & 1 \\ 0.25 & 1 \\ 0.50 & 1 \\ 0.75 & 1 \\ 1.00 & 1 \end{bmatrix}.
$$

#### 2. Compute $A^T A$
$$
A^T A = \begin{bmatrix} \sum x_i^2 & \sum x_i \\ \sum x_i & n \end{bmatrix}.
$$

For this dataset:
$$
\sum x_i^2 = 0^2 + 0.25^2 + 0.50^2 + 0.75^2 + 1.00^2 = 1.875, \quad
\sum x_i = 0 + 0.25 + 0.50 + 0.75 + 1.00 = 2.5, \quad
n = 5.
$$

Thus:
$$
A^T A = \begin{bmatrix} 1.875 & 2.5 \\ 2.5 & 5 \end{bmatrix}.
$$

#### 3. Compute $A^T y$
$$
A^T y = \begin{bmatrix} \sum x_i y_i \\ \sum y_i \end{bmatrix}.
$$

For this dataset:
$$
\sum x_i y_i = 0 \cdot 1.0000 + 0.25 \cdot 1.2840 + 0.50 \cdot 1.6487 + 0.75 \cdot 2.1170 + 1.00 \cdot 2.7183 = 5.8751,
$$
$$
\sum y_i = 1.0000 + 1.2840 + 1.6487 + 2.1170 + 2.7183 = 8.768.
$$

Thus:
$$
A^T y = \begin{bmatrix} 5.8751 \\ 8.768 \end{bmatrix}.
$$

#### 4. Compute $(A^T A)^{-1}$
The determinant of $A^T A$ is:
$$
\text{det}(A^T A) = (1.875)(5) - (2.5)(2.5) = 9.375 - 6.25 = 3.125.
$$

The inverse is:
$$
(A^T A)^{-1} = \frac{1}{\text{det}(A^T A)} \begin{bmatrix} 5 & -2.5 \\ -2.5 & 1.875 \end{bmatrix} = \frac{1}{3.125} \begin{bmatrix} 5 & -2.5 \\ -2.5 & 1.875 \end{bmatrix}.
$$

Thus:
$$
(A^T A)^{-1} = \begin{bmatrix} 1.875 & -0.9375 \\ -0.9375 & 0.703125 \end{bmatrix}.
$$

#### 5. Solve for $\begin{bmatrix} a \\ b \end{bmatrix}$
$$
\begin{bmatrix} a \\ b \end{bmatrix} = (A^T A)^{-1} A^T y.
$$

Substituting values:
$$
\begin{bmatrix} a \\ b \end{bmatrix} = \begin{bmatrix} 1.875 & -0.9375 \\ -0.9375 & 0.703125 \end{bmatrix} \begin{bmatrix} 5.8751 \\ 8.768 \end{bmatrix}.
$$

Computing:
$$
a = (1.875)(5.8751) + (-0.9375)(8.768) = 11.0157 - 8.20786 = 1.70784,
$$
$$
b = (-0.9375)(5.8751) + (0.703125)(8.768) = -5.50747 + 6.40715 = 0.89968.
$$

Thus:
$$
\begin{bmatrix} a \\ b \end{bmatrix} = \begin{bmatrix} 1.70784 \\ 0.89968 \end{bmatrix}.
$$

#### 6. Resulting polynomial
The linear least squares polynomial is:
$$
y = 1.70784x + 0.89968.
$$
