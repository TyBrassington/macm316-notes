Newton's Method is a special case of [[Fixed-Point Iteration|fixed point iteration]] for a function $g(x)$ where:
$$
x_{n+1}~=~x_{n}- \frac{g(x_{n})}{g'(x_{n})}
$$
Newton's Method for $f(x)~=~0$ **requires the [[Derivative|derivative]]** $f'(x)$, requires $f'(x_{n})~\neq~0~for~all~n$
### Derivation from Fixed-Point Iteration

We know that the iterative equation for fixed point iteration is $x_{n+1}~=~f(x_{n})$.
So if we set $f(x)~=~x~-\frac{g(x)}{g'(x)}$, then we will observe that Newton's Method is indeed a special case of fixed point iteration. Therefore, most of what applies to fixed-point will also apply to Newton's Method.

### Convergence of Newton's Method

Let $f~\epsilon~C^{2} [a,b],$ and let $p~\epsilon~(a,b)$ be a root of $f:~f(p)~=~0.$
Then there exists $\delta~>~0$ so that for every initial guess $x_{0}~\epsilon~[p~-~\delta,~p~+~\delta]$, Newton's method generates a sequence {$x_{n}$}$_{n~=~1,~2,\dots}$ converging to $p$

If $p$ is a simple root of $f~(i.e.~f'(p)~\neq~0)$, Newton's method converges (at least) **quadratically** (the correct number of significant digits approximately *doubles* at each iteration)
$$
\lim_{ n \to \infty } \frac{|x_{n+1}~-~p|}{|x_{n}~-~p|^{2}}~=~\lambda,~~~~~~~~~where~~~\lambda~=~\frac{1}{2}|g''(p)|~=~ \frac{|f''(p)|}{2|f'(p)|}~(for~f~\epsilon~C^{3})
$$
Convergence of Newton's Method is only guaranteed if the initial value $x_{0}$ is sufficiently close enough to the root.

In practice, it is good to apply a few steps of [[Bisection Method]] to get close to the root, before using the much faster Newton's Method to refine the approximation.

If the initial value $x_{0}$ is too far from the root, then Newton's method may not converge: it could oscillate, jump back and forth around a local extremum, and more unpredictable behaviour.
![[unpredictable-behaviour-newtons-method.png]]

#### Convergence at higher multiplicity (m $\geq$ 1)

Let $p$ be a [[Root of Multiplicity|root of multiplicity]] $m$ of $f(x)~\epsilon~C^{m}[a,b]:~~f(x)~=~(x~-~p)^{m} q(x)$ with $q(p)~\neq~0$
Define $\mu(x)~=\frac{f(x)}{f'(x)}$; then a calculation shows that $\mu(p)~=~0$ and $\mu'(p)~=\frac{1}{m}$:
$$
\mu(p)~=\frac{f(x)}{f'(x)}~=\frac{(x~-~p)^{m}q(x)}{m(x-p)^{m-1}~+~(x-p)^{m}q'(x)}
$$
If $p$ is a root of $f~$ of *multiplicity $m$*, then for $g(x)~=~x~-\frac{f(x)}{f'(x)}$ we have:
$$
g(p)~=~p~~~~and~~~~g'(p)~=~1-\frac{1}{m}
$$
If m = 1 ($p$ is a simple root), then g'(p) = 0: Newton's Method converges quadratically
If m > 1 ($p$ is a repeated root), then Newton's Method converges **linearly**, with a convergence rate:
$$
\underbrace{ 1~-\frac{1}{m} }_{ slower~convergence~for~higher~multiplicity~m }
$$

### Relaxed Newton's Method

If $p$ is known to have multiplicity $m$, then replace the Newton iteration with
$$
x_{n+1}~=~x_{n}~-\underbrace{ \frac{g(x_{n})}{g'(x_{n})} }_{ \mu(x) }
$$
### Modified Newton's Method

If $f$ has a root of multiplicity $m$ > 1 at $x~=~p$, the $\mu(x)$ has a simple root at $x~=~p$. Therefore we can modify Newton's Method as follows:
$$
x_{n+1}~=~f(x_{n}),~~~~where~~f(x)~=~x~-\frac{\mu(x)}{\mu'(x)}~=~x~-\frac{g(x)g'(x)}{[g'(x)]^{2}~-~g(x)g''(x)}
$$

Note: this approaches requires calculation of second derivative $g''(x)$ and is less robust to [[Round-off error|round-off error]] due to [[Amplification of Round-off Error#Subtractive Cancellation|subtractive cancellation]] errors in the denominator
### Termination of Sequence

Just like [[Fixed-Point Iteration#Termination of Sequence|fixed-point termination of sequence]], it is important to implement a stopping criteria. You should also check to see if the iterates begin to diverge to $\pm \infty$ when implementing the criterion.

