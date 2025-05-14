### [[Limits]]

A function $f$ defined on a set $X$ of real numbers has the **[[Limits|limit]]** $L$ at $x_0$, written
$$
\lim_{ n \to \infty } f(x) = L 
$$
### [[Continuity]]

Let $f$ be a function defined on a set $X$ of real numbers and $x_{0}  \epsilon  X$ . Then $f$ is **[[Continuity|continuous]]** at $x_{0}$ if
$$
\lim_{ x \to \infty } f(x) = f(x_{0}).
$$
continue expanding after midterm

### [[Intermediate Value Theorem]]

Let $f \,\epsilon \, C[a,b];$ and let $K \epsilon \mathbb{R}$ be any number between $f(a)$ and $f(b)$. Then there exists a $c \epsilon (a,b)$ so that $f(c) = K$.

![[ivt.png]]

IVT is commonly used to locate zeroes (roots) of functions.

### [[Extreme Value Theorem]]

If a function $f(x)$ is [[Continuity|continuous]] on a closed interval $[a,b]$, then $f(x)$ has both a maximum and minimum value on $[a,b]$.

![[evt.png]]
### [[Rolle's Theorem]]

If a real-valued function $f$ is [[Continuity|continuous]] on a closed interval $[a,b]$, differentiable on the open interval $(a,b)$, and $f(a)=f(b)$, then there exists at least one $c$ in the open interval $(a,b)$ such that $f'(c)=0$

![[rolles.png]]

### [[Mean Value Theorem]]

Let $f\,:\,[a,b] \to \mathbb{R}$ be a [[Continuity|continuous]] function on $[a,b]$, and differentiable on $(a,b)$, where $a<b$. Then there exists some $c$ in $(a,b)$ such that $f'(c) = \frac{f(b)-f(a)}{b-a}$

MVT is a generalization of [[Rolle's Theorem]], which assumes $f(a)=f(b)$, so that the right-hand side above is zero

![[mvt.png]]

### Taylor Series Expansion

The [[Taylor Series]] of a function is an infinite sum of terms that are expressed in terms of the function's derivatives at a single point. A [[Taylor Series]] about the point 0 is called a [[Maclaurin Series]].

##### Taylor Series Definition
$$
f(x) = f(a) + f'(a)(x - a) + \frac{f''(a)}{2!}(x - a)^2 + \frac{f^{(3)}(a)}{3!}(x - a)^3 + \cdots + \frac{f^{(n)}(a)}{n!}(x - a)^n
 = \sum_{n=0}^{\infty} \frac{f^{(n)}(a)}{n!}(x-a)^{n}

$$
##### Maclaurin Series Definition
$$
f(x) = f(0) + f'(0)x + \frac{f''(0)}{2!}x^2 + \frac{f^{(3)}(0)}{3!}x^3 + \cdots + \frac{f^{(n)}(0)}{n!}x^n + \cdots
= \sum_{n=0}^{\infty} \frac{f^{(n)}(0)}{n!}x^{n}
$$
##### Alternative Formulation
Let $x = x_0 + h$, so $h = x - x_0$; then replace $x_0$ with $x$.

$$
f(x + h) = f(x) + f'(x)h + \frac{1}{2}f''(x)h^2 + \cdots + \frac{1}{n!}f^{(n)}(x)h^n + \underbrace{\frac{1}{(n + 1)!} f^{(n+1)}(\xi) h^{n+1}}_{\text{error } R_n}

$$
### Common Taylor Series Expansions

$$
e^x = 1 + x + \frac{x^2}{2!} + \frac{x^3}{3!} + \frac{x^4}{4!} + \frac{x^5}{120} + \cdots = \sum_{n=0}^{\infty} \frac{x^n}{n!}
$$
$$
\cos(x) = 1 - \frac{x^2}{2} + \frac{x^4}{24} + \cdots = \sum_{n=0}^{\infty} (-1)^n \frac{x^{2n}}{(2n)!}
$$
$$
\sin(x) = x - \frac{x^3}{6} + \frac{x^5}{120} + \cdots = \sum_{n=0}^{\infty} (-1)^n \frac{x^{2n+1}}{(2n+1)!}
$$
$$
\ln(1+x) = x - \frac{x^2}{2} + \frac{x^3}{3} - \frac{x^4}{4} + \frac{x^5}{5} + \cdots = \sum_{n=1}^{\infty} (-1)^{n} \frac{x^{n+1}}{n+1}
$$
$$
\frac{1}{1-x} = 1 + x + x^2 + x^3 + x^4 + x^5 + \cdots = \sum_{n=0}^{\infty} x^n
$$