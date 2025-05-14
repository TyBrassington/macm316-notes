### Background discussion

We know   $\sin(x) = x - \frac{x^3}{6} + \frac{x^5}{120} + \cdots$
For "small" $x$ (in the [[Limits|limit]] $x \to 0$) we can say     $\sin x = x + \mathcal{O}(x^{3})$,     or     $\sin x - x = \mathcal{O}(x^{3})$

As $x \to 0$, the higher power terms approach zero much faster than the $x^{3}$ term, thus for sufficiently small $x$, the $-\frac{1}{6}x^{3}$ is the largest, dominant term on the right hand side, and this determines the rate of convergence

### Big-O Notation for Functions

We use Big O notation for the rate at which functions converge by describing how quickly a function approaches a limit as a variable $h \to 0$

Suppose $\lim_{h \to 0} f(h) = L$, and $\lim_{h \to 0} g(h) = 0$. If a (finite) positive constant $K$ exists such that
$|f(h) - L| \leq K|g(h)|$ for all sufficiently small $h$, then we write 
$$f(h) = L + \mathcal{O}(g(h)) \quad \text{(as } h \to 0).$$
The above equation essentially means that the difference between the limit $L$ and $f(h)$ shrinks at a rate proportional to $g(h)$ as $h$ approaches $0$. This gives us a formal way to express how quickly $f(h)$ converges to $L$.

Smaller growth rates of g(h) indicates faster convergence.

##### Example

Find the rates of convergence for the below function as $h \to 0$:
$$
\lim_{h \to 0} \frac{\sin h}{h} = 1
$$

Using the [[Taylor Series|Taylor]] expansion of $\sin h$:
$$
\sin h = h - \frac{h^3}{6} + \mathcal{O}(h^5)
$$

Substituting this into $\frac{\sin h}{h}$ , we get:
$$
\frac{\sin h}{h} = 1 - \frac{h^2}{6} + \mathcal{O}(h^4)
$$

The dominant term in this question is $-\frac{h^{2}}{6}$, therefore, the rate of convergence is $\mathcal{O}(h^2)$.
