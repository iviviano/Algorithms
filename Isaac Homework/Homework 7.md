>[!note] 1

Step 1:

Let $p(j)$ be the number of minimum paths to vertex $j$ from $1$.

Let $\texttt{OPT}(i,j)$ be the number of paths length $j$ to vertex $i$ from $1$.
Let $N(i)=\{k:(k,i)\in E\}$.

Step 2:
$$\texttt{OPT}(i,j)=\sum_{k\in N(i)}\texttt{OPT}(k,j-1)$$

Step 3:


Step 4: 
Base cases: $\texttt{OPT}(1,0)=1$. For all $i\ne 1$, $\texttt{OPT}(i,0)=0$. 


Step 5:


Step 6:
$$\begin{align*}
&\textbf{Algorithm } \text{Large Jest}\\
&\textbf{Input: } \text{Directed Graph }G=(V,E)\\
&\textbf{Output: } \text{}\\
&compute\ p(j)
\end{align*}$$

Step 7:

>[!note] 2


