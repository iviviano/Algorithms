>[!note] 1

Let $x_{i}$ be the number of truckloads sent to plant $i$. Clearly, $$\sum_{i=1}^{n}x_{i}=m$$The goal is to maximize $$\sum_{i=1}^{n}f_{i}(x_{i})$$

Let $\texttt{OPT}(i,j)$ be the maximum value of $\sum_{l=1}^{i}f_{i}(x_{i})$ such that $\sum_{l=1}^{i}x_{l}=j$ . 

$$\texttt{OPT}(i,j)=\max\{\texttt{OPT}(i-1,j-k)+f_{i}(k):0\le l\le j\}$$

Proof: if there are $i$ factories and $j$ trucks, we can send anywhere from $0$ to $j$ trucks to factory $i$. If we send $k$ trucks to factory $i$, 


>[!note] 2



>[!note] 3