Inputs:
- [[Directed Graph]] $G=(V,E)$
- Capacities $c(e)>0$ for all $e\in E$
- Demands $d(v)\in \mathbb{Z}$ for all $v\in V$

>[!def]
A *circulation* on $G$ is a value $s(e)$ on each edge $e\in E$ satisfying: 
>1. $s(e)≤c(e)$
>2. $s(e)≥0$
>3. for all $v\in V$, $$\sum_{e \text{ into }v}s(e)-\sum_{e \text{ out of }v}s(e)=d(v)$$

Output:
- Is there a circulation on $G$?

>[!note]
>A [[Graph]] $G$ has a circulation only if $\sum d(v)=0$

>[!alg]
Step 1: Convert to [[Max Flow Problem]]:
>1. Add a source $s$ to $V$. 
>2. For each $v\in V$ with $d(v)<0$, add an [[edge]] $e$ from $s$ to $v$ with capacity $-d(v)$.
>3. Add a sink $t$ to $V$.
>4. For each $v\in V$ with $d(v)>0$, add an [[edge]] $e$ from $v$ to $t$ with capacity $d(v)$.
>
Step 2: Solve the [[Max Flow Problem]] on $G=(V,E)$ with capacities $c(e)$.

If there is a feasible circulation, $$\sum_{e \text{ out of }s}c(e)=\sum_{e \text{ into }t}c(e)=D$$Additionally, $D$ must be the minimum cut, if there is a circulation.

>[!proof]
Suppose there is a feasible circulation. Then, for each $v\in V$ with $d(v)<0$, $$\sum_{e \text{ into }v}s(e)-\sum{e \text{ out of }v}=d(v)$$So, we can create a valid flow by giving all [[edge]]s $e$ from $s$ to $v$ value $-d(v)$. Therefore, $|f|≥d$. As $D$ is the value of a [[Cut]], $|f|≤D$. So, $|f|=D$.
>
Suppose the max flow has value $D$. Removing the source and sink and all associated edges gives the circulation on $G$.

