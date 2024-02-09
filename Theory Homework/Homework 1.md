>[!note] 1

(a) The [[Set]] containing the numbers $1,3,5$ and $7$
(b) The [[Set]] of all even integers.
(c) The [[Set]] of all positive even integers
(d) The [[Set]] of all positive multiples of $6$
(e) 
(f) The [[Set]] containing nothing at all.

 (assuming $0\notin \mathbb{N}$)

>[!note] 2

(a) $\{1,10,100\}$
(b) $\mathbb{N}-\{1,2,3,4,5\}$
(c) $\{1,2,3,4\}$
(d) $\{\texttt{aba}\}$
(e) $\{\epsilon\}$
(f) $\emptyset$

>[!note] 3

(a) No 
(b) Yes
(c) $A\cup B=A$
(d) $A\cap B=B$
(e) $\{(\texttt{x,x}),(\texttt{x,y}),(\texttt{y,x}),(\texttt{y,y}),(\texttt{z,x}),(\texttt{z,y})\}$
(f) $\{\emptyset,\{\texttt{x}\},\{\texttt{y}\},\{\texttt{x,y}\}\}$

>[!note] 4

(a) $f(2)=7$
(b) [[Range]] of $f$ is $Y$, [[Domain]] of $f$ is $X$
(c) $g(2,10)=6$
(d) [[Range]] of $g$ is $Y$, [[Domain]] of $g$ is $X\times Y$
(e) $f(4)=7$, $g(4,f(4))=g(4,7)=8$

>[!note] 5

Enumerate the elements of $A=\{a_{1},\ldots,a_{n}\}$. Let $P(k)$ be $|\mathcal{P}(\{a_{1},\ldots,a_{k}\})|=2^{k}$.

Base Case: $k=0$. 
Here, $A=\emptyset$. Note that $\mathcal{P}(\emptyset)=\{\emptyset\}$ and $2^{k}=1$, so $P(0)$ holds.

Inductive Step: Let $k≥0$ be given and assume $P(k)$.
Let $A_{k}=\{a_{1},\ldots,a_{k}\}$ and $A_{k+1}=\{a_{1},\ldots,a_{k+1}\}$. 