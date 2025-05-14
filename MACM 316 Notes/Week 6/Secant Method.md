In order to address the weakness of [[Newton's Method]] which requires us to know the [[Derivative|derivative]] $g'(x)$ which is not practical, we can introduce discrete approximation to $g'(x)$.

We know $f'(x_{n})~=~\lim_{ x \to x_{n}} \frac{f(x)~-~f(x_{n})}{x~-~x_{n}}$

Assume we have the two previous approximations, and let $x~=~x_{n-1}$; then
$$
f'(x_{n})~\approx \frac{f(x_{n})~-~f(x_{n-1})}{x_{n}~-~x_{n-1}}
$$

Substituting this into Newton's Method we get:
$$
x_{n+1}~=~x_{n}~-\frac{f(x_{n})}{f'(x_{n})}\approx ~x_{n}~-\frac{f(x_{n})}{\left( \frac{f(x_{n})~-~f(x_{n-1})}{x_{n}~-~x_{n-1}} \right)}~=~x_{n}~-\frac{f(x_{n})(x_{n}~-~x_{n-1})}{f(x_{n})~-~f(x_{n-1}) }
$$
### Convergence of Secant Method

For secant method, if $(x_{n}~-~p)$ is small enough,
$$
|x_{n+1}~-~p|~\approx~\lambda|x_{n}~-~p|^{\alpha},~~~~where~~\alpha~=\underbrace{ \frac{1+\sqrt{ 5 }}{2} }_{ the~golden~ratio~\approx~1.618 }~>~1
$$
Therefore, the secant method has **superlinear** convergence. It converges slightly slower than Newton's method, but is still faster than [[Bisection Method|bisection method]] or general [[Fixed-Point Iteration|fixed point iteration]]

The secant method requires only one function evaluation per iteration while Newton's Method needs two.