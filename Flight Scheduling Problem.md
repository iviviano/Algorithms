Input:
- 

Compatible considerations:
1. Can't overlap
2. End location of $i$ is start location of $j$
3. maintenance time

Can we schedule all of the flights with $k$ planes?

>[!alg]
Construct a circulation network $G=(V,E)$:
>1. $V=\{u_{i}\}\cup\{v_{i}\}$
>2. For each flight $i$, add $u_{i}$ and $v_{i}$ with edge $(u_{i},v_{i})=e$. $c(e)=l(e)=1$
>3. For each compatible flight pair $i,j$, add [[edge]] $(v_{i},u_{j})=e$. $c(e)=1$, $l(e)=0$
>4. Add a source $s$ and sink $t$ to $V$
>5. Add an [[edge]] $e=(s,u_{i})$ with $c(e)=1$ and $l(e)=0$ for all $i$
>6. Add an [[edge]] $e=(v_{i},t)$ with $c(e)=1$ and $l(e)=0$ for all $i$
>7. Add an [[edge]] $e=(s,t)$ with $c(k)=k$ and $l(e)=0$
>8. Demand is $d(v)=0$ for all $v≠s,t$. $d(s)=-d(t)=-k$
>



Add edges from the end of each flight to the beginning of each flight (only if this satisfies the overlap constraint). These edges have lower bound $0$. Add edges that are the flights. These edges have lower bound $1$. All edges have capacity $1$. Add a source $s$ and sink $t$. Add edges from $s$ to the earliest $k$ flights. Add edges from the latests

Each edge has capacity $c(e)$ and lower bound $l(e)$. A valid flow must satisfy $l(e)≤f(e)≤c(e)$. 