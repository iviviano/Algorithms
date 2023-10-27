---
mathLink: segmented least squares problem
---
Given points $$P=\{(x_{1},y_{1}),\ldots,(x_{n},y_{n})\}$$least squares finds "line of best fit". Minimize $$\sum(ax_{i}+b-y_{i})^{2}$$for fit line $y=ax+b$.

>[!def]
>*Segmented least squares* uses multiple linear fits to approximate different regions of the data set. This is done by [[Partition]]ing $P$ and then computing the least squares for each partition.

Best fit errors: $$\sum_{i\in P_{k}}(y_{i}-(a_{k}x_{i}+b_{k}))^{2}$$So, the goal is to minimize $$E=\sum E_{j}=\sum_{j=1}^{k}\sum_{i\in P_{j}}(y_{i}-(a_{j}x_{i}+b_{j}))^2$$but this allows overfitting, we could just have $n$ lines. We must add a penalty term $kC$. 

Question: is point $j$ in the same part as $j-1$. 

>[!alg] 

Step 1: $\text{OPT }(j)=$ minimum cost on first $j$ points. 

Step 2: Let $e_{ij}$ be the least square error from $i$ to $j$. Then, $$\text{OPT }(j)=\min\{\text{OPT }(i-1)+e_{ij}+C:i≤j\}$$
Step 3: Proof of step 2

Step 4: Base case: $j=1$

Step 5: Goal is to compute $\text{OPT }n$

Step 6: Write algorithm

