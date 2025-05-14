Bisection Method is an iterative root-finding method that applies to any [[Continuity|continuous]] function on $[a,b]$ that has an $f(a)$ and $f(b)$ with opposite signs:
$$
f(a)\:\cdot\:f(b)<0
$$
If those two conditions are met, then by [[Intermediate Value Theorem|IVT]], $f$ must have a root in $(a,b)$. The method does not require derivative information on $f$.

Note: the method also works if there are multiple roots. This method will only find one; which one it finds depends on the choice of the initial interval.

### Algorithm

1. Calculate $c$, the midpoint of the interval, $c = \frac{a+b}{2}$
2. Check the sign of $f(c)$; hence decide which interval $[a,c]$ or $[c,b]$ contains the root
	1. Repeat Steps 1 and 2 on that smaller interval, successively shrinking the interval containing the root until the [[Stopping Criterion|stopping criteria]] is reached

Bisection Method produces a sequence of $c_1,c_{2}$... of approximations to the true root $p$.

Convergence is slow compared to other algorithms

### Convergence of Bisection Method

Suppose that $f~\epsilon~[a,b]~(b>a)$, and that $f(a)$ and $f(b)$ have opposite signs.
The bisection method generates a sequence {$p_{n}$}$_{n=1,~2,~\dots}$ approximating a root of $f$ with
$$
|p_{n}~-~p|~\leq~ \frac{b~-~a}{2^{n}},~~~~n~\geq~1
$$
Equivalently: $p_{n}~=~p~+~\mathcal{O}(2^{-n})$.

We say that bisection method has **linear convergence** with constant $\lambda~=\frac{1}{2}$ 

### Error of Bisection Method

Let $p$ be the actual root somewhere in the interval $[a,b]$. The bound on the absolute error for $p_{n}$ is:
$$
|e_{abs}|~=~|p_{n}~-~p|~\leq~ \frac{b_{n}-a_{n}}{2}
$$
The size of the interval is reduced by a factor of 2 at every step; hence so is the error bound.

![[bisection-diagram.png]]
