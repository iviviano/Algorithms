>[!note] 1

(a) Repeat the following until $S$ has $k$ elements put the largest element of $A$ in $S$; remove one instance of this element from $A$. 

As $A$ is finite, it has a largest element. Clearly, this is a feasible algorithm as each element of $S$ comes from $A$ and $k$ elements of $A$ are added to $S$.

>[!proof]
Let $S$ be the solution given by our [[Greedy Paradigm]] [[Algorithm]] and let $X$ be any other [[Subset]] of $A$ with $k$ elements. Sort both $S$ and $X$ by non-increasing order of elements.
>
Suppose that $k>0$. Clearly, if $k=0$, $S=X=\emptyset$, so $S$ is optimal.
>
Let $P(i)$ be the statement that $S[i]≥X[i]$.
>
Base Case: $i=1$. 
As $S$ is sorted in non-increasing order and $S$ contains the largest element of $A$, $S[1]$ is the largest element of $A$. As $X$ is also a [[Subset]] of $A$, $X[1]$ is not larger than the largest element of $A$. So, $S[1]≥X[1]$, giving $P(1)$.
>
Inductive Step: let $i\in[k-1]$ and suppose that $P(i)$ is true.
$S[i]$ was the largest element of $A$ before it was removed, and $X[i]≤S[i]$. $X[i+1]≤X[i]$ as $X$ is in non-increasing order. So, $X[i+1]≤S[i]$. As there are $i$ elements of $X$ at least as large as $X[i+1]$, there are at least $i$ elements of $A$ at least as large as $X[i+1]$. So, $X[i+1]$ was still in $A$ when $S[i+1]$ was chosen. As $S[i+1]$ was the largest element of $A$ at this point, $X[i+1]≤S[i+1]$. $\therefore P(i+1)$.
>
Therefore, by [[Principle of Mathematical Induction]], $P(i)$ for all $i\in[k]$.
>
As $S[i]≥X[i]$ for all $1≤i≤k$, clearly $$\sum_{i=1}^{k}S[i]≥\sum_{i=1}^{k}X[i]$$So, no possible solution is better than $S$, showing that my [[Algorithm]] is optimal.

(b) False. Let $T(n)=n^{3}\log_{2}n$. Then, $$T\left(\frac{n}{2}\right)=\frac{n^{3}}{8}\log_{2}\frac{n}{2}$$so, $$\begin{align*}\\
8T\left(\frac{n}{2}\right)+n^{3}&=8 \frac{n^{3}}{8}\log_{2} \frac{n}{2}+n^{3}=n^{3}\log_{2}n -n^{3}\log_{2}2+n^{3}\\\\
&= n^{3}\log_{2}n-n^{3}+n^{3}=n^{3}\log_{2}n=T(n)
\end{align*}$$so, $T(n)$ satisfies the recurrence relation. However, $T(n)=O(n^{3}\log n)$, so $T(n)≠O(\log n)$.

(c) 
>[!proof]
Let $P(n)$ be that $T(n)=\frac{n}{2}+1$.
>
Base Case: $n=0$.
If $n=0$, $\frac{n}{2}+1=\frac{0}{2}+1=1=T(0)$. So, $T(0)$. 
>
Inductive Step: let $n>0$ be even, and assume $P(n-2)$. 
$$T(n)=T(n-2)+1=\frac{n-2}{2}+1+1=\frac{n}{2}-1+2=\frac{n}{2}+1$$So, $P(n)$.
>
By (PMI), $P(n)$ for all even $n≥0$.

So, $T(n)=O(n)$ by the [[Asymptotic Tight Bound for Polynomials Proposition]].

(d) True. Clearly, this does not increase the cost of $T$. As there were already no other [[Spanning Tree]]s with lower cost than $T$, $T$ is still a [[Minimum Spanning Tree]].

(e) To prove that this is feasible, we must show that its output is a [[Spanning Tree]]. A [[Spanning Tree]] $T$ is a [[Subset]] of $E$ such that $(V,T)$ is [[Connected]] and [[Acyclic]]. Clearly, $T$ is a [[Subset]] of $E$, as it starts as all of $E$ and elements are removed from there. It is also obvious that $E$ is connected, since we assume that $G$ is connected, and no edges are removed from $T$ that disconnect it.

If $T$ had a [[Cycle]], then some edge could be removed without disconnecting $(V,T)$. So, the [[Algorithm]] cannot end without $T$ being acyclic. As there are finitely many edges the algorithm does terminate. [[therefore]] $T$ is a [[Spanning Tree]]


>[!note] 2

(a)
>[!alg]

$$\begin{align*}
&\textbf{Algorithm } \text{Index Equaling Element?}\\
&\textbf{Input: } \text{Sorted Array } A \text{ of length }n \text{ with no duplicate elements}\\
&\textbf{Output: } \text{Boolean indicating whether }A[i]=i \text{ for some }i\in[n]\\
&\textbf{return } fun(0,n)\\\\
&fun(start,end):\\
&\quad \text{Let }l=end-start\\
&\quad \text{Let }middle=\left\lfloor\frac{l}{2}\right\rfloor+start\\
&\quad \text{Let }found=\text{false}\\
&\quad \textbf{If } l\%2=1 \textbf{ then:}\\
&\quad \quad found=A[middle]==middle\\
&\quad \textbf{If } found\lor l==1 \textbf{ then:}\\
&\quad \quad \textbf{return } found\\
&\quad \textbf{If } A[middle]\gt middle \textbf{ then:}\\
&\quad \quad \textbf{return } fun(start,middle)\\
&\quad \textbf{Else:}\\
&\quad \quad \textbf{return } fun\left(\left\lceil \frac{l}{2}\right\rceil+start,end\right)
\end{align*}$$

Let $P(l)$ be that if $end-start=l$ $fun(start,end)$ returns $\text{true}$ if $\exists i:start≤i<end:A[i]=i$ and $\text{false}$ otherwise.

Base Case: $l=1$
$\lfloor \frac{l}{2}\rfloor=\lfloor \frac{1}{2}\rfloor=0$, so $middle$ is assigned to $start$. Since $n\%2=1\%2=1$, $found$ is assigned to whether $A[start]=start$. Since $l==1$, $found$ is returned. As $start$ is the only integer at least as big as $start$ and less than $end$ in this case $found$ is $\text{true}\iff\exists i:start≤i<end$. $\therefore P(1)$ holds.

>[!prop] Claim:
If $A[middle]<middle$, then there cannot be an element in $A$ with index $i<middle$ and $A[i]=i$. 
>>[!proof]
>Suppose not: $A[middle]≥middle$ and for some $i<middle:A[i]=i$. As the elements of $A$ are unique integers, $A[middle]≥A[i]+middle-i$, since each consecutive pair of values must differ by at least one, and $A$ is sorted. Then, $$A[middle]≥A[i]+middle-i=i+middle-i=middle$$So, $A<middle$ is false. By contradiction, the claim is true.

>[!prop] Claim 2:
>If $A[middle]>middle$, then if $A[i]=i,i<middle$. 
>>[!proof]

Assume $A[middle]>middle$ and $A[i]=i$. Suppose that $i≥middle$. As the elements of $A$ are unique integers, $A[i]≥A[middle]+i-middle$, since each consecutive pair of values must differ by at least one, and $A$ is sorted. Then $$i=A[i]≥A[middle]+i-middle$$


Inductive Step: let $l$ be given with $1<l≤n$ and assume that for all $k\in[k-1],P(k)$.
Suppose that $l$ is even. Then, $\lfloor \frac{l}{2}\rfloor=\lceil \frac{l}{2}\rceil= \frac{l}{2}$. $found$ is $\text{false}$, as $l$ is even. As $l≠1$, the [[Algorithm]] proceeds to the next if statement. If $A[middle]≤middle$, then Claim 2 implies that if $A[i]=i$, $i<middle$. So, we need only check if there is some index $i:start≤i<middle$ such that $A[i]=i$. Since $middle-start=\frac{l}{2}<l$, this is exactly what $fun(start,middle)$ does by the inductive hypothesis. If $A[middle]<middle$, then Claim 1 implies that we only need to check indices $i:middle≤i<end$ for $A[i]=i$. As $\lfloor \frac{l}{2}\rfloor +start= \frac{l}{2}+start=middle$, the inductive hypothesis guarantees that this is exactly what $fun(\lfloor \frac{l}{2}\rfloor+start,end)$ does since $end-middle= \frac{l}{2}<l$. So, $P(l)$ holds for even $l$.

Suppose $l$ is odd. Then, $\lfloor \frac{l}{2}\rfloor= \frac{l-1}{2},\lceil \frac{l}{2}\rceil= \frac{l+1}{2}$. Since $l\%2=1$, the first conditional executes. $found$ is assigned to true $\iff$ $A[middle]=middle$. Clearly, if $found$ is true, then we may return true. This is what happens since $found\lor l==1$ will be true. If $found$ is false, $found\lor l==1$ is false since $l>1$. So, the [[Algorithm]] proceeds to the next conditional. Now, suppose $A[middle]≤middle$. Claim 2 implies that if $A[i]=i$, $i<middle$. So, we need only check if there is some index $i:start≤i<middle$ such that $A[i]=i$. Since $middle-start=\frac{l-1}{2}<l$, this is exactly what $fun(start,middle)$ does by the inductive hypothesis. On the contrary, suppose that $A[middle]>middle$. Claim 1 gives that there cannot be an index $i:i<middle$ and $A[i]=i$. Additionally, $A[middle]≠middle$, as $found$ is false. So, we must only check if there is an index $i>middle$ such that $A[i]=i$. Observe$$\left\lceil \frac{l}{2}\right\rceil+start= \frac{l+1}{2}+start= \frac{l-1}{2}+1+start=\left\lfloor \frac{l}{2}\right\rfloor+start+1=middle+1$$and $end-\lceil \frac{l}{2}\rceil-start=l- \frac{l-1}{2}<l$, and $l≥3$, so $l- \frac{l-1}{2}≥1$. This gives that $fun(\lceil \frac{l}{2}\rceil,end)$ returns the whether $A[i]=i$ for some $i:start≤i<end$ by the inductive hypothesis. So, $P(l)$ holds for odd $l$.

As $P(l)$ is true for even and odd $l$, $P(l)$ holds generally.

Therefore, by [[Principle of Mathematical Induction]], $P(l)$ for all $l\in \mathbb{N}$. As the algorithm returns $fun(0,n)$ and $n-0=n\in \mathbb{N}$, the [[Algorithm]] works for any input size $n≥1$.

Runtime Analysis:
I will analyze the runtime by counting array-indexing operations: $T(n)$. Then, the [[Worst Case Run Time]] occurs when $n=2^{k}-1$ for some $k$, and the [[Algorithm]] returns false.


(b) 


>[!note] 3
(a) Let $P=\{1,4\},W=\{3,6\}$. The [[Algorithm]] by smallest $|p_{i}-w_{f(i)}|$ will make associations: $(1,6),(4,3)$ of pumpkin-watermelon pairs. The average difference for this solution is $$\sum_{i=1}^{2}|p_{i}-w_{f(i)}|=|1-6|+|4-3|=5+1=6$$If instead, we used the associations $(1,3),(4,6)$, the average difference would be $$\sum_{i=1}^{2}|p_{i}-w_{f(i)}|=|1-3|+|4-6|=2+2=4$$

(b) 
For this proof, I will use the [[Triangle Inequality]]: $$\begin{equation}
|A-B|≤|A|+|B|
\end{equation}$$

>[!proof] [[Exchange Argument]]:
Let $f$ be a matching of pumpkins to watermelons where the pumpkins are sorted by non-decreasing weight.
Let $i\in[n-1]$ be given with $w_{f(i)}≥w_{f(i+1)}$. Let $g:[n]\rightarrow[n]$ be defined by$$g(j)=\left\{\begin{align}
&f(j+1)\text{ if }j=i\\
&f(j-1)\text{ if }j=i+1\\
&f(j)\text{ otherwise}\\
\end{align}\right.$$Clearly, $g$ is a valid matching function, as $f$ is. I will show that $$\frac{1}{n}\sum_{j=1}^{n}|p_{j}-w_{g(j)}|\le \frac{1}{n}\sum_{j=1}^{n}|p_{j}-w_{f(j)}|$$The only two different terms in this sum are for $j=i,i+1$, since these are the only two inputs for which $f$ and $g$ differ. So, I must only show $$|p_{i}-w_{g(i)}|+|p_{i+1}-w_{g(i+1)}|≤|p_{i}-w_{f(i)}|+|p_{i+1}-w_{f(i+1)}|$$
Now, $$\begin{align*}\\
&|p_{i}-w_{g(i)}|+|p_{i+1}-w_{g(i+1)}|=|p_{i}-w_{f(i+1)}|+|p_{i+1}-w_{f(i)}|\\
\end{align*}$$
There are 3 cases that must be considered:
>
Case $1$: $p_{i}≤w_{f(i+1)},p_{i+1}\le w_{f(i)}$. Then, $$|p_{i}-w_{f(i+1)}|+|p_{i+1}-w_{f(i)}|=w_{f(i+1)}-p_{i}+w_{f(i)}-p_{i+1}$$
Now, $$\begin{align*}
&w_{f(i+1)}-p_{i}+w_{f(i)}-p_{i+1}\le |w_{f(i+1)}-p_{i}+w_{f(i)}-p_{i+1}|\\
&=|w_{f(i)}-p_{i}+w_{f(i+1)}-p_{i+1}|\le|w_{f(i)}-p_{i}|+|w_{f(i+1)}-p_{i+1}| \quad(1)\\
&=|p_{i}-w_{f(i)}|+|p_{i+1}-w_{f(i+1)}|
\end{align*}$$
Case 2: $p_{i}\le w_{f(i+1)},p_{i+1}>w_{f(i)}$. Then, $$|p_{i}-w_{f(i+1)}|+|p_{i+1}-w_{f(i)}|=w_{f(i+1)}-p_{i}+p_{i+1}-w_{f(i)}$$
Apply $w_{f(i)}≥w_{f(i+1)}$: $$\begin{align*}\\
&w_{f(i+1)}-p_{i}+p_{i+1}-w_{f(i)}≤w_{f(i)}-p_{i}+p_{i+1}-w_{f(i+1)}\\
&\le|w_{f(i)}-p_{i}+p_{i+1}-w_{f(i+1)}|\le|w_{f(i)}-p_{i}|+|p_{i+1}-w_{f(i+1)}|\quad(1)\\
&=|p_{i}-w_{f(i)}|+|p_{i+1}-w_{f(i+1)}|
\end{align*}$$
Case 3: $p_{i}>w_{f(i+1)},p_{i+1}>w_{f(i)}$. Then, $$|p_{i}-w_{f(i+1)}|+|p_{i+1}-w_{f(i)}|=p_{i}-w_{f(i+1)}+p_{i+1}-w_{f(i)}$$
Now, $$\begin{align*}
&p_{i}-w_{f(i+1)}+p_{i+1}-w_{f(i)}\le|p_{i}-w_{f(i+1)}+p_{i+1}-w_{f(i)}|\\
&=|p_{i}-w_{f(i)}+p_{i+1}-w_{f(i+1)}|≤|p_{i}-w_{f(i)}|+|p_{i+1}-w_{f(i+1)}|\quad(1)\\
\end{align*}$$
The last possible combination: $p_{i}>w_{f(i+1)},p_{i+1}\le w_{f(i)}$ is not actually possible: $$w_{f(i+1)}<p_{i}≤p_{i+1}$$as $p$ is non-increasing. So, this condition implies that $w_{f(i+1)}<w_{f(i)}$, contradiction my assumption otherwise.

So, for all possible values of $p_{i},p_{i+1},w_{f(i)},w_{f(i+1)}$ with the stipulation $w_{f(i)}\ge w_{f(i+1)}$, $$\frac{1}{n}\sum_{j=1}^{n}|p_{j}-w_{g(j)}|\le \frac{1}{n}\sum_{j=1}^{n}|p_{j}-w_{f(j)}|$$This proves that the swap of any two "adjacent" watermelons $w_{f(i)},w_{f(i+1)}$ doesn't worsen the solution. 

Let $f$ be any matching of pumpkins to watermelons with the watermelons. Sort the watermelons in non-decreasing order. Then, $f$ induces an ordering of the pumpkins. Sort this ordering in non-decreasing order with bubble sort. (CLARIFY). 


