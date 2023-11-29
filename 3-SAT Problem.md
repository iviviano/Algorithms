Input: 
- $n$ [[Boolean]] variables $x_{1},\ldots,x_{n}$
- a boolean formula $\Phi(x_{1},\ldots,x_{n})$ using
	- [[And]] $\land$
	- [[Or]] $\lor$
	- [[Not]] $\bar{x_{i}}$
	- parentheses for order of operations

>[!def]
>Each instance of an $x_i$ is a *literal* (includes [[Not]]s)

Result: Any formula may be written in 3-[[Conjunctive Normal Form]], meaning each clause has at most 3 literals. 

>[!note]
>Nobody knows how to solve this in [[Polynomial Run Time]], but nobody knows how to prove you can't either.



