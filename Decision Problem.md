>[!def]
A *decision problem* is an [[Algorithm]]ic problem where the desired output is $\texttt{true}$ or $\texttt{false}$.

Examples:
- [[3-SAT Problem]] 

Non-examples:
- [[Max Flow Problem]] is an [[Optimization Problem]]

Can convert an [[Optimization Problem]] to a [[Decision Problem]] by asking 
1. is it $≥k$ for each $k$
2. if there is an upper bound on the [[Optimization Problem]] result, do binary search on $k$
Obviously, [[Decision Problem]] may be reduced to [[Optimization Problem]].

So, [[Decision Problem]] and [[Optimization Problem]] are equivalent. 