
### Double-precision (64 bits) Binary Representation

The first bit is a sign indicator, denoted by $s$. This is followed by an 11-bit exponent, $c$, called the **exponent**, and a 52-bit binary fraction, $f$, called the **mantissa**

![[double-prec-floating-point.png]]

Since 52 binary digits correspond to between 16 and 17 decimal digits, we can assume that a number represented in this system has at least **16 decimal digits of precision**.

The exponent of 11 binary digits gives a range of 0 to $2^{11} - 1$  = 2047. To accommodate both positive and negative integers, 1023 is subtracted from the exponent, so the range of the exponent is actually -1023 to 1024.

Using this system gives a floating-point number of the form

$$
(-1)^{s}\,2^{c-1023}\,(1+f)
$$
### Floating-point number system

A floating-point number system is the set of numbers
$$
\pm 0.d_{1} d_{2}d_{3}\cdots d_{k} \times b^{n},
$$
where $d$ is the mantissa, and $n$ is the exponent.

### Floating-point Representation & Arithmetic, Errors

Given $x \,\epsilon\, \mathbb{R}$ in a floating-point system with base $b$, precision $k$, if $x$ is within the numerical range of the system, but has more than $k$ digits of significance, the mantissa needs to be terminated.

##### Chopping (truncation)
"Throw away" all the digits after $k^{th}$
- Simple method
- Biased, since it always moves the result towards zero

##### Rounding
Look at the first digit to be discarded, to decide whether to round up or down.
- Unbiased
- Introduces smaller error
- Used in the IEEE standard

We write $fl(x)$ to denote the **floating-point form** (or machine representation) of $x$.
$$
x \approx fl(x)
$$
**[[Round-off error]]** : The error arising from representing a real number by its floating-point form

### Absolute and Relative Errors

**Absolute Error:** $|p-p*|$

**Relative Error:** $\frac{|p-p*|}{|p|}$ (provided $p \neq0$)

### Overflow and Underflow

In binary double precision, the smallest normalized positive number,
$$
\overbrace{ 0 }^{s } \quad \overbrace{ 0000000001 }^{ c } \quad \underbrace{ \overbrace{ 0000 \cdots0000 }^{ f } }_{ 52 \,zeroes } = 2^{-1022}
$$

The largest representable number,
$$
\overbrace{ 0 }^{s } \quad \overbrace{ 11111111110 }^{ c } \quad \underbrace{ \overbrace{ 1111 \cdots1111 }^{ f } }_{ 52 \,ones } = 2^{1023}
$$
Larger (in absolute value) numbers result in **overflow**.

[[Machine Epsilon]]:  the smallest floating-point number that can be added to 1.0 and still produce a sum that is greater than 1.0.