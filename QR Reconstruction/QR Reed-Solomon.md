Use the [[Finite Field]] $\mathbb{F}_{256}$ with elements encoded as bytes of 8 bits: $$b_{7}b_{6}b_{5}b_{4}b_{3}b_{2}b_{1}b_{0}$$
Addition and Subtraction are exclusive or

For multiplication, multiply as polynomials, then take remainder modulo a prime polynomial (a common primitive polynomial is $\texttt{100011101}$). 

