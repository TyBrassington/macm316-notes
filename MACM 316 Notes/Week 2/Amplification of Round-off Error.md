### Subtractive Cancellation

When two very close numbers are added or subtracted from one another, the error bound is just as large as the estimation of the result, giving a result that is much smaller in magnitude.

***Avoid subtracting nearly equal numbers***


### Division by small numbers

Dividing by a small number, or multiplying by a large number can magnify the absolute error

If $fl(x)=x(1+\delta)$ for some $\delta$, and $z\,=\,10^{-n}$, then $$x⨸z = fl\left( \frac{fl(x)}{fl(z)} \right)=\frac{x(1+\delta)}{z}=\frac{x}{z}=\frac{\delta x}{z}=\frac{x}{z}+\underbrace{ (\delta x)\times 10^{n} }_{ round-off \,error }$$
In this case, the absolute error in floating-point division is $|x\delta| \times 10^{n}$, which for large n, can be much larger than $|x\delta|$

### Accumulation of Round-off error

Each floating-point operation potentially introduces [[Round-off error|round-off error]], which can accumulate as the number of such operations increases. To minimize [[Round-off error]] (and speed up computation): reduce the number of floating-point operations (flops) by using improved algorithms — e.g. by rearranging a calculation to reduce the number of floating-point operations performed.


![[lecture-operation-count.png]]

### Horner's Method

[[Horner's Method]] is an algorithm for polynomial evaluation in which the polynomial is written in nested form. This allows the evaluation of a polynomial of degree n with only n multiplications and n additions. This is optimal, since there are polynomials of degree n that cannot be evaluated with fewer arithmetic operations. 

$$
a_0 + a_1x + a_2x^2 + \cdots + a_nx^n = a_0 + x \left( a_1 + x \left( a_2 + x \left( a_3 + \cdots + x(a_{n-1} + xa_n) \right) \right) \right)
$$

![[lecture-horners-method.png]]

