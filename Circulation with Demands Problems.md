Inputs:
- [[Directed Graph]] $G=(V,E)$
- Capacities $c(e)>0$ for all $e\in E$
- Demands $d(v)\in \mathbb{Z}$ for all $v\in V$

>[!def]
A *circulation* on $G$ is a value $s(e)$ on each edge $e\in E$ satisfying: 
>1. $s(e)≤c(e)$
>2. $s(e)≥0$
>3. for all $v\in V$, $$\sum_{e \text{ into }v}s(e)-\sum_{e \text{ out of }v}s(e)=d(v)$$

Ouput:
- Is there a circulation on $G$


>[!note]
>A [[Graph]] $G$ only has a circulation if $\sum d(v)=0$

