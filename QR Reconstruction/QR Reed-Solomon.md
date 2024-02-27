Use the [[Finite Field]] $\mathbb{F}_{256}$ with elements encoded as bytes of 8 bits: $$b_{7}b_{6}b_{5}b_{4}b_{3}b_{2}b_{1}b_{0}$$
Addition and Subtraction are exclusive or

For multiplication, multiply as polynomials, then take remainder modulo a prime polynomial (a common primitive polynomial is $\texttt{100011101}$). 

Why don't we just modulo with the Galois Field size? Because we will end up with lots of duplicate values, and we want to have as many unique values as possible in the field, so that a number always has one and only projection when doing a modulo or a XOR with the prime polynomial.


Generator Polynomial: $$\begin{align*}
g_{n}(x)&= \prod_{i=0}^{n-1}(x-\alpha^{i})\\
g_{3}&= (x-1)(x-\alpha)(x-\alpha^{2})
\end{align*}$$

>[!alg]

$$\begin{align*}
&\textbf{Algorithm } \text{Encode}\\

\end{align*}$$