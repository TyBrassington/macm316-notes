A number is a **fixed point** for a function $g$ if $g(p)~=~p$. 
![[fixed-point-ex.png]]

Fixed point iteration has the form, given $x_{0}$:
$$
x_{n+1}~=~g(x_{n})~~~~~n~=~0,~1,~2,~\dots
$$
If the sequence {$x_{n}$} converges to a value $p~(\lim_{ n \to \infty }x_{n}~=~p)$, then $p$ must be a fixed point of $g$
### Example

![[fixed-point-ex-2.png]]



### Termination of Sequence

When doing fixed-point iteration, evaluate $x_{n+1}~=~g(x_{n})$ until $|x_{n+1}~-~x_{n}|~<~TOL$ or the maximum iteration count defined by the [[Stopping Criterion|stopping criteria]] is exceeded.

### Convergence of Fixed-Point Iteration

For some $\xi_{n}$ between $x_{n}$ and $p$, we have:
$$
x_{n+1}~-~p~=~g(x_{n})~-~g(p)~=~g'(\xi_{n})(x_{n}~-~p)
$$
(this is the Taylor polynomial approximation of degree 0 with remainder, equivalent to [[Mean Value Theorem]])

![[fixed-point-convergence.png]]
