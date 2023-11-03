>[!note] 1

Let $x_{i}$ be the number of truckloads sent to plant $i$. Clearly, $$\sum_{i=1}^{n}x_{i}=m$$The goal is to maximize $$\sum_{i=1}^{n}f_{i}(x_{i})$$

Let $\texttt{OPT}(i,j)$ be the maximum value of $\sum_{l=1}^{i}f_{i}(x_{i})$ such that $\sum_{l=1}^{i}x_{l}=j$ . 

$$\texttt{OPT}(i,j)=\max\{\texttt{OPT}(i-1,j-x_{i})+f_{i}(x_{i}),\texttt{OPT}()\}$$


>[!note] 2



>[!note] 3